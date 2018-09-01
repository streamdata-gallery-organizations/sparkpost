---
swagger: "2.0"
x-collection-name: SparkPost
x-complete: 0
info:
  title: SparkPost Create a Template
  description: |-
    Create a template by providing a **template object** as the POST request body.

    At a minimum, the "name" and "content" fields are required, where content must contain the "from", "subject", and at least one of "html" or "text" fields.

    By default, when a template is referenced in a transmission, it is the published version of that template.  To submit a transmission that uses a draft template, set the transmission field "use_draft_template" to true.  For additional details, see the Transmissions API documentation for Using a Stored Template.


    #### Create Parts

    The following are key points about creating parts in your templates, as shown in the example:

    * The "id" field may be supplied, and it must be unique.

    * By default, templates are created as drafts.  If you would like to directly publish a template upon creation, set the "published" field to true.

    * Open and click tracking may be enable/disabled at the template level using the "open_tracking" and
    "click_tracking" fields.

    * The "from" field may be a JSON object composed of "email" and "name".

    * A "Reply-To" header may be specified using the "reply_to" field.

    * Both "text" and "html" may be provided.

    * Additional headers may be specified in the "headers" JSON dictionary.


    #### Create RFC822

    Fully formed email_rfc822 content may be provided instead of the "text", "html", "from", and "subject" parts, as shown in the example.
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
    put:
      summary: Update a Sending IP
      description: Updates the IP Pool of a sending IP.
      operationId: putSendingIps123.456.789.012
      x-api-path-slug: sendingips123-456-789-012-put
      parameters:
      - in: header
        name: Accept
      - in: body
        name: Body
        schema:
          $ref: '#/definitions/holder'
      - in: header
        name: Content-Type
      responses:
        200:
          description: OK
      tags:
      - Email
      - Sending
      - IP
  /suppression-list:
    get:
      summary: Search for List Entries
      description: Perform a filtered search for entries in your customer-specific
        exclusion list.
      operationId: getSuppressionList
      x-api-path-slug: suppressionlist-get
      parameters:
      - in: header
        name: Accept
      - in: query
        name: from
      - in: query
        name: limit
      - in: query
        name: to
      - in: query
        name: types
      responses:
        200:
          description: OK
      tags:
      - Email
      - SearchList
      - Entries
  /templates:
    get:
      summary: List all Templates
      description: |-
        Lists the most recent version of each template in your account. Each template object in the list will have the following fields:

        - id: Unique template ID

        - name: Template name

        - published: Published state of the template (true = published, false = draft)

        - description: Template description
      operationId: getTemplates
      x-api-path-slug: templates-get
      parameters:
      - in: header
        name: Accept
      responses:
        200:
          description: OK
      tags:
      - Email
      - List
      - ""
      - Templates
    post:
      summary: Create a Template
      description: |-
        Create a template by providing a **template object** as the POST request body.

        At a minimum, the "name" and "content" fields are required, where content must contain the "from", "subject", and at least one of "html" or "text" fields.

        By default, when a template is referenced in a transmission, it is the published version of that template.  To submit a transmission that uses a draft template, set the transmission field "use_draft_template" to true.  For additional details, see the Transmissions API documentation for Using a Stored Template.


        #### Create Parts

        The following are key points about creating parts in your templates, as shown in the example:

        * The "id" field may be supplied, and it must be unique.

        * By default, templates are created as drafts.  If you would like to directly publish a template upon creation, set the "published" field to true.

        * Open and click tracking may be enable/disabled at the template level using the "open_tracking" and
        "click_tracking" fields.

        * The "from" field may be a JSON object composed of "email" and "name".

        * A "Reply-To" header may be specified using the "reply_to" field.

        * Both "text" and "html" may be provided.

        * Additional headers may be specified in the "headers" JSON dictionary.


        #### Create RFC822

        Fully formed email_rfc822 content may be provided instead of the "text", "html", "from", and "subject" parts, as shown in the example.
      operationId: postTemplates
      x-api-path-slug: templates-post
      parameters:
      - in: header
        name: Accept
      - in: body
        name: Body
        schema:
          $ref: '#/definitions/holder'
      - in: header
        name: Content-Type
      responses:
        200:
          description: OK
      tags:
      - Email
      - Template
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