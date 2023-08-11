# Data Collection and Integration

### Libraries

```
import matplotlib

import pandas as pd
import cartopy.crs as ccrs
import cartopy
import matplotlib.pyplot as plt
import pandana as pdna
import osmnet as osm
from pandana.loaders import osm
import time
import pyepsg
import h5py

import urbanaccess as ua
from urbanaccess.config import settings
from urbanaccess.gtfsfeeds import feeds
from urbanaccess import gtfsfeeds
from urbanaccess.gtfs.gtfsfeeds_dataframe import gtfsfeeds_dfs
from urbanaccess.network import ua_network, load_network

from simpledbf import Dbf5

%matplotlib inline
```

### The Feeds Object
The GTFS `feeds` object is a global `urbanaccess_gtfsfeeds` object that allows you to save and manage information needed to download multiple GTFS feeds. This object is a dictionary of the names of GTFS feeds or agencies and the URLs to use to download the corresponding feeds.

```
feeds.to_dict()
```

```
feeds.add_feed(add_dict={'MTA New York City Transit Authority': 'http://web.mta.info/developers/data/nyct/subway/google_transit.zip'})
feeds.add_feed(add_dict={'MTA Bronx Transit Bus': 'http://web.mta.info/developers/data/nyct/bus/google_transit_bronx.zip'})
feeds.add_feed(add_dict={'MTA Brooklyn Transit Bus': 'http://web.mta.info/developers/data/nyct/bus/google_transit_brooklyn.zip'})
feeds.add_feed(add_dict={'MTA Manhattan Transit Bus': 'http://web.mta.info/developers/data/nyct/bus/google_transit_manhattan.zip'})
feeds.add_feed(add_dict={'MTA Queens Transit Bus': 'http://web.mta.info/developers/data/nyct/bus/google_transit_queens.zip'})
feeds.add_feed(add_dict={'MTA Staten Island Transit Bus': 'http://web.mta.info/developers/data/nyct/bus/google_tran
```
### Downloading GTFS Data

Use the download function to download all the feeds in your feeds object at once. If no parameters are specified the existing feeds object will be used to acquire the data.

By default, your data will be downloaded into the directory of this notebook in the folder: `data`

```
# List the GTFS feeds in feed object ready to download
feeds.to_dict()
```

```
gtfsfeeds.download()
```

### Downloading OpenStreetMap pedestrian street network data
```
# Download OpenStreetMap pedestrian street network data using New York City bounding box
nodes, edges = ua.osm.load.ua_network_from_bbox(bbox=(-74.25909,40.477399,-73.700181,40.916178),
                                                remove_lcn=True) 
```