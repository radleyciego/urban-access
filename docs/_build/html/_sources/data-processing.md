# Data Processing

### Load GTFS data into an UrbanAccess transit data object

```
validation = True
verbose = True
# bbox for New York City
bbox = (-74.25909,40.477399,-73.700181,40.916178)
remove_stops_outsidebbox = True
append_definitions = True

loaded_feeds = ua.gtfs.load.gtfsfeed_to_df(gtfsfeed_path='/Users/radleyciego/data/gtfsfeed_text/',
                                           validation=validation,
                                           verbose=verbose,
                                           bbox=bbox,
                                           remove_stops_outsidebbox=remove_stops_outsidebbox,
                                           append_definitions=append_definitions)
```

#### The transit data object
```
The output is a global `urbanaccess_gtfs_df` object that can be accessed with the specified variable `loaded_feeds`. This object holds all the individual GTFS feed files aggregated together with each GTFS feed file type in separate Pandas DataFrames to represent all the loaded transit feeds in a metropolitan area. 
```

```
loaded_feeds.stops.head()
```

```
loaded_feeds.stops.unique_agency_id.unique()
```

```
loaded_feeds.stops.plot(kind='scatter', x='stop_lon', y='stop_lat', s=0.1)
```

Describe the importance of data preprocessing in geospatial data engineering.
Highlight techniques for cleaning, transforming, and normalizing geospatial data.