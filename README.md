file-geocoder
==============

Geocodes a file (JSON or CSV). Talks to a Google-style geocoder.

## examples

#### geocode a JSON file, hit http://localhost:8080:

	file-geocoder /
		-f data.json / // the json file
		-a Address,City,State,Zip // list of fields containing the address, in order
		
		

#### geocode a CSV file, hit Google ([read up on their usage limits](https://developers.google.com/maps/documentation/geocoding/#Limits "usage limits")):

	file-geocoder /
		-f data.csv / // the csv file
		- t csv / // the file type - defaults to json
		-a Address,City,State,Zip // list of fields containing the address, in order
		- h maps.googleapis.com // the geocoding host
		- p 80 // the geocoding port

	


## install

	npm install file-geocoder -g
	
