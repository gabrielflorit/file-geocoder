file-geocoder
==============

    Geocode a file (JSON or CSV). Talks to a Google-style geocoder.
    Usage: file-geocoder

	Options:
	  -f, --file      JSON or CSV file to be geocoded                                     [required]
	  -a, --fields    comma-separated list of address fields, in order                    [required]
	  -t, --type      whether the file is JSON or CSV                                     [default: "json"]
	  -d, --database  database containing records. If specified, will ignore file input.  [default: null]
	  -h, --host      geocoder host                                                       [default: "localhost"]
	  -p, --port      geocoder port                                                       [default: 8080]
	  -s, --throttle  time (in seconds) to throttle the geocoding requests                [default: 0]
