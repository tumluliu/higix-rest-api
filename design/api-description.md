# Designing plan of RESTful Web API for higix

## Resource list

### First-class app resources 
#### Resource groups
* featuresets
* rasters
* datasets (originally called data)
** querystring parameters
*** box (why not bbox?), geographic bounding box as parts of the filter, in the form of [minx, miny, maxx, maxy]
*** spatial_relation: (should be intersect, or contain)
* maps
** querystring parameters
*** box (why not bbox?), geographic bounding box as parts of the filter, in the form of [minx, miny, maxx, maxy]
* models
* plugins
* st-datasets
* programs/tools
* public querystring parameters for these resources
** user_id, TODO: this should be substituted by unified user identity (e.g. @auth.login_required in Flask.RESTful)
** name_keywords, keywords for full-text search
** catalog_id, catalogs as parts of the filter
** tags, tags as parts of the filter
** app_id_in_page: ?
** app_id
** share
** keys (may be renamed to fields)
** page (may be renamed to offset, default to 0)
** page_size (may be renamed to limit, default to 10)
** order_by
** flow_id
#### Single resource
* dataset
* featureset
** querystring parameters
*** cols (may be renamed to fields), where, order_by, page, page_size
*** srid, feature_type, feature_count, shape_point_count, minx, miny, maxx, maxy
** response structure
*** JSON
*** default

* raster
** querystring parameters
*** keys (may be renamed to fields), including min, max, unique, nodata, raw_minx (why raw here?), raw_miny, raw_maxx, raw_maxy, and format (or alt) is necessary
*** band_no (may be renamed to band)
** response structure
*** JSON
{'metadata': {...}, 'preview': 'An http link to the thumbnail image', 'data': {'download': 'An http link to the download position', 'format': 'GeoTiff'}}
*** Default 
* st-dataset


### Affilicated resources

* catalogs
** methods: POST, DELETE, PUT, GET
* tags
** methods: POST, DELETE, PUT, GET
* users
** methods: POST, DELETE, PUT, GET
* authorities (relations between roles and apps)
** methods: POST, DELETE, PUT, GET
* roles
** methods: POST, DELETE, PUT, GET
* tasks (小工具), may be renamed to ...
** what the hell does this mean? how to define the relationship between tasks, tools, algorithms and plugins?
** methods: POST
* symbols
** methods: POST, DELETE, GET
* tmpfiles
** methods: POST


### Design of resource URIs

### Operations on the resources

### Query strings on the resources for GET method

### Data structure (in JSON) of the requests and responses

## Authentication issue

### Use OAuth instead of api key

## Test suite based on frisbyjs

## Documentation

### Write doc with Sphinx as before

### Build doc with readthedocs.org

## Implementation based on, perhaps Flask-restful
