# 8/24 Projecting, Plotting and Labelling Administrative Subdivisions

Map out the administrative subdivisions of a country of your chosing.
I chose Senegal.
```
library(tidyverse)
library(sf)

setwd("/Users/sebas/Documents/Agent Based Modeling")

sen_int  <- read_sf("Data/gadm36_SEN_shp/gadm36_SEN_0.shp")
sen_adm1  <- read_sf("Data/gadm36_SEN_shp/gadm36_SEN_1.shp")
sen_adm2  <- read_sf("Data/gadm36_SEN_shp/gadm36_SEN_2.shp")


ggplot() +
  geom_sf(data = sen_adm2,
          size = .4,
          color = "gray50",
          fill = "gold3",
          alpha = .65) +
  geom_sf(data = sen_adm1,
          size = .65,
          color = "gray50",
          fill = "gold3",
          alpha = .65) +
  geom_sf(data = sen_int,
          size = 2,
          color = "black",
          fill = "blue",
          alpha = 0) +
  geom_sf_text(data = sen_adm2,
               aes(label = NAME_2),
               size = 1,
               color = "black") +
  geom_sf_text(data = sen_adm1,
               aes(label = NAME_1),
               size = 3,
               color = "blue") +
  geom_sf_label(data = sen_int,
                aes(label = NAME_0),
                size = 12,
                color = "black", nudge_x = 0.3,
                nudge_y = .2)
```
![alt text](https://raw.githubusercontent.com/Seabass1000/ABM/master/Senegal.png)

Plot Dakar, Senegal's biggest county, and its districts.
```
new_sf_obj <- sen_adm1 %>%
  filter(NAME_1 == "Dakar")

sen_adm2 %>%
  filter(NAME_1 == "Dakar") %>%
  ggplot() +
  geom_sf(size = 1) +
  geom_sf_text(aes(label = NAME_2),
               size = 4) +
  geom_sf(data = new_sf_obj,
          size = 2,
          alpha = 0) +
  geom_sf_text(data = new_sf_obj,
               aes(label = NAME_1),
               size = 10, nudge_y = .05) +
  xlab("longitude") + ylab("latitude") +
  ggtitle("Dakar", subtitle = "Senegal's most populous region and its departments") +
  theme(plot.title = element_text(hjust = 0.5), 
        plot.subtitle = element_text(hjust = 0.5))
```
Create a larger map of Senegal with two details maps.
![alt text](https://raw.githubusercontent.com/Seabass1000/ABM/master/Dakar.png)

```
plot1 <- ggplot() +
  geom_sf(data = sen_adm1,
          size = 0.5,
          color = "gray50",
          fill = "gold3",
          alpha = 0.5) +
  geom_sf(data = sen_int,
          size = 2.0,
          alpha = 0) +
  
  geom_sf_text(data = sen_adm1,
               aes(label = NAME_1),
               size = 3) +
  xlab("longitude") + ylab("latitude") +
  ggtitle("Senegal", subtitle = "Details A & B") +
  theme(plot.title = element_text(hjust = 0.5), plot.subtitle = element_text(hjust = 0.5),
        panel.background = element_rect(fill = "azure"),
        panel.border = element_rect(fill = NA))

### Create Detail A Map

Dak <- sen_adm1 %>%
  filter(NAME_1 == "Dakar")

plot2 <- sen_adm2 %>%
  filter(NAME_1 == "Dakar") %>%
  ggplot() +
  geom_sf(size = .15) +
  geom_sf_text(aes(label = NAME_2),
               size = 1.75) +
  geom_sf(data = Dak,
          size = .5,
          alpha = 0) +
  geom_sf_text(data = Dak,
               aes(label = NAME_1),
               size = 3.75,
               alpha = .5) +
  xlab("longitude") + ylab("latitude") +
  ggtitle("Detail A", subtitle = "Dakar Region") +
  theme(plot.title = element_text(hjust = 0.5), plot.subtitle = element_text(hjust = 0.5),
        panel.background = element_rect(fill = "azure"),
        panel.border = element_rect(fill = NA))


### Create Detail B Map

east_cnties <- sen_adm1 %>%
  filter(NAME_1 == "Sédhiou" | NAME_1 == "Tambacounda" | NAME_1 == "Thiès")

plot3 <- sen_adm2 %>%
  filter(NAME_1 == "Sédhiou" | NAME_1 == "Tambacounda" | NAME_1 == "Thiès") %>%
  ggplot() +
  geom_sf(size = .15) +
  
  geom_sf_text(aes(label = NAME_2),
               size = 1.75) +
  geom_sf(data = east_cnties,
          size = .5,
          alpha = 0) +
  geom_sf_text(data = east_cnties,
               aes(label = NAME_1),
               size = 3.75,
               alpha = .5) +
  xlab("longitude") + ylab("latitude") +
  ggtitle("Detail B", subtitle = "Sédhiou, Tambacounda & Thiès Regions") +
  theme(plot.title = element_text(hjust = 0.5), plot.subtitle = element_text(hjust = 0.5),
        panel.background = element_rect(fill = "azure"),
        panel.border = element_rect(fill = NA))



ggplot() +
  coord_equal(xlim = c(0, 6.0), ylim = c(0, 4), expand = FALSE) +
  annotation_custom(ggplotGrob(plot1), xmin = 0.0, xmax = 4.0, ymin = 0, 
                    ymax = 4.0) +
  annotation_custom(ggplotGrob(plot3), xmin = 4.0, xmax = 6.0, ymin = 0, 
                    ymax = 2.0) +
  annotation_custom(ggplotGrob(plot2), xmin = 4.0, xmax = 6.0, ymin = 2.0, 
                    ymax = 4.0) +
  theme_void()
```
![alt text](https://raw.githubusercontent.com/Seabass1000/ABM/master/details.png)

