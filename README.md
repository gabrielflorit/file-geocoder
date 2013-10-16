file-geocoder
==============

Geocodes a file (JSON or CSV). Requires a Google-style geocoder.

## Example

Given a CSV,

```
address,              city,       state, zip
135 Morrisey Blvd,    Boston,     MA,    02125
1150 15th Street NW,  Washington, DC,    20071
242 West 41st Street, New York,   NY,    10036 
```

file-geocoder adds several geocoding fields ([what's the deal with GeocodeAdminAreaLevel1?](https://developers.google.com/maps/documentation/geocoding/#Types "Address Component Types")):

```
address,              city,       state, zip,   GeocodeLat, GeocodeLng, GeocodeStatus, GeocodeLocality, GeocodeAdminAreaLevel1, GeocodeCountry, GeocodeAddress
135 Morrisey Blvd,    Boston,     MA,    02125, 42.293929,  -71.047218, ROOFTOP,       Boston,          MA,                     United States,  "135 Morrisey Blvd, Boston, MA, 02125"
1150 15th Street NW,  Washington, DC,    20071, 38.904711,  -77.034647, ROOFTOP,       Washington,      DC,                     United States,  "1150 15th Street NW, Washington, DC, 20071"
242 West 41st Street, New York,   NY,    10036, 40.755819,  -73.988402, ROOFTOP,       New York,        NY,                     United States,  "242 West 41st Street, New York, NY, 10036"
```



## Usage examples

#### Geocode a JSON file, hit http://localhost:8080 ([how to setup a local geocoder](http://www.datasciencetoolkit.org/developerdocs#setup "Data Science Tookit")):
```sh
file-geocoder \
	-f myaddresses.json \
	-a address,city,state,zip # list of fields containing the address, in order
```		
		

#### Geocode a CSV file, hit Google, throttle geocoding requests to 1 per second ([read up on their usage limits](https://developers.google.com/maps/documentation/geocoding/#Limits "usage limits")):
```sh
file-geocoder \
	-f myaddresses.csv \
	-a address,city,state,zip \ # list of fields containing the address, in order
	-h maps.googleapis.com \ # geocoding host
	-p 80 \ # geocoding port
	-s 1 # time (in seconds) to throttle the geocoding requests
```


#### Your laptop battery died before the geocoder finished. No problem. file-geocoder stores its work on a .db file. Let's resume the geocoding: 
```sh
file-geocoder \
	-d myaddresses.db \ # database
	-a address,city,state,zip # list of fields containing the address, in order
```


## Progress bar!

![Progress bar!](https://pbs.twimg.com/media/BWp_jTtCAAATBGV.png)

## Install

	npm install file-geocoder -g
