# ![LOGO](logo.png) opendatasoft **flow**ground Connector

## Description

A generated **flow**ground connector for the opendatasoft API (version 2.1.0).

Generated from: https://api.apis.guru/v2/specs/opendatasoft.com/2.1.0/swagger.json<br/>
Generated at: 2019-05-07T17:43:25+03:00

## API Description



## Authorization

Supported authorization schemes:
- API Key- Basic Authentication

## Actions

### API entry point<br/>
> <br/>
> Provides links for:<br/>
> * catalog, your domain's list of datasets<br/>
> * opendatasoft, all datasets on the OpenDataSoft network

*Tags:* `root` `ods`

### List of all pages from this portal.

*Tags:* `page` `ods`

### A single page's metadata from this portal

*Tags:* `page` `ods`

#### Input Parameters
* `slug` - _required_ - Page slug.


### Source entry points<br/>
> <br/>
> Provides links for the source's datasets and metadata.

*Tags:* `catalog` `ods`

#### Input Parameters
* `source` - _required_ - Each source represents a different catalog of datasets you'll be able to query.

There are 2 sources available:

* catalog: the catalog of datasets on your portal
* opendatasoft: OpenDataSoft's repository of public datasets, also available at
  [data.opendatasoft.com](https://data.opendatasoft.com/page/home/)

    Possible values: catalog, opendatasoft, monitoring.

### Compute aggregations from catalog and return a list of each aggregate indexed by their names.

*Tags:* `catalog` `aggregations` `ods`

#### Input Parameters
* `source` - _required_ - Each source represents a different catalog of datasets you'll be able to query.

There are 2 sources available:

* catalog: the catalog of datasets on your portal
* opendatasoft: OpenDataSoft's repository of public datasets, also available at
  [data.opendatasoft.com](https://data.opendatasoft.com/page/home/)

    Possible values: catalog, opendatasoft, monitoring.
* `select` - _optional_ - A select expression can be used to add, remove or change fields to return.
An expression can be:
  - a wildcard ('*'): return all fields
  - a field name: return only this field
  - an include/exclude function. Include (resp exclude) all field matching include/exclude expression. This expression can contain wildcard. For example: include(spa*) will return all fields begining with 'spa'
  - a complex expression: return the result of this expression. A label can be set for this expression, in that case, field will be named with this label. For instance: 'size * 2 as bigger_size' will return a new field named bigger_size and containing the double of size field value.

* `group_by` - _optional_ - A group by expression defines a grouping function for an aggregation.
It can be:
 - a field name: group result by each value of this field
 - a range function: group result by range
 - a date function: group result by date
It is possible to specify a custom name with the 'as name' notation. For instance: group_by='city_field as city'.

* `where` - _optional_ - An array of filters.

A filter is a text expression performing a simple full-text search that can also include logical operations
(NOT, AND, OR...) as well as lots of other functions, thus performing more complex and more precise searches.
See [the query language reference](https://docs.opendatasoft.com/api/explore/v2.html#where-clause) for more details.


### List of available datasets, each with their endpoints, paginated.<br/>
> <br/>
> Links provided:<br/>
> * previous page<br/>
> * next page<br/>
> * last page<br/>
> * first page

*Tags:* `catalog` `ods`

#### Input Parameters
* `source` - _required_ - Each source represents a different catalog of datasets you'll be able to query.

There are 2 sources available:

* catalog: the catalog of datasets on your portal
* opendatasoft: OpenDataSoft's repository of public datasets, also available at
  [data.opendatasoft.com](https://data.opendatasoft.com/page/home/)

    Possible values: catalog, opendatasoft, monitoring.
* `where` - _optional_ - An array of filters.

A filter is a text expression performing a simple full-text search that can also include logical operations
(NOT, AND, OR...) as well as lots of other functions, thus performing more complex and more precise searches.
See [the query language reference](https://docs.opendatasoft.com/api/explore/v2.html#where-clause) for more details.

* `search` - _optional_ - An array of full text search.

A full text search performs a prefixed text search for each provided terms in all visible fields of a catalog/dataset.

* `rows` - _optional_ - Number of items to return.

To use in conjonction with start to implement pagination.

Rows maximum value is 100. To retrive more data use export entry points.

* `start` - _optional_ - Index of the first item to return (starting at 0).

To use in conjonction with rows to implement pagination.

* `sort` - _optional_ - A list of field names, each possibly prefixed with a minus (-).

May also be 'random(seed)', where seed can be omitted but if specified must be an int. This allows to keep
relative ordering during pagination.

Sorts results according to the specified fields' values. By default, the sort is ascending (from the highest
value to the smallest value). A minus sign ('-') may be used to perform a descending sort. Sorting is only
available on numeric fields (int, double, date and datetime) and on text fields which have the sortable
annotation.

* `pretty` - _optional_ - Activate pretty print
* `timezone` - _optional_ - Set timezone for datetime fields
* `include_app_metas` - _optional_ - Explicitely request application metas for each datasets.


### List of available endpoints for the specified dataset, with metadata and endpoints.<br/>
> <br/>
> Will provide links for:<br/>
> * the attachments endpoint<br/>
> * the files endpoint<br/>
> * the records endpoint<br/>
> * the catalog endpoint

*Tags:* `dataset` `ods`

#### Input Parameters
* `source` - _required_ - Each source represents a different catalog of datasets you'll be able to query.

There are 2 sources available:

* catalog: the catalog of datasets on your portal
* opendatasoft: OpenDataSoft's repository of public datasets, also available at
  [data.opendatasoft.com](https://data.opendatasoft.com/page/home/)

    Possible values: catalog, opendatasoft, monitoring.
* `dataset_id` - _required_ - Dataset identifier.

Can be found in the "information" tab of the dataset page.

* `pretty` - _optional_ - Activate pretty print
* `timezone` - _optional_ - Set timezone for datetime fields
* `select` - _optional_ - A select expression can be used to add, remove or change fields to return.
An expression can be:
  - a wildcard ('*'): return all fields
  - a field name: return only this field
  - an include/exclude function. Include (resp exclude) all field matching include/exclude expression. This expression can contain wildcard. For example: include(spa*) will return all fields begining with 'spa'
  - a complex expression: return the result of this expression. A label can be set for this expression, in that case, field will be named with this label. For instance: 'size * 2 as bigger_size' will return a new field named bigger_size and containing the double of size field value.

* `include_app_metas` - _optional_ - Explicitely request application metas for each datasets.


### Compute aggregations from dataset records and return a list of each aggregate indexed by their names.

*Tags:* `dataset` `aggregations` `ods`

#### Input Parameters
* `source` - _required_ - Each source represents a different catalog of datasets you'll be able to query.

There are 2 sources available:

* catalog: the catalog of datasets on your portal
* opendatasoft: OpenDataSoft's repository of public datasets, also available at
  [data.opendatasoft.com](https://data.opendatasoft.com/page/home/)

    Possible values: catalog, opendatasoft, monitoring.
* `dataset_id` - _required_ - Dataset identifier.

Can be found in the "information" tab of the dataset page.

* `select` - _optional_ - A select expression can be used to add, remove or change fields to return.
An expression can be:
  - a wildcard ('*'): return all fields
  - a field name: return only this field
  - an include/exclude function. Include (resp exclude) all field matching include/exclude expression. This expression can contain wildcard. For example: include(spa*) will return all fields begining with 'spa'
  - a complex expression: return the result of this expression. A label can be set for this expression, in that case, field will be named with this label. For instance: 'size * 2 as bigger_size' will return a new field named bigger_size and containing the double of size field value.

* `group_by` - _optional_ - A group by expression defines a grouping function for an aggregation.
It can be:
 - a field name: group result by each value of this field
 - a range function: group result by range
 - a date function: group result by date
It is possible to specify a custom name with the 'as name' notation. For instance: group_by='city_field as city'.

* `where` - _optional_ - An array of filters.

A filter is a text expression performing a simple full-text search that can also include logical operations
(NOT, AND, OR...) as well as lots of other functions, thus performing more complex and more precise searches.
See [the query language reference](https://docs.opendatasoft.com/api/explore/v2.html#where-clause) for more details.


### Get list of all available attachments

*Tags:* `dataset` `ods`

#### Input Parameters
* `source` - _required_ - Each source represents a different catalog of datasets you'll be able to query.

There are 2 sources available:

* catalog: the catalog of datasets on your portal
* opendatasoft: OpenDataSoft's repository of public datasets, also available at
  [data.opendatasoft.com](https://data.opendatasoft.com/page/home/)

    Possible values: catalog, opendatasoft, monitoring.
* `dataset_id` - _required_ - Dataset identifier.

Can be found in the "information" tab of the dataset page.


### Download attachment

*Tags:* `dataset` `ods`

#### Input Parameters
* `source` - _required_ - Each source represents a different catalog of datasets you'll be able to query.

There are 2 sources available:

* catalog: the catalog of datasets on your portal
* opendatasoft: OpenDataSoft's repository of public datasets, also available at
  [data.opendatasoft.com](https://data.opendatasoft.com/page/home/)

    Possible values: catalog, opendatasoft, monitoring.
* `dataset_id` - _required_ - Dataset identifier.

Can be found in the "information" tab of the dataset page.

* `attachment_id` - _required_

### Export dataset in CSV format

*Tags:* `export dataset` `ods`

#### Input Parameters
* `source` - _required_ - Each source represents a different catalog of datasets you'll be able to query.

There are 2 sources available:

* catalog: the catalog of datasets on your portal
* opendatasoft: OpenDataSoft's repository of public datasets, also available at
  [data.opendatasoft.com](https://data.opendatasoft.com/page/home/)

    Possible values: catalog, opendatasoft, monitoring.
* `dataset_id` - _required_ - Dataset identifier.

Can be found in the "information" tab of the dataset page.

* `where` - _optional_ - An array of filters.

A filter is a text expression performing a simple full-text search that can also include logical operations
(NOT, AND, OR...) as well as lots of other functions, thus performing more complex and more precise searches.
See [the query language reference](https://docs.opendatasoft.com/api/explore/v2.html#where-clause) for more details.

* `select` - _optional_ - A select expression can be used to add, remove or change fields to return.
An expression can be:
  - a wildcard ('*'): return all fields
  - a field name: return only this field
  - an include/exclude function. Include (resp exclude) all field matching include/exclude expression. This expression can contain wildcard. For example: include(spa*) will return all fields begining with 'spa'
  - a complex expression: return the result of this expression. A label can be set for this expression, in that case, field will be named with this label. For instance: 'size * 2 as bigger_size' will return a new field named bigger_size and containing the double of size field value.

* `rows` - _optional_ - Number of items to return in export.

Use -1 to retrieve all records

* `start` - _optional_ - Index of the first item to return (starting at 0).

To use in conjonction with rows to implement pagination.

* `timezone` - _optional_ - Set timezone for datetime fields
* `delimiter` - _optional_ - Provide a different delimiter (default ',').
    Possible values: ,, ;, |.

### Export dataset in GEOJSON format

*Tags:* `export dataset` `ods`

#### Input Parameters
* `source` - _required_ - Each source represents a different catalog of datasets you'll be able to query.

There are 2 sources available:

* catalog: the catalog of datasets on your portal
* opendatasoft: OpenDataSoft's repository of public datasets, also available at
  [data.opendatasoft.com](https://data.opendatasoft.com/page/home/)

    Possible values: catalog, opendatasoft, monitoring.
* `dataset_id` - _required_ - Dataset identifier.

Can be found in the "information" tab of the dataset page.

* `where` - _optional_ - An array of filters.

A filter is a text expression performing a simple full-text search that can also include logical operations
(NOT, AND, OR...) as well as lots of other functions, thus performing more complex and more precise searches.
See [the query language reference](https://docs.opendatasoft.com/api/explore/v2.html#where-clause) for more details.

* `search` - _optional_ - An array of full text search.

A full text search performs a prefixed text search for each provided terms in all visible fields of a catalog/dataset.

* `rows` - _optional_ - Number of items to return in export.

Use -1 to retrieve all records

* `start` - _optional_ - Index of the first item to return (starting at 0).

To use in conjonction with rows to implement pagination.

* `timezone` - _optional_ - Set timezone for datetime fields
* `pretty` - _optional_ - Activate pretty print

### Export dataset in ICAL format

*Tags:* `export dataset` `ods`

#### Input Parameters
* `source` - _required_ - Each source represents a different catalog of datasets you'll be able to query.

There are 2 sources available:

* catalog: the catalog of datasets on your portal
* opendatasoft: OpenDataSoft's repository of public datasets, also available at
  [data.opendatasoft.com](https://data.opendatasoft.com/page/home/)

    Possible values: catalog, opendatasoft, monitoring.
* `dataset_id` - _required_ - Dataset identifier.

Can be found in the "information" tab of the dataset page.

* `where` - _optional_ - An array of filters.

A filter is a text expression performing a simple full-text search that can also include logical operations
(NOT, AND, OR...) as well as lots of other functions, thus performing more complex and more precise searches.
See [the query language reference](https://docs.opendatasoft.com/api/explore/v2.html#where-clause) for more details.

* `search` - _optional_ - An array of full text search.

A full text search performs a prefixed text search for each provided terms in all visible fields of a catalog/dataset.

* `rows` - _optional_ - Number of items to return in export.

Use -1 to retrieve all records

* `start` - _optional_ - Index of the first item to return (starting at 0).

To use in conjonction with rows to implement pagination.

* `timezone` - _optional_ - Set timezone for datetime fields

### Export dataset in JSON format

*Tags:* `export dataset` `ods`

#### Input Parameters
* `source` - _required_ - Each source represents a different catalog of datasets you'll be able to query.

There are 2 sources available:

* catalog: the catalog of datasets on your portal
* opendatasoft: OpenDataSoft's repository of public datasets, also available at
  [data.opendatasoft.com](https://data.opendatasoft.com/page/home/)

    Possible values: catalog, opendatasoft, monitoring.
* `dataset_id` - _required_ - Dataset identifier.

Can be found in the "information" tab of the dataset page.

* `where` - _optional_ - An array of filters.

A filter is a text expression performing a simple full-text search that can also include logical operations
(NOT, AND, OR...) as well as lots of other functions, thus performing more complex and more precise searches.
See [the query language reference](https://docs.opendatasoft.com/api/explore/v2.html#where-clause) for more details.

* `search` - _optional_ - An array of full text search.

A full text search performs a prefixed text search for each provided terms in all visible fields of a catalog/dataset.

* `rows` - _optional_ - Number of items to return in export.

Use -1 to retrieve all records

* `start` - _optional_ - Index of the first item to return (starting at 0).

To use in conjonction with rows to implement pagination.

* `pretty` - _optional_ - Activate pretty print
* `timezone` - _optional_ - Set timezone for datetime fields

### Export dataset in OV2 format

*Tags:* `export dataset` `ods`

#### Input Parameters
* `source` - _required_ - Each source represents a different catalog of datasets you'll be able to query.

There are 2 sources available:

* catalog: the catalog of datasets on your portal
* opendatasoft: OpenDataSoft's repository of public datasets, also available at
  [data.opendatasoft.com](https://data.opendatasoft.com/page/home/)

    Possible values: catalog, opendatasoft, monitoring.
* `dataset_id` - _required_ - Dataset identifier.

Can be found in the "information" tab of the dataset page.

* `where` - _optional_ - An array of filters.

A filter is a text expression performing a simple full-text search that can also include logical operations
(NOT, AND, OR...) as well as lots of other functions, thus performing more complex and more precise searches.
See [the query language reference](https://docs.opendatasoft.com/api/explore/v2.html#where-clause) for more details.

* `search` - _optional_ - An array of full text search.

A full text search performs a prefixed text search for each provided terms in all visible fields of a catalog/dataset.

* `rows` - _optional_ - Number of items to return in export.

Use -1 to retrieve all records

* `start` - _optional_ - Index of the first item to return (starting at 0).

To use in conjonction with rows to implement pagination.

* `timezone` - _optional_ - Set timezone for datetime fields

### Export dataset in Esri shapefile (shp) format

*Tags:* `export dataset` `ods`

#### Input Parameters
* `source` - _required_ - Each source represents a different catalog of datasets you'll be able to query.

There are 2 sources available:

* catalog: the catalog of datasets on your portal
* opendatasoft: OpenDataSoft's repository of public datasets, also available at
  [data.opendatasoft.com](https://data.opendatasoft.com/page/home/)

    Possible values: catalog, opendatasoft, monitoring.
* `dataset_id` - _required_ - Dataset identifier.

Can be found in the "information" tab of the dataset page.

* `where` - _optional_ - An array of filters.

A filter is a text expression performing a simple full-text search that can also include logical operations
(NOT, AND, OR...) as well as lots of other functions, thus performing more complex and more precise searches.
See [the query language reference](https://docs.opendatasoft.com/api/explore/v2.html#where-clause) for more details.

* `search` - _optional_ - An array of full text search.

A full text search performs a prefixed text search for each provided terms in all visible fields of a catalog/dataset.

* `rows` - _optional_ - Number of items to return in export.

Use -1 to retrieve all records

* `start` - _optional_ - Index of the first item to return (starting at 0).

To use in conjonction with rows to implement pagination.

* `timezone` - _optional_ - Set timezone for datetime fields

### Export dataset in XLS (Excel) format

*Tags:* `export dataset` `ods`

#### Input Parameters
* `source` - _required_ - Each source represents a different catalog of datasets you'll be able to query.

There are 2 sources available:

* catalog: the catalog of datasets on your portal
* opendatasoft: OpenDataSoft's repository of public datasets, also available at
  [data.opendatasoft.com](https://data.opendatasoft.com/page/home/)

    Possible values: catalog, opendatasoft, monitoring.
* `dataset_id` - _required_ - Dataset identifier.

Can be found in the "information" tab of the dataset page.

* `where` - _optional_ - An array of filters.

A filter is a text expression performing a simple full-text search that can also include logical operations
(NOT, AND, OR...) as well as lots of other functions, thus performing more complex and more precise searches.
See [the query language reference](https://docs.opendatasoft.com/api/explore/v2.html#where-clause) for more details.

* `search` - _optional_ - An array of full text search.

A full text search performs a prefixed text search for each provided terms in all visible fields of a catalog/dataset.

* `rows` - _optional_ - Number of items to return in export.

Use -1 to retrieve all records

* `start` - _optional_ - Index of the first item to return (starting at 0).

To use in conjonction with rows to implement pagination.

* `timezone` - _optional_ - Set timezone for datetime fields

### Create new feedback entry.

*Tags:* `dataset` `ods`

#### Input Parameters
* `source` - _required_ - Each source represents a different catalog of datasets you'll be able to query.

There are 2 sources available:

* catalog: the catalog of datasets on your portal
* opendatasoft: OpenDataSoft's repository of public datasets, also available at
  [data.opendatasoft.com](https://data.opendatasoft.com/page/home/)

    Possible values: catalog, opendatasoft, monitoring.
* `dataset_id` - _required_ - Dataset identifier.

Can be found in the "information" tab of the dataset page.


### Download file

*Tags:* `dataset` `ods`

#### Input Parameters
* `source` - _required_ - Each source represents a different catalog of datasets you'll be able to query.

There are 2 sources available:

* catalog: the catalog of datasets on your portal
* opendatasoft: OpenDataSoft's repository of public datasets, also available at
  [data.opendatasoft.com](https://data.opendatasoft.com/page/home/)

    Possible values: catalog, opendatasoft, monitoring.
* `dataset_id` - _required_ - Dataset identifier.

Can be found in the "information" tab of the dataset page.

* `file_id` - _required_
* `thumbnail_size` - _optional_ - Set the size of the thumbnail representing the resource (attachment, image or file)

### Search dataset's records.

*Tags:* `dataset` `ods`

#### Input Parameters
* `source` - _required_ - Each source represents a different catalog of datasets you'll be able to query.

There are 2 sources available:

* catalog: the catalog of datasets on your portal
* opendatasoft: OpenDataSoft's repository of public datasets, also available at
  [data.opendatasoft.com](https://data.opendatasoft.com/page/home/)

    Possible values: catalog, opendatasoft, monitoring.
* `dataset_id` - _required_ - Dataset identifier.

Can be found in the "information" tab of the dataset page.

* `where` - _optional_ - An array of filters.

A filter is a text expression performing a simple full-text search that can also include logical operations
(NOT, AND, OR...) as well as lots of other functions, thus performing more complex and more precise searches.
See [the query language reference](https://docs.opendatasoft.com/api/explore/v2.html#where-clause) for more details.

* `search` - _optional_ - An array of full text search.

A full text search performs a prefixed text search for each provided terms in all visible fields of a catalog/dataset.

* `rows` - _optional_ - Number of items to return.

To use in conjonction with start to implement pagination.

Rows maximum value is 100. To retrive more data use export entry points.

* `start` - _optional_ - Index of the first item to return (starting at 0).

To use in conjonction with rows to implement pagination.

* `sort` - _optional_ - A list of field names, each possibly prefixed with a minus (-).

May also be 'random(seed)', where seed can be omitted but if specified must be an int. This allows to keep
relative ordering during pagination.

Sorts results according to the specified fields' values. By default, the sort is ascending (from the highest
value to the smallest value). A minus sign ('-') may be used to perform a descending sort. Sorting is only
available on numeric fields (int, double, date and datetime) and on text fields which have the sortable
annotation.

* `select` - _optional_ - A select expression can be used to add, remove or change fields to return.
An expression can be:
  - a wildcard ('*'): return all fields
  - a field name: return only this field
  - an include/exclude function. Include (resp exclude) all field matching include/exclude expression. This expression can contain wildcard. For example: include(spa*) will return all fields begining with 'spa'
  - a complex expression: return the result of this expression. A label can be set for this expression, in that case, field will be named with this label. For instance: 'size * 2 as bigger_size' will return a new field named bigger_size and containing the double of size field value.

* `pretty` - _optional_ - Activate pretty print
* `timezone` - _optional_ - Set timezone for datetime fields

### Retrieve a single record based on its ID.

*Tags:* `dataset` `ods`

#### Input Parameters
* `source` - _required_ - Each source represents a different catalog of datasets you'll be able to query.

There are 2 sources available:

* catalog: the catalog of datasets on your portal
* opendatasoft: OpenDataSoft's repository of public datasets, also available at
  [data.opendatasoft.com](https://data.opendatasoft.com/page/home/)

    Possible values: catalog, opendatasoft, monitoring.
* `dataset_id` - _required_ - Dataset identifier.

Can be found in the "information" tab of the dataset page.

* `record_id` - _required_
* `pretty` - _optional_ - Activate pretty print
* `timezone` - _optional_ - Set timezone for datetime fields
* `select` - _optional_ - A select expression can be used to add, remove or change fields to return.
An expression can be:
  - a wildcard ('*'): return all fields
  - a field name: return only this field
  - an include/exclude function. Include (resp exclude) all field matching include/exclude expression. This expression can contain wildcard. For example: include(spa*) will return all fields begining with 'spa'
  - a complex expression: return the result of this expression. A label can be set for this expression, in that case, field will be named with this label. For instance: 'size * 2 as bigger_size' will return a new field named bigger_size and containing the double of size field value.


### Get list of reuses

*Tags:* `dataset` `ods`

#### Input Parameters
* `source` - _required_ - Each source represents a different catalog of datasets you'll be able to query.

There are 2 sources available:

* catalog: the catalog of datasets on your portal
* opendatasoft: OpenDataSoft's repository of public datasets, also available at
  [data.opendatasoft.com](https://data.opendatasoft.com/page/home/)

    Possible values: catalog, opendatasoft, monitoring.
* `dataset_id` - _required_ - Dataset identifier.

Can be found in the "information" tab of the dataset page.

* `start` - _optional_ - Index of the first item to return (starting at 0).

To use in conjonction with rows to implement pagination.

* `rows` - _optional_ - Number of items to return.

To use in conjonction with start to implement pagination.

Rows maximum value is 100. To retrive more data use export entry points.

* `timezone` - _optional_ - Set timezone for datetime fields

### Retrieve a single reuse based on its ID.

*Tags:* `dataset` `ods`

#### Input Parameters
* `source` - _required_ - Each source represents a different catalog of datasets you'll be able to query.

There are 2 sources available:

* catalog: the catalog of datasets on your portal
* opendatasoft: OpenDataSoft's repository of public datasets, also available at
  [data.opendatasoft.com](https://data.opendatasoft.com/page/home/)

    Possible values: catalog, opendatasoft, monitoring.
* `dataset_id` - _required_ - Dataset identifier.

Can be found in the "information" tab of the dataset page.

* `reuse_id` - _required_
* `timezone` - _optional_ - Set timezone for datetime fields

### List of all snapshots for this dataset.

*Tags:* `dataset` `ods`

#### Input Parameters
* `source` - _required_ - Each source represents a different catalog of datasets you'll be able to query.

There are 2 sources available:

* catalog: the catalog of datasets on your portal
* opendatasoft: OpenDataSoft's repository of public datasets, also available at
  [data.opendatasoft.com](https://data.opendatasoft.com/page/home/)

    Possible values: catalog, opendatasoft, monitoring.
* `dataset_id` - _required_ - Dataset identifier.

Can be found in the "information" tab of the dataset page.

* `timezone` - _optional_ - Set timezone for datetime fields

### List of all snapshots for this dataset.

*Tags:* `dataset` `ods`

#### Input Parameters
* `source` - _required_ - Each source represents a different catalog of datasets you'll be able to query.

There are 2 sources available:

* catalog: the catalog of datasets on your portal
* opendatasoft: OpenDataSoft's repository of public datasets, also available at
  [data.opendatasoft.com](https://data.opendatasoft.com/page/home/)

    Possible values: catalog, opendatasoft, monitoring.
* `dataset_id` - _required_ - Dataset identifier.

Can be found in the "information" tab of the dataset page.

* `snapshot_id` - _required_
* `timezone` - _optional_ - Set timezone for datetime fields

### Export catalog (source) in CSV format

*Tags:* `export catalog` `ods`

#### Input Parameters
* `source` - _required_ - Each source represents a different catalog of datasets you'll be able to query.

There are 2 sources available:

* catalog: the catalog of datasets on your portal
* opendatasoft: OpenDataSoft's repository of public datasets, also available at
  [data.opendatasoft.com](https://data.opendatasoft.com/page/home/)

    Possible values: catalog, opendatasoft, monitoring.
* `where` - _optional_ - An array of filters.

A filter is a text expression performing a simple full-text search that can also include logical operations
(NOT, AND, OR...) as well as lots of other functions, thus performing more complex and more precise searches.
See [the query language reference](https://docs.opendatasoft.com/api/explore/v2.html#where-clause) for more details.

* `search` - _optional_ - An array of full text search.

A full text search performs a prefixed text search for each provided terms in all visible fields of a catalog/dataset.

* `rows` - _optional_ - Number of items to return.

To use in conjonction with start to implement pagination.

Rows maximum value is 100. To retrive more data use export entry points.

* `start` - _optional_ - Index of the first item to return (starting at 0).

To use in conjonction with rows to implement pagination.

* `timezone` - _optional_ - Set timezone for datetime fields
* `include_app_metas` - _optional_ - Explicitely request application metas for each datasets.

* `delimiter` - _optional_ - Provide a different delimiter (default ',').
    Possible values: ,, ;, |.

### Export catalog (source) in JSON format

*Tags:* `export catalog` `ods`

#### Input Parameters
* `source` - _required_ - Each source represents a different catalog of datasets you'll be able to query.

There are 2 sources available:

* catalog: the catalog of datasets on your portal
* opendatasoft: OpenDataSoft's repository of public datasets, also available at
  [data.opendatasoft.com](https://data.opendatasoft.com/page/home/)

    Possible values: catalog, opendatasoft, monitoring.
* `where` - _optional_ - An array of filters.

A filter is a text expression performing a simple full-text search that can also include logical operations
(NOT, AND, OR...) as well as lots of other functions, thus performing more complex and more precise searches.
See [the query language reference](https://docs.opendatasoft.com/api/explore/v2.html#where-clause) for more details.

* `search` - _optional_ - An array of full text search.

A full text search performs a prefixed text search for each provided terms in all visible fields of a catalog/dataset.

* `rows` - _optional_ - Number of items to return.

To use in conjonction with start to implement pagination.

Rows maximum value is 100. To retrive more data use export entry points.

* `start` - _optional_ - Index of the first item to return (starting at 0).

To use in conjonction with rows to implement pagination.

* `pretty` - _optional_ - Activate pretty print
* `timezone` - _optional_ - Set timezone for datetime fields
* `include_app_metas` - _optional_ - Explicitely request application metas for each datasets.


### Export catalog (source) in RDF/XML format

*Tags:* `export catalog` `ods`

#### Input Parameters
* `source` - _required_ - Each source represents a different catalog of datasets you'll be able to query.

There are 2 sources available:

* catalog: the catalog of datasets on your portal
* opendatasoft: OpenDataSoft's repository of public datasets, also available at
  [data.opendatasoft.com](https://data.opendatasoft.com/page/home/)

    Possible values: catalog, opendatasoft, monitoring.
* `where` - _optional_ - An array of filters.

A filter is a text expression performing a simple full-text search that can also include logical operations
(NOT, AND, OR...) as well as lots of other functions, thus performing more complex and more precise searches.
See [the query language reference](https://docs.opendatasoft.com/api/explore/v2.html#where-clause) for more details.

* `search` - _optional_ - An array of full text search.

A full text search performs a prefixed text search for each provided terms in all visible fields of a catalog/dataset.

* `rows` - _optional_ - Number of items to return.

To use in conjonction with start to implement pagination.

Rows maximum value is 100. To retrive more data use export entry points.

* `start` - _optional_ - Index of the first item to return (starting at 0).

To use in conjonction with rows to implement pagination.

* `timezone` - _optional_ - Set timezone for datetime fields
* `include_app_metas` - _optional_ - Explicitely request application metas for each datasets.


### Export catalog (source) in RSS format

*Tags:* `export catalog` `ods`

#### Input Parameters
* `source` - _required_ - Each source represents a different catalog of datasets you'll be able to query.

There are 2 sources available:

* catalog: the catalog of datasets on your portal
* opendatasoft: OpenDataSoft's repository of public datasets, also available at
  [data.opendatasoft.com](https://data.opendatasoft.com/page/home/)

    Possible values: catalog, opendatasoft, monitoring.
* `where` - _optional_ - An array of filters.

A filter is a text expression performing a simple full-text search that can also include logical operations
(NOT, AND, OR...) as well as lots of other functions, thus performing more complex and more precise searches.
See [the query language reference](https://docs.opendatasoft.com/api/explore/v2.html#where-clause) for more details.

* `search` - _optional_ - An array of full text search.

A full text search performs a prefixed text search for each provided terms in all visible fields of a catalog/dataset.

* `rows` - _optional_ - Number of items to return.

To use in conjonction with start to implement pagination.

Rows maximum value is 100. To retrive more data use export entry points.

* `start` - _optional_ - Index of the first item to return (starting at 0).

To use in conjonction with rows to implement pagination.

* `timezone` - _optional_ - Set timezone for datetime fields
* `include_app_metas` - _optional_ - Explicitely request application metas for each datasets.


### Export catalog (source) in TTL (turtle/rdf) format

*Tags:* `export catalog` `ods`

#### Input Parameters
* `source` - _required_ - Each source represents a different catalog of datasets you'll be able to query.

There are 2 sources available:

* catalog: the catalog of datasets on your portal
* opendatasoft: OpenDataSoft's repository of public datasets, also available at
  [data.opendatasoft.com](https://data.opendatasoft.com/page/home/)

    Possible values: catalog, opendatasoft, monitoring.
* `where` - _optional_ - An array of filters.

A filter is a text expression performing a simple full-text search that can also include logical operations
(NOT, AND, OR...) as well as lots of other functions, thus performing more complex and more precise searches.
See [the query language reference](https://docs.opendatasoft.com/api/explore/v2.html#where-clause) for more details.

* `search` - _optional_ - An array of full text search.

A full text search performs a prefixed text search for each provided terms in all visible fields of a catalog/dataset.

* `rows` - _optional_ - Number of items to return.

To use in conjonction with start to implement pagination.

Rows maximum value is 100. To retrive more data use export entry points.

* `start` - _optional_ - Index of the first item to return (starting at 0).

To use in conjonction with rows to implement pagination.

* `timezone` - _optional_ - Set timezone for datetime fields
* `include_app_metas` - _optional_ - Explicitely request application metas for each datasets.


### Export catalog (source) in XLS (Excel) format

*Tags:* `export catalog` `ods`

#### Input Parameters
* `source` - _required_ - Each source represents a different catalog of datasets you'll be able to query.

There are 2 sources available:

* catalog: the catalog of datasets on your portal
* opendatasoft: OpenDataSoft's repository of public datasets, also available at
  [data.opendatasoft.com](https://data.opendatasoft.com/page/home/)

    Possible values: catalog, opendatasoft, monitoring.
* `where` - _optional_ - An array of filters.

A filter is a text expression performing a simple full-text search that can also include logical operations
(NOT, AND, OR...) as well as lots of other functions, thus performing more complex and more precise searches.
See [the query language reference](https://docs.opendatasoft.com/api/explore/v2.html#where-clause) for more details.

* `search` - _optional_ - An array of full text search.

A full text search performs a prefixed text search for each provided terms in all visible fields of a catalog/dataset.

* `rows` - _optional_ - Number of items to return.

To use in conjonction with start to implement pagination.

Rows maximum value is 100. To retrive more data use export entry points.

* `start` - _optional_ - Index of the first item to return (starting at 0).

To use in conjonction with rows to implement pagination.

* `timezone` - _optional_ - Set timezone for datetime fields
* `include_app_metas` - _optional_ - Explicitely request application metas for each datasets.


### List of available metadata templates types, each with their endpoints.

*Tags:* `metadata` `ods`

#### Input Parameters
* `source` - _required_ - Each source represents a different catalog of datasets you'll be able to query.

There are 2 sources available:

* catalog: the catalog of datasets on your portal
* opendatasoft: OpenDataSoft's repository of public datasets, also available at
  [data.opendatasoft.com](https://data.opendatasoft.com/page/home/)

    Possible values: catalog, opendatasoft, monitoring.

### List of metadata templates available for this type.

*Tags:* `metadata` `ods`

#### Input Parameters
* `source` - _required_ - Each source represents a different catalog of datasets you'll be able to query.

There are 2 sources available:

* catalog: the catalog of datasets on your portal
* opendatasoft: OpenDataSoft's repository of public datasets, also available at
  [data.opendatasoft.com](https://data.opendatasoft.com/page/home/)

    Possible values: catalog, opendatasoft, monitoring.
* `metadata_template_type` - _required_
    Possible values: basic, interop, extra.

### A single metadata_template

*Tags:* `metadata` `ods`

#### Input Parameters
* `source` - _required_ - Each source represents a different catalog of datasets you'll be able to query.

There are 2 sources available:

* catalog: the catalog of datasets on your portal
* opendatasoft: OpenDataSoft's repository of public datasets, also available at
  [data.opendatasoft.com](https://data.opendatasoft.com/page/home/)

    Possible values: catalog, opendatasoft, monitoring.
* `metadata_template_type` - _required_
    Possible values: basic, interop, extra.
* `metadata_template_name` - _required_

## License

**flow**ground :- Telekom iPaaS / opendatasoft-com-connector<br/>
Copyright © 2019, [Deutsche Telekom AG](https://www.telekom.de)<br/>
contact: flowground@telekom.de

All files of this connector are licensed under the Apache 2.0 License. For details
see the file LICENSE on the toplevel directory.
