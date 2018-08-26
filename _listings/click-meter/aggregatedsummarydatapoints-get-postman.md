{
  "info": {
    "name": "Click Meter Retrieve statistics about a subset of datapoints for a timeframe with datapoints data",
    "_postman_id": "7c9559f5-3d5e-434c-a9e0-53d848d9c827",
    "description": "Retrieve statistics about a subset of datapoints for a timeframe with datapoints data.",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "Aggregated",
      "item": [
        {
          "id": "c3289cd8-e7e0-4763-8540-7cc6a31cc374",
          "name": "getAggregatedSummaryDatapoints",
          "request": {
            "url": "http://apiv2.clickmeter.com:80/aggregated/summary/datapoints?favourite=%7B%7D&fromDay=%7B%7D&groupId=%7B%7D&limit=%7B%7D&offset=%7B%7D&sortBy=%7B%7D&sortDirection=%7B%7D&status=%7B%7D&tag=%7B%7D&textSearch=%7B%7D&timeFrame=%7B%7D&toDay=%7B%7D&type=%7B%7D",
            "method": "GET",
            "body": {
              "mode": "raw"
            },
            "description": "Retrieve statistics about a subset of datapoints for a timeframe with datapoints data."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "77c0bcdd-ecfb-464b-ad66-c39e10dadcad"
            }
          ]
        }
      ]
    }
  ]
}