# Tidyverse_Tips
Tips and useful functions


## `simplify()`

    df %>% summarise(x = simplify(strsplit(x, ",")))
    

## `uncount()`
Copies each row n number of times
    
    df <- tibble(x = c("a", "b"), n = c(1, 2))
    uncount(df, n)
    #> # A tibble: 3 x 1
    #>   x    
    #> 1 a    
    #> 2 b    
    #> 3 b  

## `relocate()`
Move a column to a different position

    df <- tibble(a = 1, b = 1, c = 1, d = "a", e = "a", f = "a")
    df %>% relocate(f)
    #> # A tibble: 1 x 6
    #>   f         a     b     c d     e    
    #> 1 a         1     1     1 a     a    
