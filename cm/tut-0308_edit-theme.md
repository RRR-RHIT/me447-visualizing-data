
edit the plot theme
-------------------

Our scatterplot script to this point consists of

``` r
library(ggplot2)

time_sec  <- seq(0, 2*pi, by = pi/50) # sec
freq      <- 2                        # r/s
displ_mm  <- sin(freq * time_sec)     # mm
vibr_data <- data.frame(time_sec, displ_mm)

f1 <- ggplot(data = vibr_data, aes(x = time_sec, y = displ_mm)) +
    geom_point(shape = 21
        , color = "slateblue4"
        , fill  = "slateblue1"
        , size  = 3
        ) +
    xlab("Time (sec)") + 
    ylab("Position (mm)") +
    ggtitle("Scatterplot") +
    scale_y_continuous(limits = c(-2, 2), breaks = seq(-2, 2, 1))
```

The gray background is a *ggplot2* default setting. We can use ggplot2 *themes* to change the background (and every other default setting as well).

In the first example, we'll use one of the set of themes available in the *ggplot2* package.

``` r
f1 <- f1 +
    theme_light()

print(f1)
```

![](tut-0308_edit-theme_files/figure-markdown_github-ascii_identifiers/unnamed-chunk-3-1.png)

Examples of all the default themes are illustrated at Wickham's [ggplot2 website](http://ggplot2.tidyverse.org/reference/ggtheme.html).

Control the size and font style using the `theme()` function. I use the `rel()` size argument to make all text the same relative size (`0.9`) and type (`"plain"`).

``` r
f1 <- f1 + 
    theme(plot.title = element_text(size = rel(0.9), face = "plain")  
        , axis.title = element_text(size = rel(0.9), face = "plain") 
        , axis.text = element_text(size = rel(0.9), face = "plain")
        )

print(f1)
```

![](tut-0308_edit-theme_files/figure-markdown_github-ascii_identifiers/unnamed-chunk-4-1.png)

Previous tutorial: [edit the scales](tut-0307_edit-scales.md)<br> Next tutorial: [scatterplot exercise](tut-0309_scatterplot-exercise.md)

------------------------------------------------------------------------

[main page](../README.md)<br> [topics page](README-by-topic.md)