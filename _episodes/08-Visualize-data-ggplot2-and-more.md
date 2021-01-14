---
title: Visualize-data-ggplot2 package and more "
teaching: 20
exercises: 20
questions:
- "How to plot data with ggplot2?"

objectives:
- "Visualise your data using xxx"
keypoints:
- ""
- ""
- ""

---

## ggplot2 package 
Comprare to basic plots, ggplot2 package provides better visually appealing plots. ggplot2 package needs to be installed before use. 
# See bottom right on the RStudio:
click on `Packages` tab, select on `Install`, then search `ggplo2` under Packages to install ggplots2.


![Screenshot of main code listing](../fig/Visualize-your-data-16.png)


Additional packages such as `ggbeeswarm` and `ggrepel` also contain useful functions to add to the functionality of ggplot2.

https://ggplot2.tidyverse.org/
https://www.r-graph-gallery.com/ggplot2-package.html
http://r-statistics.co/ggplot2-Tutorial-With-R.html

# Load your `ggplot2` library
```
library(ggplot2)
mp <- ggplot(xd, aes(x = x8, y = x9))
mp + geom_point()
```
![Screenshot of main code listing](../fig/Visualize-your-data-17.png)

```
mp + geom_point(aes(color = x3, shape = x3), size = 4)
```
(https://www.statsandr.com/blog/graphics-in-r-with-ggplot2/)
(https://derekmichaelwright.github.io/htmls/academic/envdata.html#)
 
 
![Screenshot of main code listing](../fig/Visualize-your-data-18.png)

```
mp + geom_line(size = 2)
```
![Screenshot of main code listing](../fig/Visualize-your-data-19.png)

```
mp + geom_line(aes(color = x3), size = 2)
```
![Screenshot of main code listing](../fig/Visualize-your-data-20.png)

```
mp + geom_smooth(method = "loess")
```

![Screenshot of main code listing](../fig/Visualize-your-data-21.png)

```
mp + geom_smooth(method = "lm")
```
![Screenshot of main code listing](../fig/Visualize-your-data-22.png)

```
xx <- data.frame(data = c(rnorm(50, mean = 40, sd = 10),
                          rnorm(50, mean = 60, sd = 5)),
                 group = factor(rep(1:2, each = 50)),
                 label = c("Label1", rep(NA, 49), "Label2", rep(NA, 49)))
mp <- ggplot(xx, aes(x = data, fill = group))
mp + geom_histogram(color = "black")
```

![Screenshot of main code listing](../fig/Visualize-your-data-23.png)

```
mp + geom_histogram(color = "black", position = "dodge")
```
![Screenshot of main code listing](../fig/Visualize-your-data-24.png)

```
mp1 <- mp + geom_histogram(color = "black") + facet_grid(group~.)
mp1
```
![Screenshot of main code listing](../fig/Visualize-your-data-25.png)

```
mp + geom_density(alpha = 0.5)
```
![Screenshot of main code listing](../fig/Visualize-your-data-26.png)

```
mp <- ggplot(xx, aes(x = group, y = data, fill = group))
mp + geom_boxplot(color = "black")
```
![Screenshot of main code listing](../fig/Visualize-your-data-27.png)

```
mp + geom_boxplot() + geom_point()
```

![Screenshot of main code listing](../fig/Visualize-your-data-28.png)

```
mp + geom_violin() + geom_boxplot(width = 0.1, fill = "white")
```
![Screenshot of main code listing](../fig/Visualize-your-data-29.png)

```
library(ggbeeswarm)
mp + geom_quasirandom()
```
* Make sure your have ggbeeswarm package installed 
![Screenshot of main code listing](../fig/Visualize-your-data-30.png)

```
mp + geom_quasirandom(aes(shape = group))
```
![Screenshot of main code listing](../fig/Visualize-your-data-31.png)

```
mp2 <- mp + geom_violin() + 
  geom_boxplot(width = 0.1, fill = "white") +
  geom_beeswarm(alpha = 0.5)
library(ggrepel)
mp2 + geom_text_repel(aes(label = label), nudge_x = 0.4)
```
![Screenshot of main code listing](../fig/Visualize-your-data-32.png)
```
library(ggpubr)
ggarrange(mp1, mp2, ncol = 2, widths = c(2,1),
          common.legend = T, legend = "bottom")
```
![Screenshot of main code listing](../fig/Visualize-your-data-33.png)