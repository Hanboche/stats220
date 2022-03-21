
This file displays the **meme** that I created using the following R code with the *magick* package.

```r
library(magick)
library(tidyverse)

pkq <- image_read("https://img.shuicaimi.com/c2020/12/09/0l5qdagaza1.jpg") %>%
  image_scale(500)

Bear<-
  image_read("https://www.ygexing.com/upload/223/new/20210303/15690311636958128.jpg")%>%
  image_scale(500)

wechat_text <- image_blank(width = 500,
                           height = 500,
                           color = "#ffffff")%>%
  image_annotate(text = "pkq",
                 color = "#000000",
                 size = 60,
                 font = "Impact",
                 gravity = "center")

baidu_text <- image_blank(width = 500,
                          height = 500,
                          color = "#ffffff")%>%
  image_annotate(text = "bear",
                 color = "#000000",
                 size = 60,
                 font = "Impact",
                 gravity = "center")

first_row <- c(pkq, wechat_text) %>% image_append()
second_row <- c(Bear, baidu_text) %>% image_append()
hbc <- c(first_row, second_row) %>% image_append(stack = TRUE) %>% image_scale(600)
image_write(hbc, "my_meme.png")
```

![](my_meme.png)

Your index.md file needs contain information about the meme you created, for example, what the motivation was, and how your meme is new/original (e.g. an adaption of an existing meme format).

  
