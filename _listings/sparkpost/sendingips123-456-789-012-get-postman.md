{
  "info": {
    "name": "SparkPost Get a Sending IP",
    "_postman_id": "bcad3a72-7385-429d-8e75-9bd804113508",
    "description": "Get a sending ip.",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "Email",
      "item": [
        {
          "id": "16da1301-1107-4ddb-a78a-7e955e7d03ee",
          "name": "getSendingIps123.456.789.012",
          "request": {
            "url": "http://api.sparkpost.com/api/v1/sending-ips/123.456.789.012",
            "method": "GET",
            "header": [
              {
                "key": "Accept",
                "value": "{}",
                "description": "",
                "disabled": false
              }
            ],
            "body": {
              "mode": "raw"
            },
            "description": "Get a sending ip."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "7d0521c3-8039-41bb-a5e5-a2089915e569"
            }
          ]
        }
      ]
    }
  ]
}