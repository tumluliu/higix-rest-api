# Designing plan of RESTful Web API for higix

关于本次重新设计的基本原则，应该从API的用户，也就是Web app developers的角度出去去考虑。他们希望如何最自然流畅的去取用资源，如何舒服的操纵资源，如何能从资源的一种表达方式顺畅的跳转到另一种表达方式，如何从一个资源跳转到另一个资源，等等。如果能有效的解决了这些问题，那么这个API才算是能用的。

## Resource list

### First-class app resources 

#### Resource groups

* datasets (originally called data)
在这个层次上到底应该提供哪些一般性的服务接口，这个需要对现有业务仔细归纳，并且对将来可能的扩展变化进行合理假设之后才能确定。而且这个位置将来一定是会有扩展的，比如增加对新的数据模型的支持，包括网络模型、拓扑模型等等。怎么设计才是最容易扩展的。
	* querystring parameters
		* box (why not bbox?), geographic bounding box as parts of the filter, in the form of [minx, miny, maxx, maxy]
		* spatial_relation: (should be intersect, or contain)
* featuresets
* rasters
* st-datasets
* maps
	* querystring parameters
		* box (why not bbox?), geographic bounding box as parts of the filter, in the form of [minx, miny, maxx, maxy]
* models
* plugins
* programs/tools
在plugin和program关系还没完全理清的情况下又乱入了一个名为task的交互式小工具，真是乱上加乱。
* public querystring parameters for these resources
	* user_id, TODO: this should be substituted by unified user identity (e.g. @auth.login_required in Flask.RESTful)
	* name_keywords, keywords for full-text search
	* catalog_id, catalogs as parts of the filter
	* tags, tags as parts of the filter
	* app_id_in_page: ?
	* app_id
	* share
	* keys (may be renamed to fields)
	* page (may be renamed to offset, default to 0)
	* page_size (may be renamed to limit, default to 10)
	* order_by
	* flow_id
	
#### Single resource
* dataset
* featureset
    * querystring parameters
        * cols (may be renamed to fields), where, order_by, page, page_size
		* srid, feature_type, feature_count, shape_point_count, minx, miny, maxx, maxy
	* response structure
		* JSON
		* default

* raster
	* querystring parameters
		* keys (may be renamed to fields), including min, max, unique, nodata, raw_minx (why raw here?), raw_miny, raw_maxx, raw_maxy, and format (or alt) is necessary
		* band_no (may be renamed to band)
	* response structure
	* JSON
{'metadata': {...}, 'preview': 'An http link to the thumbnail image', 'data': {'download': 'An http link to the download position', 'format': 'GeoTiff'}}
	* Default 
* st-dataset


### Affilicated resources

* catalogs
	* methods: POST, DELETE, PUT, GET
* tags
	* methods: POST, DELETE, PUT, GET
* users
	* methods: POST, DELETE, PUT, GET
* authorities (relations between roles and apps)
	* methods: POST, DELETE, PUT, GET
* roles
	* methods: POST, DELETE, PUT, GET
* tasks (小工具), may be renamed to ...
	* what the hell does this mean? how to define the relationship between tasks, tools, algorithms and plugins?
	* methods: POST
* symbols
	* methods: POST, DELETE, GET
* tmpfiles
	* methods: POST


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
