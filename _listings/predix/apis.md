---
name: Predix
x-slug: predix
description: Predix (IoT PaaS) helps you develop apps that connect people with industrial
  machines through analytics and data for better business outcomes.
image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/predix-vector-logo.png
x-kinRank: "7"
x-alexaRank: "264121"
tags: Datapoints
created: "2018-08-26"
modified: "2018-08-26"
url: https://raw.githubusercontent.com/streamdata-gallery-topics/datapoints/master/_listings/predix/apis.md
specificationVersion: "0.14"
apis:
- name: Data Services - Query Datapoints
  x-api-slug: v1datapoints-get
  description: "Both the GET and POST methods can be used to query time series data.
    Use the query API with the GET HTTP method by passing the query JSON as a URL
    query parameter. The advantage of using the GET method is that requests and responses
    can be cached in proxy servers and browsers.  In cases where the query JSON is
    very long and exceeds query parameter length (for some browsers), use POST as
    a convenience method to query the time series API. POST requests have no restrictions
    on data length, however, requests are never cached. The Time Series service API
    is designed this way to support complex, nested time series queries on one or
    more tags and their attributes, with start and end times, along with aggregations
    and filters.Response JSON (Status 200)\n{\n\t\"tags\": [{\n\t\t\"name\": \"ALT_SENSOR\",\n\t\t\"results\":
    [{\n\t\t\t\"filters\": {\n\t\t\t\t\"attributes\": {\n\t\t\t\t\t\"host\": [\n\t\t\t\t\t\t\"test\"\n\t\t\t\t\t]\n\t\t\t\t},\n\t\t\t\t\"measurements\":
    {\n\t\t\t\t\t\"condition\": \"le\",\n\t\t\t\t\t\"values\": [\n\t\t\t\t\t\t36\n\t\t\t\t\t]\n\t\t\t\t},\n\t\t\t\t\"qualities\":
    {\n\t\t\t\t\t\"values\": [\n\t\t\t\t\t\t\"3\"\n\t\t\t\t\t]\n\t\t\t\t}\n\t\t\t},\n\t\t\t\"attributes\":
    {\n\t\t\t\t\"host\": [\"test\"]\n\t\t\t},\n\t\t\t\"values\": [\n\t\t\t\t[1449709894000,
    5, 3],\n\t\t\t\t[1449709895000, 7, 3]\n\t\t\t]\n\t\t}],\n\t\t\"stats\": {\n\t\t\t\"rawCount\":
    2\n\t\t}\n\t}]\n}"
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/predix-vector-logo.png
  humanURL: https://www.predix.io
  baseURL: https://time-series-service-doc.grc-apps.svc.ice.ge.com//
  tags: SaaS, Technology, Enterprise, Internet of Things, Relative Data, Service API
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-topics/datapoints/master/_listings/predix/v1datapoints-get-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-topics/datapoints/master/_listings/predix/v1datapoints-get-openapi.md
x-common:
- type: x-api-gallery
  url: http://predicthq.api.gallery.streamdata.io
- type: x-api-stack
  url: http://predix.stack.network
- type: x-crunchbase
  url: https://crunchbase.com/organization/predix
- type: x-documentation
  url: https://docs.predix.io/en-US/platform
- type: x-twitter
  url: https://twitter.com/Predix
- type: x-website
  url: https://www.predix.io
include: []
maintainers:
- FN: Kin Lane
  x-twitter: apievangelist
  email: info@apievangelist.com
---