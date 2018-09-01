---
swagger: "2.0"
x-collection-name: SparkPost
x-complete: 0
info:
  title: SparkPost Delay Reason Metrics
  description: Provides deliverability metrics, specific to delay events, grouped
    by the delay reasons.
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
  /metrics/deliverability/rejection-reason:
    get:
      summary: Rejection Reason Metrics
      description: Provides deliverability metrics, specific to rejection events,
        grouped by the rejection reasons.
      operationId: getMetricsDeliverabilityRejectionReason
      x-api-path-slug: metricsdeliverabilityrejectionreason-get
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
  /metrics/deliverability/binding:
    get:
      summary: Deliverability Metrics by Binding
      description: |-
        **Note:** This endpoint is available in SparkPost Elite only.

        Provides aggregate metrics grouped by binding over the time window specified.
      operationId: getMetricsDeliverabilityBinding
      x-api-path-slug: metricsdeliverabilitybinding-get
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
        name: order_by
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
      - Deliverability
      - Metrics
      - By
      - Binding
  /ip-pools/warm_up_ip_pool:
    get:
      summary: Get an IP Pool
      description: Get an ip pool.
      operationId: getIpPoolsWarmUpIpPool
      x-api-path-slug: ippoolswarm-up-ip-pool-get
      parameters:
      - in: header
        name: Accept
      responses:
        200:
          description: OK
      tags:
      - Email
      - IP
      - Pool
    put:
      summary: Update an IP Pool
      description: Update an ip pool.
      operationId: putIpPoolsWarmUpIpPool
      x-api-path-slug: ippoolswarm-up-ip-pool-put
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
    delete:
      summary: Delete an IP Pool
      description: Delete an ip pool.
      operationId: deleteIpPoolsWarmUpIpPool
      x-api-path-slug: ippoolswarm-up-ip-pool-delete
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
      - IP
      - Pool
  /tracking-domains/example.domain.com:
    get:
      summary: Retrieve a Tracking Domain
      description: |-
        Retrieve an existing tracking domain.

        **NOTE:** For SparkPost, port and secure are not returned since they are hard coded values.
      operationId: getTrackingDomainsExample.domain.com
      x-api-path-slug: trackingdomainsexample-domain-com-get
      parameters:
      - in: header
        name: Accept
      responses:
        200:
          description: OK
      tags:
      - Email
      - Retrieve
      - Tracking
      - Domain
    put:
      summary: Update a Tracking Domain
      description: |-
        Update the attributes of an existing tracking domain.  A tracking domain cannot be
        set as the default until it is verified.  If a tracking domain is set to the default,
        and there is already a default domain, the default is changed.

        **NOTE:** For SparkPost, port and secure cannot be updated.
      operationId: putTrackingDomainsExample.domain.com
      x-api-path-slug: trackingdomainsexample-domain-com-put
      parameters:
      - in: header
        name: Accept
      - in: body
        name: Body
        schema:
          $ref: '#/definitions/holder'
      responses:
        200:
          description: OK
      tags:
      - Email
      - Tracking
      - Domain
    delete:
      summary: Delete a Tracking Domain
      description: Delete an existing tracking domain.
      operationId: deleteTrackingDomainsExample.domain.com
      x-api-path-slug: trackingdomainsexample-domain-com-delete
      parameters:
      - in: header
        name: Accept
      responses:
        200:
          description: OK
      tags:
      - Email
      - Tracking
      - Domain
  /recipient-lists/unique_id_4_graduate_students_list:
    put:
      summary: Update a Recipient List
      description: "Update an existing recipient list by specifying its ID in the
        URI path and use a\n**recipient list object** as the PUT request body. Use
        the **num_rcpt_errors** parameter to limit the number of recipient errors\nreturned.\n\nThe
        following are key points about updating your recipient lists:\n\n* If a non-scheduled
        transmission contains a recipient list, the recipient list cannot\nbe updated
        if the transmission is submitted or generating.\n\n* If a scheduled transmission
        contains a recipient list, the recipient list cannot be updated if the transmission
        is\ngenerating or submitted and within 10 minutes of the scheduled generation
        time.  \n\n* The \"id\" field is read only and cannot be changed.  If the
        recipient list \"id\" is provided in\nthe **recipient list object**, it must
        match the id parameter.\n\n* If a \"recipients\" array is provided in the
        update request, it must contain the complete recipient\nlist and all relevant
        recipient fields whether they are being changed or not.  The new recipients\nwill
        completely replace the existing recipients.  The number of accepted recipients
        and the\nnumber of rejected recipients will only be returned if a \"recipients\"
        array is provided in the request.\n\n* If a \"name\" field is provided in
        the update request, it will replace the existing\n\"name\" field for the recipient
        list.\n\n* If a \"description\" field is provided in the update request, it
        will replace the existing\n\"description\" field for the recipient list.\n\n*
        If an \"attributes\" object is provided in the update request, it will completely
        replace the existing\n\"attributes\" object for the recipient list."
      operationId: putRecipientListsUnique4GraduateStudentsList
      x-api-path-slug: recipientlistsunique-id-4-graduate-students-list-put
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
    delete:
      summary: Delete a Recipient List
      description: |-
        Permanently delete the specified recipient list.

        Once a recipient list is deleted, it
        cannot be recovered.  Before deleting a list, ensure that it is no longer needed and keep a backup copy.  If a deleted
        list is needed again, the list must be resubmitted with the CREATE API.

        If a transmission contains a recipient list, the recipient list cannot be deleted if the transmission is
        submitted or generating.
      operationId: deleteRecipientListsUnique4GraduateStudentsList
      x-api-path-slug: recipientlistsunique-id-4-graduate-students-list-delete
      parameters:
      - in: header
        name: Accept
      responses:
        200:
          description: OK
      tags:
      - Email
      - Recipient
      - List
  /webhooks/12affc24-f183-11e3-9234-3c15c2c818c2/validate:
    post:
      summary: Validate a Webhook
      description: |-
        The validation sends an example message event batch from the Webhooks API to the
        target URL, validates that the target responds with HTTP 200,
        and returns detailed information on the response received from the target.

        #### Message Properties

        | Property   | Type   | Description | Required | Notes |
        |------------|--------|-------------|----------|-------|
        | message    | object | Example batch to send | yes | example: `{"msys": {}}`  |
      operationId: postWebhooks12affc24F18311e392343c15c2c818c2Valate
      x-api-path-slug: webhooks12affc24f18311e392343c15c2c818c2validate-post
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
      - Validate
      - Webhook
  /webhooks/events/samples:
    get:
      summary: Samples
      description: |-
        List an example of the event data that will be posted by a Webhook for the specified events.

        **Note:** the data that will arrive at your target URL will **not** contain the top level ``results`` key shown in the example response.
      operationId: getWebhooksEventsSamples
      x-api-path-slug: webhookseventssamples-get
      parameters:
      - in: header
        name: Accept
      - in: query
        name: events
      responses:
        200:
          description: OK
      tags:
      - Email
      - Samples
  /transmissions:
    post:
      summary: Create a Transmission (metadata with stored template and inline recipients)
      description: "You can create a transmission in a number of ways. In all cases,
        you can use the **num_rcpt_errors** parameter to limit the number of recipient
        errors returned.\n\n**Note:** The \"return_path\" in the POST request body
        applies to SparkPost Elite only.\n\n**Note:** Sending limits apply to SparkPost
        only. When a transmission is created in SparkPost, the number of messages
        in the transmission is compared to the sending limit of your account. If the
        transmission will cause you to exceed your sending limit, the entire transmission
        results in an error and no messages are sent.  Note that no messages will
        be sent for the given transmission, regardless of the number of messages that
        caused you to exceed your sending limit. In this case, the Transmission API
        will return an HTTP 420 error code with an error detailing whether you would
        exceed your hourly, daily, or sandbox sending limit. \n\n#### Using Inline
        Email Part Content\n\nCreate a transmission using inline email part content.\n\n####
        Using Inline RFC822 Content\n\nCreate a transmission using inline RFC822 content.
        Content headers are not generated for transmissions providing RFC822 content.
        They are expected to be provided as headers contained in the RFC822 content.\n\n####
        Using a Stored Recipients List\n\nCreate a transmission using a stored recipients
        list by specifying the \"list_id\" in the \"recipients\" attribute.\n\n####
        Using a Stored Template\n\nCreate a transmission using a stored template by
        specifying the \"template_id\" in the \"content\" attribute.  The \"use_draft_template\"
        field is optional and indicates whether to use a draft version or the published
        version of the template when generating messages.\n\n#### Scheduling Transmissions\n\nCreate
        a scheduled transmission to be generated and sent at a future time by specifying
        \"start_time\" in the \"options\" attribute.\n\nScheduling a transmission
        that specifies a stored template will use the LATEST version of the template
        available at the time of scheduled generation.  The use of published versus
        draft versions follows the same logic in all transmission requests, whether
        scheduled or immediate generation. When \"use_draft_template\" is not specified
        (or set to false), the latest published version of the specified stored template
        is used. If \"use_draft_template\" is set to true, the latest draft version
        is used in the transmission instead.\n\nOnce message generation has been initiated,
        all messages in the transmission will use the template selected at the start
        of the generation. If a template update is made during the generation of a
        transmission that uses that template, the template update will succeed but
        the transmission will continue to use the version that was selected at the
        start of the generation."
      operationId: postTransmissions
      x-api-path-slug: transmissions-post
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
      - Transmission
      - (metadata
      - Stored
      - Template
      - Inline
      - Recipients)
  /metrics/deliverability/binding-group:
    get:
      summary: Deliverability Metrics by Binding Group
      description: |-
        **Note:** This endpoint is available in SparkPost Elite only.

        Provides aggregate metrics grouped by binding group over the time window specified.
      operationId: getMetricsDeliverabilityBindingGroup
      x-api-path-slug: metricsdeliverabilitybindinggroup-get
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
        name: order_by
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
      - Deliverability
      - Metrics
      - By
      - Binding
      - Group
  /relay-webhooks:
    get:
      summary: List all Relay Webhooks
      description: List all your relay webhooks.
      operationId: getRelayWebhooks
      x-api-path-slug: relaywebhooks-get
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
      - Relay
      - Webhooks
    post:
      summary: Create a Relay Webhook
      description: Create a relay webhook by providing a **relay webhooks object**
        as the POST request body.
      operationId: postRelayWebhooks
      x-api-path-slug: relaywebhooks-post
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
      - Relay
      - Webhook
  /message-events/events/documentation:
    get:
      summary: Documentation
      description: List descriptions of the event fields that could be included in
        a response from the Message Events search endpoint. Fields will vary by event
        type.
      operationId: getMessageEventsEventsDocumentation
      x-api-path-slug: messageeventseventsdocumentation-get
      parameters:
      - in: header
        name: Accept
      responses:
        200:
          description: OK
      tags:
      - Email
      - Documentation
  /relay-webhooks/12013026328707075:
    get:
      summary: Retrieve a Relay Webhook
      description: Retrieve a specific relay webhook by specifying the webhook ID
        in the URI path.
      operationId: getRelayWebhooks12013026328707075
      x-api-path-slug: relaywebhooks12013026328707075-get
      parameters:
      - in: header
        name: Accept
      responses:
        200:
          description: OK
      tags:
      - Email
      - Retrieve
      - Relay
      - Webhook
    put:
      summary: Update a Relay Webhook
      description: Update a relay webhook by specifying the webhook ID in the URI
        path.
      operationId: putRelayWebhooks12013026328707075
      x-api-path-slug: relaywebhooks12013026328707075-put
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
      - Relay
      - Webhook
    delete:
      summary: Delete a Relay Webhook
      description: Delete a relay webhook by specifying the webhook ID in the URI
        path.
      operationId: deleteRelayWebhooks12013026328707075
      x-api-path-slug: relaywebhooks12013026328707075-delete
      parameters:
      - in: header
        name: Accept
      responses:
        200:
          description: OK
      tags:
      - Email
      - Relay
      - Webhook
  /sending-domains//verify:
    post:
      summary: Verify a Sending Domain
      description: |-
        The verify resource operates differently depending on the provided request fields:

          * Including the fields "dkim_verify" and/or "spf_verify" in the request initiates a check against the associated DNS record type for the specified sending domain.

          * Including the fields "postmaster_at_verify" and/or "abuse_at_verify" in the request results in an email sent to the specified sending domain's postmaster@ and/or abuse@ mailbox where a verification link can be clicked.

          * Including the fields "postmaster_at_token" and/or "abuse_at_token" in the request initiates a check of the provided token(s) against the stored token(s) for the specified sending domain.

        The domain's "status" object is returned on success.
      operationId: postSendingDomainsVerify
      x-api-path-slug: sendingdomainsverify-post
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
      - Verify
      - Sending
      - Domain
  /webhooks/12affc24-f183-11e3-9234-3c15c2c818c2/batch-status:
    get:
      summary: Retrieve Status Information
      description: |-
        Retrieve status information regarding batches that have been generated
        for the given webhook by specifying its id in the URI path. Status information includes the successes of batches
        that previously failed to reach the webhook's target URL and batches that
        are currently in a failed state.
      operationId: getWebhooks12affc24F18311e392343c15c2c818c2BatchStatus
      x-api-path-slug: webhooks12affc24f18311e392343c15c2c818c2batchstatus-get
      parameters:
      - in: header
        name: Accept
      - in: query
        name: limit
      responses:
        200:
          description: OK
      tags:
      - Email
      - Retrieve
      - Status
      - Information
  /metrics/deliverability/watched-domain:
    get:
      summary: Deliverability Metrics by Watched Domain
      description: |-
        Provides aggregate metrics grouped by watched domain over the time window specified. The difference
        between domain and watched domain is that watched domains are comprised of the top 99% domains
        in the world.
      operationId: getMetricsDeliverabilityWatchedDomain
      x-api-path-slug: metricsdeliverabilitywatcheddomain-get
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
        name: order_by
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
      - Deliverability
      - Metrics
      - By
      - Watched
      - Domain
  /webhooks/events/documentation:
    get:
      summary: Documentation
      description: List descriptions of the events, event types, and event fields
        that could be included in a Webhooks post to your target URL.
      operationId: getWebhooksEventsDocumentation
      x-api-path-slug: webhookseventsdocumentation-get
      parameters:
      - in: header
        name: Accept
      responses:
        200:
          description: OK
      tags:
      - Email
      - Documentation
  /metrics/deliverability/campaign:
    get:
      summary: Deliverability Metrics by Campaign
      description: Provides aggregate metrics grouped by campaign over the time window
        specified.
      operationId: getMetricsDeliverabilityCampaign
      x-api-path-slug: metricsdeliverabilitycampaign-get
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
        name: order_by
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
      - Deliverability
      - Metrics
      - By
      - Campaign
  /templates/11714265276872/preview:
    post:
      summary: Preview a Template
      description: |-
        Preview the most recent version of an existing template by specifying {id}/preview in the URI path
        and providing "substitution_data" as part of the POST request body.
        The template's content will be expanded using the substitution data provided and returned
        in the response. By default, the most recently updated version is returned.  Use the **draft** query parameter to specify a draft or published
        template.

        See the Substitutions Reference section for more information.
      operationId: postTemplates11714265276872Preview
      x-api-path-slug: templates11714265276872preview-post
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
        name: draft
      responses:
        200:
          description: OK
      tags:
      - Email
      - Preview
      - Template
  /suppression-list/rcpt_1@example.com:
    get:
      summary: Retrieve a Recipient Suppression Status
      description: "Retrieve the suppression status for a specific recipient by specifying
        the recipient\u2019s email address in the URI path.\n\nIf the recipient is
        not in the customer-specific exclusion list, an HTTP status of 404 is returned.
        If the recipient is in the list, an HTTP status of 200 is returned with the
        full suppression status in the response body.\n\nIn addition to the list entry
        attributes, the response body also includes \"created\" and \"updated\" timestamps."
      operationId: getSuppressionListRcpt1@example.com
      x-api-path-slug: suppressionlistrcpt-1example-com-get
      parameters:
      - in: header
        name: Accept
      responses:
        200:
          description: OK
      tags:
      - Email
      - Retrieve
      - Recipient
      - Suppression
      - Status
    delete:
      summary: Delete a List Entry
      description: |-
        Delete a recipient from the list by specifying the recipient's email address in the URI path.

        If the recipient is not in the customer-specific exclusion list, an HTTP status of 404 is returned. If the recipient is in the list, an HTTP status of 204 is returned indicating a successful deletion.
      operationId: deleteSuppressionListRcpt1@example.com
      x-api-path-slug: suppressionlistrcpt-1example-com-delete
      parameters:
      - in: header
        name: Accept
      responses:
        200:
          description: OK
      tags:
      - Email
      - List
      - Entry
  /transmissions/11714265276872:
    delete:
      summary: Delete a Transmission
      description: |-
        Delete a transmission by specifying its ID in the URI path.

        Only transmissions which are scheduled for future generation may be deleted.

        Scheduled transmissions cannot be deleted if the transmission is within 10 minutes of the scheduled generation time.
      operationId: deleteTransmissions11714265276872
      x-api-path-slug: transmissions11714265276872-delete
      parameters:
      - in: header
        name: Accept
      responses:
        200:
          description: OK
      tags:
      - Email
      - Transmission
  /metrics/deliverability/template:
    get:
      summary: Deliverability Metrics by Template
      description: Provides aggregate metrics grouped by template over the time window
        specified.
      operationId: getMetricsDeliverabilityTemplate
      x-api-path-slug: metricsdeliverabilitytemplate-get
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
        name: order_by
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
      - Deliverability
      - Metrics
      - By
      - Template
  /inbound-domains/inbounddomain.test.com:
    get:
      summary: Retrieve an Inbound Domain
      description: Retrieve an inbound domain by specifying its domain name in the
        URI path.
      operationId: getInboundDomainsInbounddomain.test.com
      x-api-path-slug: inbounddomainsinbounddomain-test-com-get
      parameters:
      - in: header
        name: Accept
      responses:
        200:
          description: OK
      tags:
      - Email
      - Retrieve
      - Inbound
      - Domain
    delete:
      summary: Delete an Inbound Domain
      description: Delete an inbound domain by specifying its domain name in the URI
        path.
      operationId: deleteInboundDomainsInbounddomain.test.com
      x-api-path-slug: inbounddomainsinbounddomain-test-com-delete
      parameters:
      - in: header
        name: Accept
      responses:
        200:
          description: OK
      tags:
      - Email
      - Inbound
      - Domain
  /metrics/deliverability:
    get:
      summary: Deliverability Metrics Summary
      description: |-
        Provides high-level summary of aggregate metrics and lists the child endpoints that contain
        aggregate data, which can be used as "group by" qualifiers.
      operationId: getMetricsDeliverability
      x-api-path-slug: metricsdeliverability-get
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
      - Deliverability
      - Metrics
      - Summary
  /metrics/deliverability/bounce-reason/domain:
    get:
      summary: Bounce Reason Metrics By Domain
      description: Provides deliverability metrics, specific to bounce events, grouped
        by the domain and bounce reasons.
      operationId: getMetricsDeliverabilityBounceReasonDomain
      x-api-path-slug: metricsdeliverabilitybouncereasondomain-get
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
      - Domain
  /subaccounts/:subaccountID:
    get:
      summary: List specific subaccount
      description: Endpoint for retrieving information about a specific subaccount.
      operationId: getSubaccountsSubaccount
      x-api-path-slug: subaccountssubaccountid-get
      parameters:
      - in: header
        name: Accept
      responses:
        200:
          description: OK
      tags:
      - Email
      - List
      - Specific
      - Subaccount
    put:
      summary: Edit a subaccount
      description: |-
        Update an existing subaccount's information. You can update the following information associated with a subaccount:

        #### Request Body Attributes

        | Field   | Required   | Type   | Description                                        | Notes |
        | ------- | ---------- | ------ | -------------------------------------------------- | ----- |
        | name    | no         | string | User friendly identifier for a specific subaccount |       |
        | status  | no         | string | Status of the account                              | Value is one of `active`, `suspended`, or `terminated` |
      operationId: putSubaccountsSubaccount
      x-api-path-slug: subaccountssubaccountid-put
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
      - Edit
      - Subaccount
  /metrics/deliverability/delay-reason:
    get:
      summary: Delay Reason Metrics
      description: Provides deliverability metrics, specific to delay events, grouped
        by the delay reasons.
      operationId: getMetricsDeliverabilityDelayReason
      x-api-path-slug: metricsdeliverabilitydelayreason-get
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
      - Delay
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