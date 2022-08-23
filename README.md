# Creating-mutiple-graphs-with-ggplot

#Creating multiple graphs with ggplot
### make sure to install all the packages below. 
pacman::p_load(datasets, pacman, psych, rio, tidyverse)
### Using the Iris dataset 
view(iris)
glimpse(iris)
attach(iris)

### Basic statistics 


ggplot(data = iris, mapping = aes(x = Petal.Length, fill = Species)) +
  geom_histogram() +
  theme(legend.position = "bottom")

### Separating the plots by group 
  ggplot(data = iris, mapping = aes(x = Petal.Length, fill = Species)) +
    geom_histogram() +
    facet_grid(Species ~.)
  theme(legend.position = "bottom")

  
  
### Density plots
ggplot(data = iris, mapping = aes(x = Petal.Length, fill = Species)) +
    geom_density() +
    theme(legend.position = "bottom")


### Separating the plots by group 
ggplot(data = iris, mapping = aes(x = Petal.Length, fill = Species)) +
  geom_density() +
  facet_grid(Species ~.)
theme(legend.position = "bottom")  


### scatterplot 
ggplot(iris, mapping = aes(Petal.Width, Petal.Length, color = Species))+
  geom_point(size = 3) +
  geom_smooth(method = lm) + 
  geom_density2d(alpha = 0.5) + 
  theme(legend.position = "bottom")
  



### scatterplot 
ggplot(iris, mapping = aes(Petal.Width, Petal.Length, color = Species))+
  geom_point(size = 3) +
  geom_smooth(method = lm) + 
  geom_density2d(alpha = 0.5) + 
  facet_grid(Species~.)
  theme(legend.position = "none")

       
