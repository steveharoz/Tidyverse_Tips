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

## Custom linetype
To make a custom dash style, specify the length of the line (hex 1-F) and the length of the space.

    geom_line(linetype = "21")

## ggsignif

![image](https://user-images.githubusercontent.com/2257540/128414887-4db0bcc0-537e-4dbd-8aaa-b4e41c73c179.png)


## get ggplot data
![image](https://user-images.githubusercontent.com/2257540/131897725-b029e854-cd21-40a7-8e89-a8cf659364cb.png)

## [`skimr::skim()`](https://docs.ropensci.org/skimr/) 
overview of dataframe

```r
skim(iris)

## ── Data Summary ────────────────────────
##                            Values
## Name                       iris  
## Number of rows             150   
## Number of columns          5     
## _______________________          
## Column type frequency:           
##   factor                   1     
##   numeric                  4     
## ________________________         
## Group variables            None  
## 
## ── Variable type: factor ───────────────────────────────────────────────────────────────────────────
##   skim_variable n_missing complete_rate ordered n_unique top_counts               
## 1 Species               0             1 FALSE          3 set: 50, ver: 50, vir: 50
## 
## ── Variable type: numeric ──────────────────────────────────────────────────────────────────────────
##   skim_variable n_missing complete_rate  mean    sd    p0   p25   p50   p75  p100 hist 
## 1 Sepal.Length          0             1  5.84 0.828   4.3   5.1  5.8    6.4   7.9 ▆▇▇▅▂
## 2 Sepal.Width           0             1  3.06 0.436   2     2.8  3      3.3   4.4 ▁▆▇▂▁
## 3 Petal.Length          0             1  3.76 1.77    1     1.6  4.35   5.1   6.9 ▇▁▆▇▂
## 4 Petal.Width           0             1  1.20 0.762   0.1   0.3  1.3    1.8   2.5 ▇▁▇▅▃
```


