file-geocoder
==============

Geocodes a file (JSON or CSV). Talks to a Google-style geocoder.

## Examples

#### Geocode a JSON file, hit http://localhost:8080 ([how to setup a local geocoder](http://www.datasciencetoolkit.org/ "Data Science Tookit")):

	file-geocoder /
		-f data.json / // the json file
		-a Address,City,State,Zip // list of fields containing the address, in order
		
		

#### Geocode a CSV file, hit Google, throttle geocoding requests to 1 per second ([read up on their usage limits](https://developers.google.com/maps/documentation/geocoding/#Limits "usage limits")):

	file-geocoder /
		-f data.csv / // the csv file
		- t csv / // the file type - defaults to json
		-a Address,City,State,Zip // list of fields containing the address, in order
		- h maps.googleapis.com // the geocoding host
		- p 80 // the geocoding port
		- s 1 // time (in seconds) to throttle the geocoding requests



#### Your laptop battery died before the geocoder finished. No problem. file-geocoder stores its work on a db file. Let's resume the geocoding: 
	
	file-geocoder /
		- d data.db // the database
		-a Address,City,State,Zip // list of fields containing the address, in order


## install

	npm install file-geocoder -g
	
