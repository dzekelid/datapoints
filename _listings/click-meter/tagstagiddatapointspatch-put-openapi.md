---
swagger: "2.0"
x-collection-name: Click Meter
x-complete: 0
info:
  title: Click Meter Associate/Deassociate a tag with a datapoint
  description: Associate/deassociate a tag with a datapoint.
  contact:
    name: Api Support
    url: http://www.clickmeter.com/api
    email: api@clickmeter.com
  version: v2
host: apiv2.clickmeter.com:80
basePath: /
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /aggregated/summary/datapoints:
    get:
      summary: Retrieve statistics about a subset of datapoints for a timeframe with
        datapoints data
      description: Retrieve statistics about a subset of datapoints for a timeframe
        with datapoints data.
      operationId: getAggregatedSummaryDatapoints
      x-api-path-slug: aggregatedsummarydatapoints-get
      parameters:
      - in: query
        name: favourite
        description: Is the datapoint marked as favourite
      - in: query
        name: fromDay
        description: If using a custom timeFrame you can specify the starting day
          (YYYYMMDD)
      - in: query
        name: groupId
        description: Filter by this group id
      - in: query
        name: limit
        description: Limit results to this number
      - in: query
        name: offset
        description: Offset where to start from
      - in: query
        name: sortBy
        description: Field to sort by
      - in: query
        name: sortDirection
        description: Direction of sort asc or desc
      - in: query
        name: status
        description: Status of datapoint (deleted/active/paused/spam)
      - in: query
        name: tag
        description: A comma separated list of tags you want to filter with
      - in: query
        name: textSearch
        description: Filter fields by this pattern
      - in: query
        name: timeFrame
        description: Timeframe of the request
      - in: query
        name: toDay
        description: If using a custom timeFrame you can specify the ending day (YYYYMMDD)
      - in: query
        name: type
        description: Type of datapoint (tl/tp)
      responses:
        200:
          description: OK
      tags:
      - Aggregated
      - Summary
      - Datapoints
  /conversions/{conversionId}/datapoints:
    get:
      summary: Retrieve a list of datapoints connected to this conversion
      description: Retrieve a list of datapoints connected to this conversion.
      operationId: getConversionsConversionDatapoints
      x-api-path-slug: conversionsconversioniddatapoints-get
      parameters:
      - in: path
        name: conversionId
        description: Id of the conversion
      - in: query
        name: createdAfter
        description: Exclude datapoints created before this date (YYYYMMDD)
      - in: query
        name: createdBefore
        description: Exclude datapoints created after this date (YYYYMMDD)
      - in: query
        name: limit
        description: Limit results to this number
      - in: query
        name: offset
        description: Offset where to start from
      - in: query
        name: status
        description: Status of datapoint (deleted/active/paused/spam)
      - in: query
        name: tags
        description: Filter by this tag name
      - in: query
        name: textSearch
        description: Filter fields by this pattern
      - in: query
        name: type
        description: Type of datapoint (tl/tp)
      responses:
        200:
          description: OK
      tags:
      - Conversions
      - ConversionId
      - Datapoints
  /conversions/{conversionId}/datapoints/batch/patch:
    put:
      summary: Modify the association between a conversion and multiple datapoints
      description: Modify the association between a conversion and multiple datapoints.
      operationId: putConversionsConversionDatapointsBatchPatch
      x-api-path-slug: conversionsconversioniddatapointsbatchpatch-put
      parameters:
      - in: path
        name: conversionId
        description: Id of the conversion
      - in: body
        name: data
        description: Patch requests
        schema:
          $ref: '#/definitions/holder'
      responses:
        200:
          description: OK
      tags:
      - Conversions
      - ConversionId
      - Datapoints
      - Batch
      - Patch
  /conversions/{conversionId}/datapoints/count:
    get:
      summary: Retrieve a count of datapoints connected to this conversion
      description: Retrieve a count of datapoints connected to this conversion.
      operationId: getConversionsConversionDatapointsCount
      x-api-path-slug: conversionsconversioniddatapointscount-get
      parameters:
      - in: path
        name: conversionId
        description: Id of the conversion
      - in: query
        name: createdAfter
        description: Exclude datapoints created before this date (YYYYMMDD)
      - in: query
        name: createdBefore
        description: Exclude datapoints created after this date (YYYYMMDD)
      - in: query
        name: status
        description: Status of datapoint (deleted/active/paused/spam)
      - in: query
        name: tags
        description: Filter by this tag name
      - in: query
        name: textSearch
        description: Filter fields by this pattern
      - in: query
        name: type
        description: Type of datapoint (tl/tp)
      responses:
        200:
          description: OK
      tags:
      - Conversions
      - ConversionId
      - Datapoints
      - Count
  /conversions/{conversionId}/datapoints/patch:
    put:
      summary: Modify the association between a conversion and a datapoint
      description: Modify the association between a conversion and a datapoint.
      operationId: putConversionsConversionDatapointsPatch
      x-api-path-slug: conversionsconversioniddatapointspatch-put
      parameters:
      - in: path
        name: conversionId
        description: Id of the conversion
      - in: body
        name: data
        description: Patch request
        schema:
          $ref: '#/definitions/holder'
      responses:
        200:
          description: OK
      tags:
      - Conversions
      - ConversionId
      - Datapoints
      - Patch
  /datapoints:
    get:
      summary: List of all the datapoints associated to the user
      description: List of all the datapoints associated to the user.
      operationId: getDatapoints
      x-api-path-slug: datapoints-get
      parameters:
      - in: query
        name: createdAfter
        description: Exclude datapoints created before this date (YYYYMMDD)
      - in: query
        name: createdBefore
        description: Exclude datapoints created after this date (YYYYMMDD)
      - in: query
        name: limit
        description: Maximum elements to retrieve
      - in: query
        name: offset
        description: Where to start when retrieving elements
      - in: query
        name: onlyFavorites
        description: Filter fields by favourite status
      - in: query
        name: sortBy
        description: Field to sort by
      - in: query
        name: sortDirection
        description: Direction of sort asc or desc
      - in: query
        name: status
        description: Status of the datapoint
      - in: query
        name: tags
        description: A comma separated list of tags you want to filter with
      - in: query
        name: textSearch
        description: Filter fields by this pattern
      - in: query
        name: type
        description: Type of the datapoint (tp/tl)
      responses:
        200:
          description: OK
      tags:
      - Datapoints
    post:
      summary: Create a datapoint
      description: Create a datapoint.
      operationId: postDatapoints
      x-api-path-slug: datapoints-post
      parameters:
      - in: body
        name: value
        description: The body of the datapoint
        schema:
          $ref: '#/definitions/holder'
      responses:
        200:
          description: OK
      tags:
      - Datapoints
  /datapoints/aggregated:
    get:
      summary: Retrieve statistics about this customer for a timeframe by groups
      description: Retrieve statistics about this customer for a timeframe by groups.
      operationId: getDatapointsAggregated
      x-api-path-slug: datapointsaggregated-get
      parameters:
      - in: query
        name: favourite
        description: Is the datapoint is marked as favourite
      - in: query
        name: fromDay
        description: If using a custom timeFrame you can specify the starting day
          (YYYYMMDD)
      - in: query
        name: hourly
        description: If using yesterday or today timeframe you can ask for the hourly
          detail
      - in: query
        name: status
        description: Status of datapoint (deleted/active/paused/spam)
      - in: query
        name: tag
        description: A comma separated list of tags you want to filter with
      - in: query
        name: timeFrame
        description: Timeframe of the request
      - in: query
        name: toDay
        description: If using a custom timeFrame you can specify the ending day (YYYYMMDD)
      - in: query
        name: type
        description: Type of datapoint (tl/tp)
      responses:
        200:
          description: OK
      tags:
      - Datapoints
      - Aggregated
  /datapoints/aggregated/list:
    get:
      summary: Retrieve statistics about all datapoints of this customer for a timeframe
        grouped by some temporal entity (day/week/month)
      description: Retrieve statistics about all datapoints of this customer for a
        timeframe grouped by some temporal entity (day/week/month).
      operationId: getDatapointsAggregatedList
      x-api-path-slug: datapointsaggregatedlist-get
      parameters:
      - in: query
        name: favourite
        description: Is the datapoint is marked as favourite
      - in: query
        name: fromDay
        description: If using a custom timeFrame you can specify the starting day
          (YYYYMMDD)
      - in: query
        name: groupBy
        description: The temporal entity you want to group by (week/month)
      - in: query
        name: status
        description: Status of datapoint (deleted/active/paused/spam)
      - in: query
        name: tag
        description: A comma separated list of tags you want to filter with
      - in: query
        name: timeFrame
        description: Timeframe of the request
      - in: query
        name: toDay
        description: If using a custom timeFrame you can specify the ending day (YYYYMMDD)
      - in: query
        name: type
        description: Type of datapoint (tl/tp)
      responses:
        200:
          description: OK
      tags:
      - Datapoints
      - Aggregated
      - List
  /datapoints/batch:
    delete:
      summary: Delete multiple datapoints
      description: Delete multiple datapoints.
      operationId: deleteDatapointsBatch
      x-api-path-slug: datapointsbatch-delete
      parameters:
      - in: body
        name: batch
        description: A json containing the datapoints to delete
        schema:
          $ref: '#/definitions/holder'
      responses:
        200:
          description: OK
      tags:
      - Datapoints
      - Batch
    post:
      summary: Update multiple datapoints
      description: Update multiple datapoints.
      operationId: postDatapointsBatch
      x-api-path-slug: datapointsbatch-post
      parameters:
      - in: body
        name: batch
        description: A json containing the datapoints to update
        schema:
          $ref: '#/definitions/holder'
      responses:
        200:
          description: OK
      tags:
      - Datapoints
      - Batch
    put:
      summary: Create multiple datapoints
      description: Create multiple datapoints.
      operationId: putDatapointsBatch
      x-api-path-slug: datapointsbatch-put
      parameters:
      - in: body
        name: batch
        description: A json containing the datapoints to create
        schema:
          $ref: '#/definitions/holder'
      responses:
        200:
          description: OK
      tags:
      - Datapoints
      - Batch
  /datapoints/count:
    get:
      summary: Count the datapoints associated to the user
      description: Count the datapoints associated to the user.
      operationId: getDatapointsCount
      x-api-path-slug: datapointscount-get
      parameters:
      - in: query
        name: createdAfter
        description: Exclude datapoints created before this date (YYYYMMDD)
      - in: query
        name: createdBefore
        description: Exclude datapoints created after this date (YYYYMMDD)
      - in: query
        name: onlyFavorites
        description: Filter fields by favourite status
      - in: query
        name: status
        description: Status of the datapoint
      - in: query
        name: tags
        description: A comma separated list of tags you want to filter with
      - in: query
        name: textSearch
        description: Filter fields by this pattern
      - in: query
        name: type
        description: Type of the datapoint (tp/tl)
      responses:
        200:
          description: OK
      tags:
      - Datapoints
      - Count
  /datapoints/{id}:
    delete:
      summary: Delete a datapoint
      description: Delete a datapoint.
      operationId: deleteDatapoints
      x-api-path-slug: datapointsid-delete
      parameters:
      - in: path
        name: id
        description: The id of the datapoint
      responses:
        200:
          description: OK
      tags:
      - Datapoints
      - Id
    get:
      summary: Get a datapoint
      description: Get a datapoint.
      operationId: getDatapoints
      x-api-path-slug: datapointsid-get
      parameters:
      - in: path
        name: id
        description: The id of the datapoint
      responses:
        200:
          description: OK
      tags:
      - Datapoints
      - Id
    post:
      summary: Update a datapoint
      description: Update a datapoint.
      operationId: postDatapoints
      x-api-path-slug: datapointsid-post
      parameters:
      - in: path
        name: id
        description: The id of the datapoint
      - in: body
        name: value
        description: The body of the datapoint
        schema:
          $ref: '#/definitions/holder'
      responses:
        200:
          description: OK
      tags:
      - Datapoints
      - Id
  /datapoints/{id}/aggregated:
    get:
      summary: Retrieve statistics about this datapoint for a timeframe
      description: Retrieve statistics about this datapoint for a timeframe.
      operationId: getDatapointsAggregated
      x-api-path-slug: datapointsidaggregated-get
      parameters:
      - in: query
        name: fromDay
        description: If using a custom timeFrame you can specify the starting day
          (YYYYMMDD)
      - in: query
        name: hourly
        description: If using yesterday or today timeframe you can ask for the hourly
          detail
      - in: path
        name: id
        description: Id of the datapoint
      - in: query
        name: timeFrame
        description: Timeframe of the request
      - in: query
        name: toDay
        description: If using a custom timeFrame you can specify the ending day (YYYYMMDD)
      responses:
        200:
          description: OK
      tags:
      - Datapoints
      - Id
      - Aggregated
  /datapoints/{id}/aggregated/list:
    get:
      summary: Retrieve statistics about this datapoint for a timeframe grouped by
        some temporal entity (day/week/month)
      description: Retrieve statistics about this datapoint for a timeframe grouped
        by some temporal entity (day/week/month).
      operationId: getDatapointsAggregatedList
      x-api-path-slug: datapointsidaggregatedlist-get
      parameters:
      - in: query
        name: fromDay
        description: If using a custom timeFrame you can specify the starting day
          (YYYYMMDD)
      - in: query
        name: groupBy
        description: The temporal entity you want to group by (week/month)
      - in: path
        name: id
        description: Id of the datapoint
      - in: query
        name: timeFrame
        description: Timeframe of the request
      - in: query
        name: toDay
        description: If using a custom timeFrame you can specify the ending day (YYYYMMDD)
      responses:
        200:
          description: OK
      tags:
      - Datapoints
      - Id
      - Aggregated
      - List
  /datapoints/{id}/favourite:
    put:
      summary: Fast switch the "favourite" field of a datapoint
      description: Fast switch the "favourite" field of a datapoint.
      operationId: putDatapointsFavourite
      x-api-path-slug: datapointsidfavourite-put
      parameters:
      - in: path
        name: id
        description: Id of the datapoint
      responses:
        200:
          description: OK
      tags:
      - Datapoints
      - Id
      - Favourite
  /datapoints/{id}/hits:
    get:
      summary: Retrieve the list of events related to this datapoint.
      description: Retrieve the list of events related to this datapoint..
      operationId: getDatapointsHits
      x-api-path-slug: datapointsidhits-get
      parameters:
      - in: query
        name: filter
        description: Filter event type (spiders/uniques/nonuniques/conversions)
      - in: query
        name: fromDay
        description: If using a custom timeFrame you can specify the starting day
          (YYYYMMDD)
      - in: path
        name: id
        description: Id of the datapoint
      - in: query
        name: limit
        description: Limit results to this number
      - in: query
        name: offset
        description: Offset where to start from (its the lastKey field in the response
          object)
      - in: query
        name: timeframe
        description: Timeframe of the request
      - in: query
        name: toDay
        description: If using a custom timeFrame you can specify the ending day (YYYYMMDD)
      responses:
        200:
          description: OK
      tags:
      - Datapoints
      - Id
      - Hits
  /datapoints/{id}/notes:
    put:
      summary: Fast patch the "notes" field of a datapoint
      description: Fast patch the "notes" field of a datapoint.
      operationId: putDatapointsNotes
      x-api-path-slug: datapointsidnotes-put
      parameters:
      - in: path
        name: id
        description: Id of the datapoint
      - in: body
        name: note
        description: Patch requests
        schema:
          $ref: '#/definitions/holder'
      responses:
        200:
          description: OK
      tags:
      - Datapoints
      - Id
      - Notes
  /datapoints/{id}/reports:
    get:
      summary: Retrieve a top report connected to this datapoint
      description: Retrieve a top report connected to this datapoint.
      operationId: getDatapointsReports
      x-api-path-slug: datapointsidreports-get
      parameters:
      - in: query
        name: fromDay
        description: If using a custom timeFrame you can specify the starting day
          (YYYYMMDD)
      - in: path
        name: id
        description: Id of the datapoint
      - in: query
        name: timeframe
        description: Timeframe of the request
      - in: query
        name: toDay
        description: If using a custom timeFrame you can specify the ending day (YYYYMMDD)
      - in: query
        name: type
        description: Type of the report
      responses:
        200:
          description: OK
      tags:
      - Datapoints
      - Id
      - Reports
  /groups/{id}/datapoints:
    get:
      summary: List of all the datapoints associated to the user in this group.
      description: List of all the datapoints associated to the user in this group..
      operationId: getGroupsDatapoints
      x-api-path-slug: groupsiddatapoints-get
      parameters:
      - in: query
        name: createdAfter
        description: Exclude datapoints created before this date (YYYYMMDD)
      - in: query
        name: createdBefore
        description: Exclude datapoints created after this date (YYYYMMDD)
      - in: path
        name: id
        description: Id of the group
      - in: query
        name: limit
        description: Maximum elements to retrieve
      - in: query
        name: offset
        description: Where to start when retrieving elements
      - in: query
        name: onlyFavorites
        description: Filter fields by favourite status
      - in: query
        name: sortBy
        description: Field to sort by
      - in: query
        name: sortDirection
        description: Direction of sort asc or desc
      - in: query
        name: status
        description: Status of the datapoint
      - in: query
        name: tags
        description: A comma separated list of tags you want to filter with
      - in: query
        name: textSearch
        description: Filter fields by this pattern
      - in: query
        name: type
        description: Type of the datapoint (tp/tl)
      responses:
        200:
          description: OK
      tags:
      - Groups
      - Id
      - Datapoints
    post:
      summary: Create a datapoint in this group
      description: Create a datapoint in this group.
      operationId: postGroupsDatapoints
      x-api-path-slug: groupsiddatapoints-post
      parameters:
      - in: path
        name: id
        description: The id of the group
      - in: body
        name: value
        description: The body of the datapoint
        schema:
          $ref: '#/definitions/holder'
      responses:
        200:
          description: OK
      tags:
      - Groups
      - Id
      - Datapoints
  /groups/{id}/datapoints/count:
    get:
      summary: Count the datapoints associated to the user in this group.
      description: Count the datapoints associated to the user in this group..
      operationId: getGroupsDatapointsCount
      x-api-path-slug: groupsiddatapointscount-get
      parameters:
      - in: query
        name: createdAfter
        description: Exclude datapoints created before this date (YYYYMMDD)
      - in: query
        name: createdBefore
        description: Exclude datapoints created after this date (YYYYMMDD)
      - in: path
        name: id
        description: Id of the group
      - in: query
        name: onlyFavorites
        description: Filter fields by favourite status
      - in: query
        name: status
        description: Status of the datapoint
      - in: query
        name: tags
        description: A comma separated list of tags you want to filter with
      - in: query
        name: textSearch
        description: Filter fields by this pattern
      - in: query
        name: type
        description: Type of the datapoint (tp/tl)
      responses:
        200:
          description: OK
      tags:
      - Groups
      - Id
      - Datapoints
      - Count
  /retargeting/{id}/datapoints:
    get:
      summary: List of all the datapoints associated to the retargeting script.
      description: List of all the datapoints associated to the retargeting script..
      operationId: getRetargetingDatapoints
      x-api-path-slug: retargetingiddatapoints-get
      parameters:
      - in: query
        name: createdAfter
        description: Exclude datapoints created before this date (YYYYMMDD)
      - in: query
        name: createdBefore
        description: Exclude datapoints created after this date (YYYYMMDD)
      - in: path
        name: id
        description: Id of the retargeting script
      - in: query
        name: limit
        description: Maximum elements to retrieve
      - in: query
        name: offset
        description: Where to start when retrieving elements
      - in: query
        name: onlyFavorites
        description: Filter fields by favourite status
      - in: query
        name: sortBy
        description: Field to sort by
      - in: query
        name: sortDirection
        description: Direction of sort asc or desc
      - in: query
        name: status
        description: Status of the datapoint
      - in: query
        name: tags
        description: A comma separated list of tags you want to filter with
      - in: query
        name: textSearch
        description: Filter fields by this pattern
      responses:
        200:
          description: OK
      tags:
      - Retargeting
      - Id
      - Datapoints
  /retargeting/{id}/datapoints/count:
    get:
      summary: Count the datapoints associated to the retargeting script.
      description: Count the datapoints associated to the retargeting script..
      operationId: getRetargetingDatapointsCount
      x-api-path-slug: retargetingiddatapointscount-get
      parameters:
      - in: query
        name: createdAfter
        description: Exclude datapoints created before this date (YYYYMMDD)
      - in: query
        name: createdBefore
        description: Exclude datapoints created after this date (YYYYMMDD)
      - in: path
        name: id
        description: Id of the group
      - in: query
        name: onlyFavorites
        description: Filter fields by favourite status
      - in: query
        name: status
        description: Status of the datapoint
      - in: query
        name: tags
        description: A comma separated list of tags you want to filter with
      - in: query
        name: textSearch
        description: Filter fields by this pattern
      responses:
        200:
          description: OK
      tags:
      - Retargeting
      - Id
      - Datapoints
      - Count
  /tags/{tagId}/datapoints:
    delete:
      summary: Delete the association of this tag with all datapoints
      description: Delete the association of this tag with all datapoints.
      operationId: deleteTagsTagDatapoints
      x-api-path-slug: tagstagiddatapoints-delete
      parameters:
      - in: path
        name: tagId
        description: Id of the tag
      responses:
        200:
          description: OK
      tags:
      - Tags
      - TagId
      - Datapoints
    get:
      summary: List of all the datapoints associated to the user filtered by this
        tag
      description: List of all the datapoints associated to the user filtered by this
        tag.
      operationId: getTagsTagDatapoints
      x-api-path-slug: tagstagiddatapoints-get
      parameters:
      - in: query
        name: createdAfter
        description: Exclude datapoints created before this date (YYYYMMDD)
      - in: query
        name: createdBefore
        description: Exclude datapoints created after this date (YYYYMMDD)
      - in: query
        name: limit
        description: Maximum elements to retrieve
      - in: query
        name: offset
        description: Where to start when retrieving elements
      - in: query
        name: status
        description: Status of the datapoint
      - in: path
        name: tagId
        description: Id of the tag
      - in: query
        name: textSearch
        description: Filter fields by this pattern
      - in: query
        name: type
        description: Type of the datapoint (tp/tl)
      responses:
        200:
          description: OK
      tags:
      - Tags
      - TagId
      - Datapoints
  /tags/{tagId}/datapoints/count:
    get:
      summary: Count the datapoints associated to the user filtered by this tag
      description: Count the datapoints associated to the user filtered by this tag.
      operationId: getTagsTagDatapointsCount
      x-api-path-slug: tagstagiddatapointscount-get
      parameters:
      - in: query
        name: createdAfter
        description: Exclude datapoints created before this date (YYYYMMDD)
      - in: query
        name: createdBefore
        description: Exclude datapoints created after this date (YYYYMMDD)
      - in: query
        name: status
        description: Status of the datapoint
      - in: path
        name: tagId
        description: Id of the tag
      - in: query
        name: textSearch
        description: Filter fields by this pattern
      - in: query
        name: type
        description: Type of the datapoint (tp/tl)
      responses:
        200:
          description: OK
      tags:
      - Tags
      - TagId
      - Datapoints
      - Count
  /tags/{tagId}/datapoints/patch:
    put:
      summary: Associate/Deassociate a tag with a datapoint
      description: Associate/deassociate a tag with a datapoint.
      operationId: putTagsTagDatapointsPatch
      x-api-path-slug: tagstagiddatapointspatch-put
      parameters:
      - in: body
        name: data
        description: The body patch
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: tagId
        description: Id of the tag
      responses:
        200:
          description: OK
      tags:
      - Tags
      - TagId
      - Datapoints
      - Patch
x-streamrank:
  polling_total_time_average: 0
  polling_size_download_average: 0
  streaming_total_time_average: 0
  streaming_size_download_average: 0
  change_yes: 0
  change_no: 0
  time_percentage: 0
  size_percentage: 0
  change_percentage: 0
  last_run: ""
  days_run: 0
  minute_run: 0
---