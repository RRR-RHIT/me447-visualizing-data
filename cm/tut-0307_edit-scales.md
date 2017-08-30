
edit the scales
---------------

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
    ggtitle("Scatterplot")
```

Suppose we want the graph to have a 2 mm y-scale with tick marks at 1 mm intervals.

``` r
f1 <- f1 +
    scale_y_continuous(limits = c(-2, 2), breaks = seq(-2, 2, 1))

print(f1)
```

![](tut-0307_edit-scales_files/figure-markdown_github-ascii_identifiers/unnamed-chunk-3-1.png)

------------------------------------------------------------------------

Self-check quiz

1.  Explain the values assigned to the `limits` argument
2.  Explain the values assigned to the `breaks` argument

Confirm your answers by typing the following in your Console and reading the results in *Help* pane.

-   `?c()`
-   `?scale_y_continuous`

------------------------------------------------------------------------

Previous tutorial: [edit axis labels and title](tut-0306_edit-axis-labels-title.md)<br> Next tutorial: [edit theme](tut-0308_edit-theme.md)

------------------------------------------------------------------------

[main page](../README.md)<br> [topics page](README-by-topic.md)