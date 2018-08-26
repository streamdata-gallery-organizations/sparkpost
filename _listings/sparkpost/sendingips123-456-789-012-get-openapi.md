---
swagger: "2.0"
x-collection-name: SparkPost
x-complete: 0
info:
  title: SparkPost Get a Sending IP
  description: Get a sending ip.
  version: 1.0.0
host: api.sparkpost.com
basePath: /api/v1
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /sending-ips/123.456.789.012:
    get:
      summary: Get a Sending IP
      description: Get a sending ip.
      operationId: getSendingIps123.456.789.012
      x-api-path-slug: sendingips123-456-789-012-get
      parameters:
      - in: header
        name: Accept
      responses:
        200:
          description: OK
      tags:
      - Email
      - Sending
      - IP
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