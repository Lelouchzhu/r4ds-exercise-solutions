
# Introduction

## Acknowledgment

All the credit should go to Hadley Wickham for writing the truly fantastic *R for Data Science* book,
without which these solutions would not exist---literally.

I wrote these solutions while using *R for Data Science* in for a course I was teaching at the University of Washington, POLS 501: "Advanced Political Research Design and Analysis".
A special thanks to the political science grad students who took that course with me.

This book was written in the open, with some people contributed pull requests to fix problems.
Thank you to all who contributed via GitHub:


```r
library(dplyr)
# git --no-pager shortlog -ns > contribs.txt
contribs <- readr::read_tsv("contribs.txt", col_names = c("n", "name"))
#> Parsed with column specification:
#> cols(
#>   n = col_integer(),
#>   name = col_character()
#> )

contribs <- contribs %>%
  filter(!name %in% c("jrnold", "Jeffrey Arnold")) %>%
  arrange(name) %>%
  mutate(uname = ifelse(!grepl(" ", name), paste0("@", name), name))

cat("Thanks go to all contributers in alphabetical order: ")
#> Thanks go to all contributers in alphabetical order:
cat(paste0(contribs$uname, collapse = ", "))
#> @A, Adam Blake, @Ben, James Clawson, Nick DeCoursin
cat(".\n")
#> .
```

