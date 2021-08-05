# Tidyverse_Tips
Tips and useful functions


    

## [`uncount()`](https://tidyr.tidyverse.org/reference/uncount.html)
Copies each row n number of times
    
    df <- tibble(x = c("a", "b"), n = c(1, 2))
    uncount(df, n)
    #> # A tibble: 3 x 1
    #>   x    
    #> 1 a    
    #> 2 b    
    #> 3 b  

## [`relocate()`](https://dplyr.tidyverse.org/reference/relocate.html)
Move a column to a different position

    df <- tibble(a = 1, b = 1, c = 1, d = "a", e = "a", f = "a")
    df %>% relocate(f)
    #> # A tibble: 1 x 6
    #>   f         a     b     c d     e    
    #> 1 a         1     1     1 a     a    


## [`simplify()`](https://purrr.tidyverse.org/reference/as_vector.html)

    df %>% summarise(x = simplify(strsplit(x, ",")))
    
## [`view()`](https://tibble.tidyverse.org/reference/view.html)
(lowercase!) will view the tibble and return the value, so you can debug long pipe chains.

    df %>%
       view("before filter") %>%
       filter(a > 0) %>%
       view("after filter")
       
## [`%T>%`](https://magrittr.tidyverse.org/reference/tee.html)
will return the original value instead of the result of the function. It's useful for print() or View() calls in the middle of a pipe chain.

df %T>%
   View("before filter") %>%
   filter(a > 0)
   
## ggsignif

![image](https://user-images.githubusercontent.com/2257540/128414887-4db0bcc0-537e-4dbd-8aaa-b4e41c73c179.png)

