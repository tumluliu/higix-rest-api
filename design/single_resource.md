# Single resource

## dataset
    
## featureset

For each single featureset, users may ask for partial results filtered by either query conditions or fields. But how do users know what fields does the dataset have? Such information should be contained in the default result.

_sample URL:_

http://api.higix.org/v1/featuresets/1234
	
_sample response in JSON format:_
    		    
```javascript
{
    'metadata': {
        'app_id': 1234,
        'name': 'Sample roads',
        'author': 'lliu',
        'org': 'dbrg',
        'srid': '900913',
        'minx': -180.0,
        'miny': -90.0,
        'maxx': 180.0,
        'maxy': 90.0,
        'fields': ['fid', 'name', 'level', 'description', 'geom'],
        'geometry_column': 'geom',
        'feature_count': 9527,
		'shape_point_count': 123456,
        'etc.': '...'
    },
    'preview': 'http://api.higix.org/v1/featuresets/1234/preview.png',
    'data': 'http://api.higix.org/v1/featuresets/1234/data?format=geojson'
}
```

### metadata parameters

* srid, feature_type, feature_count, shape_point_count, minx, miny, maxx, maxy

_sample URL:_
http://api.higix.org/v1/featuresets/1234?metadata=srid,feature_type,feature_count,fields

### data parameters

* format, cols (may be renamed to fields), ignore_geom, bbox, where, order_by, pagination, page (offset), page_size (limit)

_sample URL:_

http://api.higix.org/v1/featuresets/1234/data?format=geojson

http://api.higix.org/v1/featuresets/1234/data?format=protobuf&fields=name,level&offset=2&limit=50

http://api.higix.org/v1/featuresets/1234/data?format=csv&fields=name,length&ignore_geom=true&bbox=-75.0,-35.0,103.5,15.4&pagination=false

## raster

_sample URL:_

http://api.higix.org/v1/rasters/2345

_sample response in JSON format:_

```javascript
{
     'metadata': {
         'app_id': 2345,
         'name': 'Sample raster',
         'author': 'ayang',
         'org': 'dbrg',
         'srid': '4326',
         'minx': -180.0,
         'miny': -90.0,
         'maxx': 180.0,
         'maxy': 90.0,
         'width': 1024,
         'height': 768,
         'max': 8848.8,
         'min': -123.4,
         'nodata': -32768,
         'bands': 3,
         'unique': 'http://api.higix.org/v1/rasters/2345?metadata=unique_values',
         'histogram': 'http://api.higix.org/v1/rasters/2345?metadata=histogram',
         'etc.': '...'
     },
     'preview': 'http://api.higix.org/v1/rasters/2345/preview.png',
     'data': 'http://api.higix.org/v1/rasters/2345/data.tif'
}
```

### metadata parameters

* keys (should be renamed to **metadata**), including min, max, unique, nodata, raw_minx (why raw here?), raw_miny, raw_maxx, raw_maxy, and format (or alt) is necessary
* band_no (may be renamed to band)

_sample URL:_

http://api.higix.org/v1/rasters/2345?metadata=srid,bands,width,height

http://api.higix.org/v1/rasters/2345?metadata=unique&band=1

http://api.higix.org/v1/rasters/2345?metadata=histogram&intervals=10&band=2

### data parameters

* format, bbox, band

_sample URL:_

http://api.higix.org/v1/rasters/2345/data?format=geotiff&band=1,2,3&bbox=-12.3,-23.4,34.5,45.6
 
## st-dataset

