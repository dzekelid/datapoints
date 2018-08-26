{
  "info": {
    "name": "Predix Data Services Query Datapoints",
    "_postman_id": "457dd810-c11c-4016-95cc-417f8dc1cea5",
    "description": "Both the GET and POST methods can be used to query time series data. Use the query API with the GET HTTP method by passing the query JSON as a URL query parameter. The advantage of using the GET method is that requests and responses can be cached in proxy servers and browsers.  In cases where the query JSON is very long and exceeds query parameter length (for some browsers), use POST as a convenience method to query the time series API. POST requests have no restrictions on data length, however, requests are never cached. The Time Series service API is designed this way to support complex, nested time series queries on one or more tags and their attributes, with start and end times, along with aggregations and filters.Response JSON (Status 200)\n{\n\t\"tags\": [{\n\t\t\"name\": \"ALT_SENSOR\",\n\t\t\"results\": [{\n\t\t\t\"filters\": {\n\t\t\t\t\"attributes\": {\n\t\t\t\t\t\"host\": [\n\t\t\t\t\t\t\"test\"\n\t\t\t\t\t]\n\t\t\t\t},\n\t\t\t\t\"measurements\": {\n\t\t\t\t\t\"condition\": \"le\",\n\t\t\t\t\t\"values\": [\n\t\t\t\t\t\t36\n\t\t\t\t\t]\n\t\t\t\t},\n\t\t\t\t\"qualities\": {\n\t\t\t\t\t\"values\": [\n\t\t\t\t\t\t\"3\"\n\t\t\t\t\t]\n\t\t\t\t}\n\t\t\t},\n\t\t\t\"attributes\": {\n\t\t\t\t\"host\": [\"test\"]\n\t\t\t},\n\t\t\t\"values\": [\n\t\t\t\t[1449709894000, 5, 3],\n\t\t\t\t[1449709895000, 7, 3]\n\t\t\t]\n\t\t}],\n\t\t\"stats\": {\n\t\t\t\"rawCount\": 2\n\t\t}\n\t}]\n}",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "Available",
      "item": [
        {
          "id": "448d65a9-0d42-435b-ad9f-bc475f17de73",
          "name": "getAggregationNames",
          "request": {
            "url": "http://time-series-service-doc.grc-apps.svc.ice.ge.com/v1/aggregations",
            "method": "GET",
            "header": [
              {
                "key": "Authorization",
                "value": "{}",
                "description": "",
                "disabled": false
              },
              {
                "key": "Content-Type",
                "value": "{}",
                "description": "",
                "disabled": false
              },
              {
                "key": "Predix-Zone-Id",
                "value": "{}",
                "description": "",
                "disabled": false
              },
              {
                "key": "Accept",
                "value": "*/*",
                "disabled": false
              }
            ],
            "body": {
              "mode": "raw"
            },
            "description": "Return all supported aggregations.Response JSON (Status 200){\n  \"results\": [\n    {\n      \"name\": \"max\",\n      \"type\": \"Maximum\",\n      \"description\": \"Returns the maximum value data point for the time range\"\n    },\n    {\n      \"name\": \"trendmode\",\n      \"type\": \"Trend Mode\",\n      \"description\": \"Returns the maximum and minimum value data point for the time range\"\n    },\n    {\n      \"name\": \"count\",\n      \"type\": \"Count\",\n      \"description\": \"Returns the number of data points\"\n    },\n    {\n      \"name\": \"scale\",\n      \"type\": \"Scale\",\n      \"description\": \"Scales each data point by a factor\"\n    },\n    {\n      \"name\": \"interpolate\",\n      \"type\": \"Interpolate\",\n      \"description\": \"Does linear interpolation for the chosen window\"\n    },\n    {\n      \"name\": \"sum\",\n      \"type\": \"Sum\",\n      \"description\": \"Adds the data points together\"\n    },\n    {\n      \"name\": \"diff\",\n      \"type\": \"Difference\",\n      \"description\": \"Returns the difference between successive data points\"\n    },\n    {\n      \"name\": \"gaps\",\n      \"type\": \"Gaps\",\n      \"description\": \"Marks gaps in data according to sampling rate with a null data point\"\n    },\n    {\n      \"name\": \"sampler\",\n      \"type\": \"Sampler\",\n      \"description\": \"Returns the sampling rate of change for the data points\"\n    },\n    {\n      \"name\": \"div\",\n      \"type\": \"Divide\",\n      \"description\": \"Divides each data point by a divisor\"\n    },\n    {\n      \"name\": \"min\",\n      \"type\": \"Minimum\",\n      \"description\": \"Returns the minimum value data point for the time range\"\n    },\n    {\n      \"name\": \"avg\",\n      \"type\": \"Average\",\n      \"description\": \"Returns the average of the data point set\"\n    },\n    {\n      \"name\": \"least_squares\",\n      \"type\": \"Least Squares\",\n      \"description\": \"Returns a best fit line through the data points using the least squares algorithm\"\n    },\n    {\n      \"name\": \"percentile\",\n      \"type\": \"Percentile\",\n      \"description\": \"Returns the percentile of the data range\"\n    },\n    {\n      \"name\": \"dev\",\n      \"type\": \"Standard Deviation\",\n      \"description\": \"Returns the standard deviation of the time series\"\n    },\n    {\n      \"name\": \"rate\",\n      \"type\": \"Rate\",\n      \"description\": \"Returns the rate of change for the data points\"\n    }\n  ]\n}"
          },
          "response": [
            {
              "status": "Successful response",
              "code": 200,
              "name": "Response_200",
              "id": "21b63644-aedf-4bd8-9633-1f0ea342d065"
            }
          ]
        }
      ]
    },
    {
      "name": "Query",
      "item": [
        {
          "id": "9d782a4e-e9e4-4d00-9566-67100510051f",
          "name": "query",
          "request": {
            "url": "http://time-series-service-doc.grc-apps.svc.ice.ge.com/v1/datapoints?query=%7B%7D",
            "method": "GET",
            "header": [
              {
                "key": "Authorization",
                "value": "{}",
                "description": "",
                "disabled": false
              },
              {
                "key": "Content-Type",
                "value": "{}",
                "description": "",
                "disabled": false
              },
              {
                "key": "Predix-Zone-Id",
                "value": "{}",
                "description": "",
                "disabled": false
              },
              {
                "key": "Accept",
                "value": "*/*",
                "disabled": false
              }
            ],
            "body": {
              "mode": "raw"
            },
            "description": "Both the GET and POST methods can be used to query time series data. Use the query API with the GET HTTP method by passing the query JSON as a URL query parameter. The advantage of using the GET method is that requests and responses can be cached in proxy servers and browsers.  In cases where the query JSON is very long and exceeds query parameter length (for some browsers), use POST as a convenience method to query the time series API. POST requests have no restrictions on data length, however, requests are never cached. The Time Series service API is designed this way to support complex, nested time series queries on one or more tags and their attributes, with start and end times, along with aggregations and filters.Response JSON (Status 200)\n{\n\t\"tags\": [{\n\t\t\"name\": \"ALT_SENSOR\",\n\t\t\"results\": [{\n\t\t\t\"filters\": {\n\t\t\t\t\"attributes\": {\n\t\t\t\t\t\"host\": [\n\t\t\t\t\t\t\"test\"\n\t\t\t\t\t]\n\t\t\t\t},\n\t\t\t\t\"measurements\": {\n\t\t\t\t\t\"condition\": \"le\",\n\t\t\t\t\t\"values\": [\n\t\t\t\t\t\t36\n\t\t\t\t\t]\n\t\t\t\t},\n\t\t\t\t\"qualities\": {\n\t\t\t\t\t\"values\": [\n\t\t\t\t\t\t\"3\"\n\t\t\t\t\t]\n\t\t\t\t}\n\t\t\t},\n\t\t\t\"attributes\": {\n\t\t\t\t\"host\": [\"test\"]\n\t\t\t},\n\t\t\t\"values\": [\n\t\t\t\t[1449709894000, 5, 3],\n\t\t\t\t[1449709895000, 7, 3]\n\t\t\t]\n\t\t}],\n\t\t\"stats\": {\n\t\t\t\"rawCount\": 2\n\t\t}\n\t}]\n}"
          },
          "response": [
            {
              "status": "Successful response",
              "code": 200,
              "name": "Response_200",
              "id": "7f13507f-68a3-4dc6-b1a4-8f70d0d55503"
            }
          ]
        }
      ]
    }
  ]
}