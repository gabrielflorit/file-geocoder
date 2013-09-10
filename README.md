mongo-geocoder
==============

Geocode a MongoDB collection. Talks to a Google-style geocoder.
Usage: mongo-geocoder

Options:
  -d, --database    the MongoDB database                                [required]
  -c, --collection  the MongoDB collection                              [required]
  -f, --fields      a comma-separated list of address fields, in order  [required]
  -h, --host        the geocoder host                                   [default: "localhost"]
  -p, --port        the geocoder port                                   [default: 8080]
  -s, --connection  the MongoDB connection string                       [default: "mongodb://127.0.0.1:27017/"]