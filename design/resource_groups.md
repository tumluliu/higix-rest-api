# Resource groups

## datasets (originally called data)

    在这个层次上到底应该提供哪些一般性的服务接口，这个需要对现有业务仔细归纳，并且对将来可能的扩展变化进行合理假设之后才能确定。而且这个位置将来一定是会有扩展的，比如增加对新的数据模型的支持，包括网络模型、拓扑模型等等。怎么设计才是最容易扩展的。

### querystring parameters

* box (why not bbox?), geographic bounding box as parts of the filter, in the form of [minx, miny, maxx, maxy]
* spatial_relation: (should be intersect, or contain)

## featuresets

## rasters

## st-datasets

## maps

### querystring parameters

* box (why not bbox?), geographic bounding box as parts of the filter, in the form of [minx, miny, maxx, maxy]

## models

## plugins

## programs/tools

    在plugin和program关系还没完全理清的情况下又乱入了一个名为task的交互式小工具，真是乱上加乱。

## public querystring parameters for these resources

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
