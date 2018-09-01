---
swagger: "2.0"
x-collection-name: SparkPost
x-complete: 0
info:
  title: SparkPost Bounce Reason Metrics
  description: Provides deliverability metrics, specific to bounce events, grouped
    by the bounce reasons.
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
  /metrics/protocols:
    get:
      summary: Protocols List
      description: |-
        **Note:** This endpoint is available in SparkPost Elite only.

        Returns a list of protocols that the Metrics API contains data on.
      operationId: getMetricsProtocols
      x-api-path-slug: metricsprotocols-get
      parameters:
      - in: header
        name: Accept
      responses:
        200:
          description: OK
      tags:
      - Email
      - Protocols
      - List
  /subaccounts:
    get:
      summary: List subaccounts
      description: Endpoint for retrieving a list of your subaccounts. This endpoint
        only returns information about the subaccounts themselves, not the data associated
        with the subaccount.
      operationId: getSubaccounts
      x-api-path-slug: subaccounts-get
      parameters:
      - in: header
        name: Accept
      responses:
        200:
          description: OK
      tags:
      - Email
      - List
      - Subaccounts
    post:
      summary: Create new subaccount
      description: |-
        Provisions a new subaccount and an initial subaccount API key. Subaccount API keys are only allowed very
        specific grants, which are limited to: `smtp/inject`, `sending_domains/manage`, `message_events/view` and `suppression_lists/manage`.
        Subaccounts are allowed to send mail using the SMTP protocol, retrieve sending statistics via the Message Events API, and manage their own Sending Domains and Suppression List.

        #### Request Body Attributes

        | Field         | Required   | Type    | Description                                                                                                                   |
        | ------------  | ---------- | ------- | ----------------------------------------------------------------------------------------------------------------------------- |
        | name          | yes        | string  | User friendly identifier for a specific subaccount                                                                            |
        | key_label     | yes        | string  | User friendly identifier for the initial subaccount api key                                                                   |
        | key_grants    | yes        | Array   | List of grants to give to the initial subaccount api key                                                                      |
        | key_valid_ips | no         | Array   | List of IP's that the initial subaccount api key can be used from. If empty array, then api key is usable on any IP address   |
      operationId: postSubaccounts
      x-api-path-slug: subaccounts-post
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
      - New
      - Subaccount
  /sending-ips:
    get:
      summary: Get all Sending IPs
      description: Get all sending ips.
      operationId: getSendingIps
      x-api-path-slug: sendingips-get
      parameters:
      - in: header
        name: Accept
      responses:
        200:
          description: OK
      tags:
      - Email
      - Sending
      - IPs
  /metrics/deliverability/sending-ip:
    get:
      summary: Deliverability Metrics by Sending IP
      description: Deliverability metrics by sending ip.
      operationId: getMetricsDeliverabilitySendingIp
      x-api-path-slug: metricsdeliverabilitysendingip-get
      parameters:
      - in: header
        name: Accept
      - in: query
        name: bindings
      - in: query
        name: binding_groups
      - in: query
        name: campaigns
      - in: query
        name: domains
      - in: query
        name: from
      - in: query
        name: ip_pools
      - in: query
        name: limit
      - in: query
        name: metrics
      - in: query
        name: nodes
      - in: query
        name: order_by
      - in: query
        name: protocols
      - in: query
        name: sending_domains
      - in: query
        name: sending_ips
      - in: query
        name: subaccounts
      - in: query
        name: templates
      - in: query
        name: timezone
      - in: query
        name: to
      responses:
        200:
          description: OK
      tags:
      - Email
      - Deliverability
      - Metrics
      - By
      - Sending
      - IP
  /tracking-domains:
    get:
      summary: List all Tracking Domains
      description: |-
        Retrieve a list of all tracking domains.

        **NOTE:** For SparkPost, port and secure are not returned since they are hard coded values.
      operationId: getTrackingDomains
      x-api-path-slug: trackingdomains-get
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
      - Tracking
      - Domains
    post:
      summary: Create a Tracking Domain
      description: |-
        Create a tracking domain. A tracking domain cannot be set as the default until it is verified.

        **NOTE:** For SparkPost, only domain is required in the POST request body. The values for port (80) and secure (false) are not configurable.
      operationId: postTrackingDomains
      x-api-path-slug: trackingdomains-post
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
      - Tracking
      - Domain
  /bounce-domains/example.domain.com/verify:
    post:
      summary: Verify a Bounce Domain
      description: Verify a bounce domain.
      operationId: postBounceDomainsExample.domain.comVerify
      x-api-path-slug: bouncedomainsexample-domain-comverify-post
      parameters:
      - in: header
        name: Accept
      - in: header
        name: Content-Type
      responses:
        200:
          description: OK
      tags:
      - Email
      - Verify
      - Bounce
      - Domain
  /recipient-lists:
    get:
      summary: List all Recipient Lists
      description: |-
        List a summary of all recipient lists.  The recipients for each list are not included in the
        results.  To retrieve recipient details, use the RETRIEVE API for a specified recipient list.
      operationId: getRecipientLists
      x-api-path-slug: recipientlists-get
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
      - Recipient
      - Lists
    post:
      summary: Create a Recipient List
      description: |-
        Create a recipient list by providing a **recipient list object** as the POST request body.

        At a minimum, the "recipients" array is required, which must contain a valid "address".  If the
        recipient list "id" is not provided in the POST request body, one will be generated and returned
        in the results body.  Use the **num_rcpt_errors** parameter to limit the number of recipient errors
        returned.

        **Note:** The "return_path" in the POST request body applies to SparkPost Elite only.
      operationId: postRecipientLists
      x-api-path-slug: recipientlists-post
      parameters:
      - in: header
        name: Accept
      - in: body
        name: Body
        schema:
          $ref: '#/definitions/holder'
      - in: header
        name: Content-Type
      - in: query
        name: num_rcpt_errors
      responses:
        200:
          description: OK
      tags:
      - Email
      - Recipient
      - List
  /message-events:
    get:
      summary: Search for Message Events
      description: Perform a filtered search for message event data. The response
        is sorted by descending timestamp.
      operationId: getMessageEvents
      x-api-path-slug: messageevents-get
      parameters:
      - in: header
        name: Accept
      - in: query
        name: bounce_classes
      - in: query
        name: campaign_ids
      - in: query
        name: events
      - in: query
        name: friendly_froms
      - in: query
        name: from
      - in: query
        name: message_ids
      - in: query
        name: page
      - in: query
        name: per_page
      - in: query
        name: reason
      - in: query
        name: recipients
      - in: query
        name: template_ids
      - in: query
        name: timezone
      - in: query
        name: to
      - in: query
        name: transmission_ids
      responses:
        200:
          description: OK
      tags:
      - Email
      - SearchMessage
      - Events
  /ip-pools:
    get:
      summary: List all IP Pools
      description: List all ip pools.
      operationId: getIpPools
      x-api-path-slug: ippools-get
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
      - IP
      - Pools
    post:
      summary: Create an IP Pool
      description: Create an ip pool.
      operationId: postIpPools
      x-api-path-slug: ippools-post
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
      - IP
      - Pool
  /templates/11714265276872:
    get:
      summary: Retrieve a Template
      description: |-
        Retrieve a single template by specifying its ID in the URI path. By default, the most recently
        updated version is returned. Use the **draft** query parameter to specify a draft or published
        template.


        The result will include a "last_update_time" field. The "last_update_time" is the time the template was last updated, for both draft and published versions.

        If the template was used for message generation, the result will also include a "last_use" field. The "last_use" time represents the last time any version of this template was used (draft or published).
      operationId: getTemplates11714265276872
      x-api-path-slug: templates11714265276872-get
      parameters:
      - in: header
        name: Accept
      - in: query
        name: draft
      responses:
        200:
          description: OK
      tags:
      - Email
      - Retrieve
      - Template
    put:
      summary: Update a Template
      description: |-
        Update an existing template by specifying its ID in the URI path and use a **template object** as the PUT request body.
        By default, the update will result in a new draft version, but the published version can be overwritten directly by using the **update_published** query parameter.

        The "name" field may be modified, but the "id" field is read only.

        If a content object is provided in the update request, it must
        contain all relevant content fields whether they are being changed or not.
        The new content will completely overwrite the existing content.

        The example shows an update that will rename the template, enable open tracking,
        and update the content all in one API call. All content fields are included whether they are being
        changed or not.

        Publishing a template is a specific case of an update.  The body of the PUT
        request should contain the `"published": true` field as shown in the example. The
        **update_published** query parameter does not apply.
      operationId: putTemplates11714265276872
      x-api-path-slug: templates11714265276872-put
      parameters:
      - in: body
        name: Body
        schema:
          $ref: '#/definitions/holder'
      - in: header
        name: Content-Type
      - in: query
        name: update_published
      responses:
        200:
          description: OK
      tags:
      - Email
      - Template
    delete:
      summary: Delete a Template
      description: |-
        Delete a template by specifying its ID in the URI path.
        If the template delete API call succeeds, then ALL versions of the template will be deleted from the system (both published AND draft versions).

        If a transmission uses a stored template, the template cannot be deleted if the transmission is submitted or generating.
      operationId: deleteTemplates11714265276872
      x-api-path-slug: templates11714265276872-delete
      parameters:
      - in: header
        name: Accept
      responses:
        200:
          description: OK
      tags:
      - Email
      - Template
  /bounce-domains/example.domain.com:
    get:
      summary: Retrieve a Bounce Domain
      description: Retrieve a bounce domain.
      operationId: getBounceDomainsExample.domain.com
      x-api-path-slug: bouncedomainsexample-domain-com-get
      parameters:
      - in: header
        name: Accept
      responses:
        200:
          description: OK
      tags:
      - Email
      - Retrieve
      - Bounce
      - Domain
    delete:
      summary: Delete a Bounce Domain
      description: Delete a bounce domain.
      operationId: deleteBounceDomainsExample.domain.com
      x-api-path-slug: bouncedomainsexample-domain-com-delete
      parameters:
      - in: header
        name: Accept
      responses:
        200:
          description: OK
      tags:
      - Email
      - Bounce
      - Domain
  /metrics/deliverability/link-name:
    get:
      summary: Engagement Details
      description: |-
        Provides deliverability metrics, specific to engagement events (clicks/opens), grouped by the link
        name (or URL if no link name exists).
      operationId: getMetricsDeliverabilityLinkName
      x-api-path-slug: metricsdeliverabilitylinkname-get
      parameters:
      - in: header
        name: Accept
      - in: query
        name: campaigns
      - in: query
        name: from
      - in: query
        name: limit
      - in: query
        name: metrics
      - in: query
        name: templates
      - in: query
        name: timezone
      - in: query
        name: to
      responses:
        200:
          description: OK
      tags:
      - Email
      - Engagement
      - Details
  /sending-domains/example1.com:
    get:
      summary: Retrieve a Sending Domain
      description: Retrieve a sending domain by specifying its domain name in the
        URI path.  The response includes details about its DKIM key configuration.
      operationId: getSendingDomainsExample1.com
      x-api-path-slug: sendingdomainsexample1-com-get
      parameters:
      - in: header
        name: Accept
      responses:
        200:
          description: OK
      tags:
      - Email
      - Retrieve
      - Sending
      - Domain
    put:
      summary: Update a Sending Domain
      description: |-
        Update the attributes of an existing sending domain by specifying its domain name in the URI path and use a **sending domain object** as the PUT request body.

        If a tracking domain is specified, it will replace any currently specified tracking domain.  If the supplied tracking domain is a blank string, it will clear any currently specified tracking domain. Note that if a tracking domain is not specified, any currently specified tracking domain will remain intact.

        If a dkim object is provided in the update request, it must contain all relevant fields whether they are being changed or not.  The new dkim object will completely overwrite the existing one.

        To remove the DKIM Signing Domain Identifier for a Sending Domain, use the empty string for the value of the dkim.signing_domain field. ( **Note**: dkim.signing_domain is only available in SparkPost Elite. )
      operationId: putSendingDomainsExample1.com
      x-api-path-slug: sendingdomainsexample1-com-put
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
      - Domain
    delete:
      summary: Delete a Sending Domain
      description: |-
        Delete an existing sending domain.

        **Warning:** Before deleting a sending domain please ensure you are no longer using it. After deleting a sending domain, any new transmissions that use it will result in a rejection. This includes any transmissions that are in progress, scheduled for the future, or use a stored template referencing the sending domain.
      operationId: deleteSendingDomainsExample1.com
      x-api-path-slug: sendingdomainsexample1-com-delete
      parameters:
      - in: header
        name: Accept
      responses:
        200:
          description: OK
      tags:
      - Email
      - Sending
      - Domain
  /metrics/:
    get:
      summary: Metrics Discoverability Links
      description: |-
        Provides links to all child URIs within the Metrics API.

        **Note:** Links in the response for binding-groups, bindings, nodes, and protocols apply to SparkPost Elite only.
      operationId: getMetrics
      x-api-path-slug: metrics-get
      parameters:
      - in: header
        name: Accept
      responses:
        200:
          description: OK
      tags:
      - Email
      - Metrics
      - Discoverability
      - Links
  /sending-domains:
    get:
      summary: List all Sending Domains
      description: List an overview of all sending domains in the system.
      operationId: getSendingDomains
      x-api-path-slug: sendingdomains-get
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
      - Sending
      - Domains
    post:
      summary: Create a Sending Domain
      description: |-
        Create a sending domain by providing a **sending domain object** as the POST request body.

        **Note**: For some SparkPost Elite customers, Sending Domains will be set to verified automatically when they are created, and can be used to send messages immediately. For these customers, there is no need to use the "verify" endpoint to verify Sending Domains. To find out if this applies in your SparkPost Elite environment, please contact support <support@sparkpostelite.com>, or contact your TAM.
      operationId: postSendingDomains
      x-api-path-slug: sendingdomains-post
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
      - Domain
  /account:
    get:
      summary: Retrieve Account Usage
      description: Retrieve account usage.
      operationId: getAccount
      x-api-path-slug: account-get
      parameters:
      - in: query
        name: include
      responses:
        200:
          description: OK
      tags:
      - Email
      - Retrieve
      - Account
      - Usage
  /metrics/deliverability/rejection-reason/domain:
    get:
      summary: Rejection Reason Metrics By Domain
      description: Provides deliverability metrics, specific to rejection events,
        grouped by the domain and rejection reasons.
      operationId: getMetricsDeliverabilityRejectionReasonDomain
      x-api-path-slug: metricsdeliverabilityrejectionreasondomain-get
      parameters:
      - in: header
        name: Accept
      - in: query
        name: bindings
      - in: query
        name: binding_groups
      - in: query
        name: campaigns
      - in: query
        name: domains
      - in: query
        name: from
      - in: query
        name: limit
      - in: query
        name: nodes
      - in: query
        name: protocols
      - in: query
        name: templates
      - in: query
        name: timezone
      - in: query
        name: to
      responses:
        200:
          description: OK
      tags:
      - Email
      - Rejection
      - Reason
      - Metrics
      - Domain
  /metrics/deliverability/bounce-reason:
    get:
      summary: Bounce Reason Metrics
      description: Provides deliverability metrics, specific to bounce events, grouped
        by the bounce reasons.
      operationId: getMetricsDeliverabilityBounceReason
      x-api-path-slug: metricsdeliverabilitybouncereason-get
      parameters:
      - in: header
        name: Accept
      - in: query
        name: bindings
      - in: query
        name: binding_groups
      - in: query
        name: campaigns
      - in: query
        name: domains
      - in: query
        name: from
      - in: query
        name: limit
      - in: query
        name: metrics
      - in: query
        name: nodes
      - in: query
        name: protocols
      - in: query
        name: templates
      - in: query
        name: timezone
      - in: query
        name: to
      responses:
        200:
          description: OK
      tags:
      - Email
      - Bounce
      - Reason
      - Metrics
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