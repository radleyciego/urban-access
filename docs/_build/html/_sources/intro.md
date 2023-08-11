# Measuring Accessibility: Integrated NYC MTA Transit and Pedestrian Network Times using UrbanAccess

The distribution of places of employment and resulting commuting times have emerged as the single strongest factor in upward mobility, according to an ongoing Harvard University study (Chetty and Hendren, 2015). There is a significant causal effect between the neighborhood in which residents live and their prospects for upward mobility. Residents with longer commute times to work are less likely to experience economic mobility. 

This study seeks to explore this hypothesis within the context of New York City; a metropolis often considered the financial capital of the world with an abundance of opportunity yet plagued with income inequality. Through a network analysis whereby pedestrian and transit networks are integrated, this study assesses accessibility to places of employment on the block group scale utilizing UrbanAccess, a Python tool for computing GTFS transit and OSM pedestrian networks for accessibility analysis (Blanchard, Waddell, 2017). Resulting geovisualizations provide insight into which boroughs and neighborhoods are high and low opportunity areas, and where policy to support economic mobility would be most beneficial. 

This notebook details the main functionality of UrbanAccess with examples using MTA GTFS data, Census block, and OpenStreetMap (OSM) pedestrian network data to create an integrated transit and pedestrian network for New York, NY for use in Pandana network accessibility queries.

```{tableofcontents}
```
