#Data-Map
Visualizing and finding links in data by geolocation.

**We need to make sure we start up the MongoDB Server before starting the app!**

1. Get Google Maps JS API Key and other collector api keys and set them in `.env`
2. Install Python requirements with `pip install --upgrade -r requirements.txt`


##Writing Collectors

```python
#
# Location: Dictionary with two keys, lat and long
# Radius: Max distance (in meters) away from your location
#
class My_Collector:
    def __init__(self,api_key=None):
        #initiate stuff

    def search(self,location,radius):
        # All the data about a single location
        single_data_point = {
            "location":{
                "lat":1.3,
                "lng":3.7
            },
            # Information tied to an individual location
            "my_collector(i.e twitter)":{
                "name":"John Doe"
                "favorite soda":"Wolf Cola"
                # Other info
            }
        }
        # Return all Locations within radius
        return [list of all data points]
```

###Example Of Returned Data:
```python
[
    {
        "location": {
            "u'lat'": 32.6167174,
            "u'lng'": -116.9975158
        },
        "places": {
            "expires": 1482111454,
            "name": "u'State Street'",
            "place_id": "u'ChIJ_e2p4W9P2YARM4tLdk64ppA'",
            "vicinity": "u'Chula Vista'",
            "photos": "u'./data/lat32_6167174___lng-116_9975158'",
            "types": [
                "u'route'"
            ]
        }
    },
    {
        "location": {
            "u'lat'": 32.6168755,
            "u'lng'": -116.9970153
        },
        "places": {
            "expires": 1482111454,
            "name": "u'Happy San Diego Cleaners'",
            "place_id": "u'ChIJ_____29P2YARl4tMmWhZp4c'",
            "vicinity": "u'Chula Vista'",
            "photos": "u'./data/lat32_6168755___lng-116_9970153'",
            "types": [
                "u'laundry'",
                "u'point_of_interest'",
                "u'establishment'"
            ]
        }
    }
]
```
# Data-Map
