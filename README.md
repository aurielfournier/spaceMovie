# spaceMovie color palette generator
Chris Hamm  


## Space Movie color palettes
The colors used in this package were all found using publically available sources, many of them from LucasArts themselves. For example:

- [Rebels](http://www.starwars.com/news/star-wars-rebels-costume-color-guide-for-padawans-twileks-and-more)
- [Imperials](http://www.starwars.com/news/star-wars-rebels-costume-color-guide-for-imperials)

Kartik Ram's [Wes Anderson](https://github.com/karthik/wesanderson) color palette inspired me to create this package and I followed his implementation for consistency.

#### A brief note about the yellow color in the "Main" list: I don't believe this is the color of yellow used in the main title. I found this color referenced on the internet [here](), but it just looks too dark. 

### Installation

```r
devtools::install_github("butterflyology/spaceMovie")
```

### Usage

```r
library("spaceMovie")
```

### Chopper

```r
library("ggplot2")
ggplot(iris, aes(Sepal.Length, Sepal.Width, color = Species)) +
  theme_bw() +
  geom_point(size = 3) +
  scale_color_manual(values = SW_palette("Chopper")) +
  labs(y = "Sepal width", x = "Sepal length") +
  theme(legend.text = element_text(face = "italic"))
```

<img src="figure/chopper-1.png" style="display: block; margin: auto;" />

### Boba

```r
SW_palette("Boba")
```

<img src="figure/Boba-1.png" style="display: block; margin: auto;" />

### Zeb

```r
SW_palette("Zeb")
```

<img src="figure/Zeb-1.png" style="display: block; margin: auto;" />

### Sabine

```r
SW_palette("Sabine")
```

<img src="figure/Sabine-1.png" style="display: block; margin: auto;" />


### Main

```r
qplot(factor(cyl), data = mtcars, geom = "bar", fill=factor(vs)) +
  scale_fill_manual(values = SW_palette("Main"))
```

<img src="figure/Main-1.png" style="display: block; margin: auto;" />

### Inquisitor volcano

```r
SW_colors_1 <- SW_palette("Inquisitor", 21, type = "continuous")
image(volcano, col = SW_colors_1, las = 1)
```

<img src="figure/Inquisitor-1.png" style="display: block; margin: auto;" />

### Heat map

```r
SW_colors_2 <- SW_palette("Hera", 100, type = "continuous")

ggplot(heatmap, aes(x = X2, y = X1, fill = value)) + 
  geom_tile() + 
  scale_fill_gradientn(colours = SW_colors_2) + 
  scale_x_discrete(expand = c(0, 0)) +
  scale_y_discrete(expand = c(0, 0)) + 
  coord_equal() 
```

<img src="figure/Heat-1.png" style="display: block; margin: auto;" />
