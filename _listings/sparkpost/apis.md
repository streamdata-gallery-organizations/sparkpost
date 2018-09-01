---
name: SparkPost
x-slug: sparkpost
description: Deliver your app and website emails on time and to the inbox. Trusted
  to send 25% of the worlds non-spam email. Email delivery for companies big and small.
image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/20663-sparkpost.jpg
x-kinRank: "6"
x-alexaRank: "68202"
tags: SparkPost
created: "2018-08-31"
modified: "2018-08-31"
url: https://raw.githubusercontent.com/streamdata-gallery-organizations/sparkpost/master/_listings/sparkpost/apis.md
specificationVersion: "0.14"
apis:
- name: SparkPost API - Get a Sending IP
  x-api-slug: sendingips123-456-789-012-get
  description: Get a sending ip.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/20663-sparkpost.jpg
  humanURL: http://sparkpost.com
  baseURL: https://api.sparkpost.com//api/v1
  tags: Marketing, Emails, New, Technology, SaaS, Mobile, Webhook Implementations
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/sparkpost/master/_listings/sparkpost/sendingips123-456-789-012-get-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/sparkpost/master/_listings/sparkpost/sendingips123-456-789-012-get-openapi.md
- name: SparkPost API - Update a Sending IP
  x-api-slug: sendingips123-456-789-012-put
  description: Updates the IP Pool of a sending IP.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/20663-sparkpost.jpg
  humanURL: http://sparkpost.com
  baseURL: https://api.sparkpost.com//api/v1
  tags: Marketing, Emails, New, Technology, SaaS, Mobile, Webhook Implementations
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/sparkpost/master/_listings/sparkpost/sendingips123-456-789-012-put-openapi.md
- name: SparkPost API - Search for List Entries
  x-api-slug: suppressionlist-get
  description: Perform a filtered search for entries in your customer-specific exclusion
    list.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/20663-sparkpost.jpg
  humanURL: http://sparkpost.com
  baseURL: https://api.sparkpost.com//api/v1
  tags: Marketing, Emails, New, Technology, SaaS, Mobile, Webhook Implementations
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/sparkpost/master/_listings/sparkpost/suppressionlist-get-openapi.md
- name: SparkPost API - List all Templates
  x-api-slug: templates-get
  description: |-
    Lists the most recent version of each template in your account. Each template object in the list will have the following fields:

    - id: Unique template ID

    - name: Template name

    - published: Published state of the template (true = published, false = draft)

    - description: Template description
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/20663-sparkpost.jpg
  humanURL: http://sparkpost.com
  baseURL: https://api.sparkpost.com//api/v1
  tags: Marketing, Emails, New, Technology, SaaS, Mobile, Webhook Implementations
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/sparkpost/master/_listings/sparkpost/templates-get-openapi.md
- name: SparkPost API - Create a Template
  x-api-slug: templates-post
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
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/20663-sparkpost.jpg
  humanURL: http://sparkpost.com
  baseURL: https://api.sparkpost.com//api/v1
  tags: Marketing, Emails, New, Technology, SaaS, Mobile, Webhook Implementations
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/sparkpost/master/_listings/sparkpost/templates-post-openapi.md
- name: SparkPost API - Protocols List
  x-api-slug: metricsprotocols-get
  description: |-
    **Note:** This endpoint is available in SparkPost Elite only.

    Returns a list of protocols that the Metrics API contains data on.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/20663-sparkpost.jpg
  humanURL: http://sparkpost.com
  baseURL: https://api.sparkpost.com//api/v1
  tags: Marketing, Emails, New, Technology, SaaS, Mobile, Webhook Implementations
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/sparkpost/master/_listings/sparkpost/metricsprotocols-get-openapi.md
- name: SparkPost API - List subaccounts
  x-api-slug: subaccounts-get
  description: Endpoint for retrieving a list of your subaccounts. This endpoint only
    returns information about the subaccounts themselves, not the data associated
    with the subaccount.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/20663-sparkpost.jpg
  humanURL: http://sparkpost.com
  baseURL: https://api.sparkpost.com//api/v1
  tags: Marketing, Emails, New, Technology, SaaS, Mobile, Webhook Implementations
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/sparkpost/master/_listings/sparkpost/subaccounts-get-openapi.md
- name: SparkPost API - Create new subaccount
  x-api-slug: subaccounts-post
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
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/20663-sparkpost.jpg
  humanURL: http://sparkpost.com
  baseURL: https://api.sparkpost.com//api/v1
  tags: Marketing, Emails, New, Technology, SaaS, Mobile, Webhook Implementations
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/sparkpost/master/_listings/sparkpost/subaccounts-post-openapi.md
- name: SparkPost API - Get all Sending IPs
  x-api-slug: sendingips-get
  description: Get all sending ips.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/20663-sparkpost.jpg
  humanURL: http://sparkpost.com
  baseURL: https://api.sparkpost.com//api/v1
  tags: Marketing, Emails, New, Technology, SaaS, Mobile, Webhook Implementations
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/sparkpost/master/_listings/sparkpost/sendingips-get-openapi.md
- name: SparkPost API - Deliverability Metrics by Sending IP
  x-api-slug: metricsdeliverabilitysendingip-get
  description: Deliverability metrics by sending ip.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/20663-sparkpost.jpg
  humanURL: http://sparkpost.com
  baseURL: https://api.sparkpost.com//api/v1
  tags: Marketing, Emails, New, Technology, SaaS, Mobile, Webhook Implementations
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/sparkpost/master/_listings/sparkpost/metricsdeliverabilitysendingip-get-openapi.md
- name: SparkPost API - List all Tracking Domains
  x-api-slug: trackingdomains-get
  description: |-
    Retrieve a list of all tracking domains.

    **NOTE:** For SparkPost, port and secure are not returned since they are hard coded values.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/20663-sparkpost.jpg
  humanURL: http://sparkpost.com
  baseURL: https://api.sparkpost.com//api/v1
  tags: Marketing, Emails, New, Technology, SaaS, Mobile, Webhook Implementations
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/sparkpost/master/_listings/sparkpost/trackingdomains-get-openapi.md
- name: SparkPost API - Create a Tracking Domain
  x-api-slug: trackingdomains-post
  description: |-
    Create a tracking domain. A tracking domain cannot be set as the default until it is verified.

    **NOTE:** For SparkPost, only domain is required in the POST request body. The values for port (80) and secure (false) are not configurable.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/20663-sparkpost.jpg
  humanURL: http://sparkpost.com
  baseURL: https://api.sparkpost.com//api/v1
  tags: Marketing, Emails, New, Technology, SaaS, Mobile, Webhook Implementations
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/sparkpost/master/_listings/sparkpost/trackingdomains-post-openapi.md
- name: SparkPost API - Verify a Bounce Domain
  x-api-slug: bouncedomainsexample-domain-comverify-post
  description: Verify a bounce domain.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/20663-sparkpost.jpg
  humanURL: http://sparkpost.com
  baseURL: https://api.sparkpost.com//api/v1
  tags: Marketing, Emails, New, Technology, SaaS, Mobile, Webhook Implementations
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/sparkpost/master/_listings/sparkpost/bouncedomainsexample-domain-comverify-post-openapi.md
- name: SparkPost API - List all Recipient Lists
  x-api-slug: recipientlists-get
  description: |-
    List a summary of all recipient lists.  The recipients for each list are not included in the
    results.  To retrieve recipient details, use the RETRIEVE API for a specified recipient list.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/20663-sparkpost.jpg
  humanURL: http://sparkpost.com
  baseURL: https://api.sparkpost.com//api/v1
  tags: Marketing, Emails, New, Technology, SaaS, Mobile, Webhook Implementations
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/sparkpost/master/_listings/sparkpost/recipientlists-get-openapi.md
- name: SparkPost API - Create a Recipient List
  x-api-slug: recipientlists-post
  description: |-
    Create a recipient list by providing a **recipient list object** as the POST request body.

    At a minimum, the "recipients" array is required, which must contain a valid "address".  If the
    recipient list "id" is not provided in the POST request body, one will be generated and returned
    in the results body.  Use the **num_rcpt_errors** parameter to limit the number of recipient errors
    returned.

    **Note:** The "return_path" in the POST request body applies to SparkPost Elite only.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/20663-sparkpost.jpg
  humanURL: http://sparkpost.com
  baseURL: https://api.sparkpost.com//api/v1
  tags: Marketing, Emails, New, Technology, SaaS, Mobile, Webhook Implementations
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/sparkpost/master/_listings/sparkpost/recipientlists-post-openapi.md
- name: SparkPost API - Search for Message Events
  x-api-slug: messageevents-get
  description: Perform a filtered search for message event data. The response is sorted
    by descending timestamp.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/20663-sparkpost.jpg
  humanURL: http://sparkpost.com
  baseURL: https://api.sparkpost.com//api/v1
  tags: Marketing, Emails, New, Technology, SaaS, Mobile, Webhook Implementations
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/sparkpost/master/_listings/sparkpost/messageevents-get-openapi.md
- name: SparkPost API - List all IP Pools
  x-api-slug: ippools-get
  description: List all ip pools.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/20663-sparkpost.jpg
  humanURL: http://sparkpost.com
  baseURL: https://api.sparkpost.com//api/v1
  tags: Marketing, Emails, New, Technology, SaaS, Mobile, Webhook Implementations
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/sparkpost/master/_listings/sparkpost/ippools-get-openapi.md
- name: SparkPost API - Create an IP Pool
  x-api-slug: ippools-post
  description: Create an ip pool.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/20663-sparkpost.jpg
  humanURL: http://sparkpost.com
  baseURL: https://api.sparkpost.com//api/v1
  tags: Marketing, Emails, New, Technology, SaaS, Mobile, Webhook Implementations
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/sparkpost/master/_listings/sparkpost/ippools-post-openapi.md
- name: SparkPost API - Retrieve a Template
  x-api-slug: templates11714265276872-get
  description: |-
    Retrieve a single template by specifying its ID in the URI path. By default, the most recently
    updated version is returned. Use the **draft** query parameter to specify a draft or published
    template.


    The result will include a "last_update_time" field. The "last_update_time" is the time the template was last updated, for both draft and published versions.

    If the template was used for message generation, the result will also include a "last_use" field. The "last_use" time represents the last time any version of this template was used (draft or published).
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/20663-sparkpost.jpg
  humanURL: http://sparkpost.com
  baseURL: https://api.sparkpost.com//api/v1
  tags: Marketing, Emails, New, Technology, SaaS, Mobile, Webhook Implementations
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/sparkpost/master/_listings/sparkpost/templates11714265276872-get-openapi.md
- name: SparkPost API - Update a Template
  x-api-slug: templates11714265276872-put
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
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/20663-sparkpost.jpg
  humanURL: http://sparkpost.com
  baseURL: https://api.sparkpost.com//api/v1
  tags: Marketing, Emails, New, Technology, SaaS, Mobile, Webhook Implementations
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/sparkpost/master/_listings/sparkpost/templates11714265276872-put-openapi.md
- name: SparkPost API - Delete a Template
  x-api-slug: templates11714265276872-delete
  description: |-
    Delete a template by specifying its ID in the URI path.
    If the template delete API call succeeds, then ALL versions of the template will be deleted from the system (both published AND draft versions).

    If a transmission uses a stored template, the template cannot be deleted if the transmission is submitted or generating.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/20663-sparkpost.jpg
  humanURL: http://sparkpost.com
  baseURL: https://api.sparkpost.com//api/v1
  tags: Marketing, Emails, New, Technology, SaaS, Mobile, Webhook Implementations
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/sparkpost/master/_listings/sparkpost/templates11714265276872-delete-openapi.md
- name: SparkPost API - Retrieve a Bounce Domain
  x-api-slug: bouncedomainsexample-domain-com-get
  description: Retrieve a bounce domain.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/20663-sparkpost.jpg
  humanURL: http://sparkpost.com
  baseURL: https://api.sparkpost.com//api/v1
  tags: Marketing, Emails, New, Technology, SaaS, Mobile, Webhook Implementations
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/sparkpost/master/_listings/sparkpost/bouncedomainsexample-domain-com-get-openapi.md
- name: SparkPost API - Delete a Bounce Domain
  x-api-slug: bouncedomainsexample-domain-com-delete
  description: Delete a bounce domain.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/20663-sparkpost.jpg
  humanURL: http://sparkpost.com
  baseURL: https://api.sparkpost.com//api/v1
  tags: Marketing, Emails, New, Technology, SaaS, Mobile, Webhook Implementations
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/sparkpost/master/_listings/sparkpost/bouncedomainsexample-domain-com-delete-openapi.md
- name: SparkPost API - Engagement Details
  x-api-slug: metricsdeliverabilitylinkname-get
  description: |-
    Provides deliverability metrics, specific to engagement events (clicks/opens), grouped by the link
    name (or URL if no link name exists).
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/20663-sparkpost.jpg
  humanURL: http://sparkpost.com
  baseURL: https://api.sparkpost.com//api/v1
  tags: Marketing, Emails, New, Technology, SaaS, Mobile, Webhook Implementations
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/sparkpost/master/_listings/sparkpost/metricsdeliverabilitylinkname-get-openapi.md
- name: SparkPost API - Retrieve a Sending Domain
  x-api-slug: sendingdomainsexample1-com-get
  description: Retrieve a sending domain by specifying its domain name in the URI
    path.  The response includes details about its DKIM key configuration.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/20663-sparkpost.jpg
  humanURL: http://sparkpost.com
  baseURL: https://api.sparkpost.com//api/v1
  tags: Marketing, Emails, New, Technology, SaaS, Mobile, Webhook Implementations
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/sparkpost/master/_listings/sparkpost/sendingdomainsexample1-com-get-openapi.md
- name: SparkPost API - Update a Sending Domain
  x-api-slug: sendingdomainsexample1-com-put
  description: |-
    Update the attributes of an existing sending domain by specifying its domain name in the URI path and use a **sending domain object** as the PUT request body.

    If a tracking domain is specified, it will replace any currently specified tracking domain.  If the supplied tracking domain is a blank string, it will clear any currently specified tracking domain. Note that if a tracking domain is not specified, any currently specified tracking domain will remain intact.

    If a dkim object is provided in the update request, it must contain all relevant fields whether they are being changed or not.  The new dkim object will completely overwrite the existing one.

    To remove the DKIM Signing Domain Identifier for a Sending Domain, use the empty string for the value of the dkim.signing_domain field. ( **Note**: dkim.signing_domain is only available in SparkPost Elite. )
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/20663-sparkpost.jpg
  humanURL: http://sparkpost.com
  baseURL: https://api.sparkpost.com//api/v1
  tags: Marketing, Emails, New, Technology, SaaS, Mobile, Webhook Implementations
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/sparkpost/master/_listings/sparkpost/sendingdomainsexample1-com-put-openapi.md
- name: SparkPost API - Delete a Sending Domain
  x-api-slug: sendingdomainsexample1-com-delete
  description: |-
    Delete an existing sending domain.

    **Warning:** Before deleting a sending domain please ensure you are no longer using it. After deleting a sending domain, any new transmissions that use it will result in a rejection. This includes any transmissions that are in progress, scheduled for the future, or use a stored template referencing the sending domain.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/20663-sparkpost.jpg
  humanURL: http://sparkpost.com
  baseURL: https://api.sparkpost.com//api/v1
  tags: Marketing, Emails, New, Technology, SaaS, Mobile, Webhook Implementations
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/sparkpost/master/_listings/sparkpost/sendingdomainsexample1-com-delete-openapi.md
- name: SparkPost API - Metrics Discoverability Links
  x-api-slug: metrics-get
  description: |-
    Provides links to all child URIs within the Metrics API.

    **Note:** Links in the response for binding-groups, bindings, nodes, and protocols apply to SparkPost Elite only.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/20663-sparkpost.jpg
  humanURL: http://sparkpost.com
  baseURL: https://api.sparkpost.com//api/v1
  tags: Marketing, Emails, New, Technology, SaaS, Mobile, Webhook Implementations
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/sparkpost/master/_listings/sparkpost/metrics-get-openapi.md
- name: SparkPost API - List all Sending Domains
  x-api-slug: sendingdomains-get
  description: List an overview of all sending domains in the system.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/20663-sparkpost.jpg
  humanURL: http://sparkpost.com
  baseURL: https://api.sparkpost.com//api/v1
  tags: Marketing, Emails, New, Technology, SaaS, Mobile, Webhook Implementations
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/sparkpost/master/_listings/sparkpost/sendingdomains-get-openapi.md
- name: SparkPost API - Create a Sending Domain
  x-api-slug: sendingdomains-post
  description: |-
    Create a sending domain by providing a **sending domain object** as the POST request body.

    **Note**: For some SparkPost Elite customers, Sending Domains will be set to verified automatically when they are created, and can be used to send messages immediately. For these customers, there is no need to use the "verify" endpoint to verify Sending Domains. To find out if this applies in your SparkPost Elite environment, please contact support <support@sparkpostelite.com>, or contact your TAM.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/20663-sparkpost.jpg
  humanURL: http://sparkpost.com
  baseURL: https://api.sparkpost.com//api/v1
  tags: Marketing, Emails, New, Technology, SaaS, Mobile, Webhook Implementations
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/sparkpost/master/_listings/sparkpost/sendingdomains-post-openapi.md
- name: SparkPost API - Retrieve Account Usage
  x-api-slug: account-get
  description: Retrieve account usage.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/20663-sparkpost.jpg
  humanURL: http://sparkpost.com
  baseURL: https://api.sparkpost.com//api/v1
  tags: Marketing, Emails, New, Technology, SaaS, Mobile, Webhook Implementations
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/sparkpost/master/_listings/sparkpost/account-get-openapi.md
- name: SparkPost API - Rejection Reason Metrics By Domain
  x-api-slug: metricsdeliverabilityrejectionreasondomain-get
  description: Provides deliverability metrics, specific to rejection events, grouped
    by the domain and rejection reasons.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/20663-sparkpost.jpg
  humanURL: http://sparkpost.com
  baseURL: https://api.sparkpost.com//api/v1
  tags: Marketing, Emails, New, Technology, SaaS, Mobile, Webhook Implementations
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/sparkpost/master/_listings/sparkpost/metricsdeliverabilityrejectionreasondomain-get-openapi.md
- name: SparkPost API - Bounce Reason Metrics
  x-api-slug: metricsdeliverabilitybouncereason-get
  description: Provides deliverability metrics, specific to bounce events, grouped
    by the bounce reasons.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/20663-sparkpost.jpg
  humanURL: http://sparkpost.com
  baseURL: https://api.sparkpost.com//api/v1
  tags: Marketing, Emails, New, Technology, SaaS, Mobile, Webhook Implementations
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/sparkpost/master/_listings/sparkpost/metricsdeliverabilitybouncereason-get-openapi.md
- name: SparkPost API - Rejection Reason Metrics
  x-api-slug: metricsdeliverabilityrejectionreason-get
  description: Provides deliverability metrics, specific to rejection events, grouped
    by the rejection reasons.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/20663-sparkpost.jpg
  humanURL: http://sparkpost.com
  baseURL: https://api.sparkpost.com//api/v1
  tags: Marketing, Emails, New, Technology, SaaS, Mobile, Webhook Implementations
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/sparkpost/master/_listings/sparkpost/metricsdeliverabilityrejectionreason-get-openapi.md
- name: SparkPost API - Deliverability Metrics by Binding
  x-api-slug: metricsdeliverabilitybinding-get
  description: |-
    **Note:** This endpoint is available in SparkPost Elite only.

    Provides aggregate metrics grouped by binding over the time window specified.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/20663-sparkpost.jpg
  humanURL: http://sparkpost.com
  baseURL: https://api.sparkpost.com//api/v1
  tags: Marketing, Emails, New, Technology, SaaS, Mobile, Webhook Implementations
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/sparkpost/master/_listings/sparkpost/metricsdeliverabilitybinding-get-openapi.md
- name: SparkPost API - Get an IP Pool
  x-api-slug: ippoolswarm-up-ip-pool-get
  description: Get an ip pool.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/20663-sparkpost.jpg
  humanURL: http://sparkpost.com
  baseURL: https://api.sparkpost.com//api/v1
  tags: Marketing, Emails, New, Technology, SaaS, Mobile, Webhook Implementations
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/sparkpost/master/_listings/sparkpost/ippoolswarm-up-ip-pool-get-openapi.md
- name: SparkPost API - Update an IP Pool
  x-api-slug: ippoolswarm-up-ip-pool-put
  description: Update an ip pool.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/20663-sparkpost.jpg
  humanURL: http://sparkpost.com
  baseURL: https://api.sparkpost.com//api/v1
  tags: Marketing, Emails, New, Technology, SaaS, Mobile, Webhook Implementations
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/sparkpost/master/_listings/sparkpost/ippoolswarm-up-ip-pool-put-openapi.md
- name: SparkPost API - Delete an IP Pool
  x-api-slug: ippoolswarm-up-ip-pool-delete
  description: Delete an ip pool.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/20663-sparkpost.jpg
  humanURL: http://sparkpost.com
  baseURL: https://api.sparkpost.com//api/v1
  tags: Marketing, Emails, New, Technology, SaaS, Mobile, Webhook Implementations
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/sparkpost/master/_listings/sparkpost/ippoolswarm-up-ip-pool-delete-openapi.md
- name: SparkPost API - Retrieve a Tracking Domain
  x-api-slug: trackingdomainsexample-domain-com-get
  description: |-
    Retrieve an existing tracking domain.

    **NOTE:** For SparkPost, port and secure are not returned since they are hard coded values.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/20663-sparkpost.jpg
  humanURL: http://sparkpost.com
  baseURL: https://api.sparkpost.com//api/v1
  tags: Marketing, Emails, New, Technology, SaaS, Mobile, Webhook Implementations
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/sparkpost/master/_listings/sparkpost/trackingdomainsexample-domain-com-get-openapi.md
- name: SparkPost API - Update a Tracking Domain
  x-api-slug: trackingdomainsexample-domain-com-put
  description: |-
    Update the attributes of an existing tracking domain.  A tracking domain cannot be
    set as the default until it is verified.  If a tracking domain is set to the default,
    and there is already a default domain, the default is changed.

    **NOTE:** For SparkPost, port and secure cannot be updated.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/20663-sparkpost.jpg
  humanURL: http://sparkpost.com
  baseURL: https://api.sparkpost.com//api/v1
  tags: Marketing, Emails, New, Technology, SaaS, Mobile, Webhook Implementations
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/sparkpost/master/_listings/sparkpost/trackingdomainsexample-domain-com-put-openapi.md
- name: SparkPost API - Delete a Tracking Domain
  x-api-slug: trackingdomainsexample-domain-com-delete
  description: Delete an existing tracking domain.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/20663-sparkpost.jpg
  humanURL: http://sparkpost.com
  baseURL: https://api.sparkpost.com//api/v1
  tags: Marketing, Emails, New, Technology, SaaS, Mobile, Webhook Implementations
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/sparkpost/master/_listings/sparkpost/trackingdomainsexample-domain-com-delete-openapi.md
- name: SparkPost API - Update a Recipient List
  x-api-slug: recipientlistsunique-id-4-graduate-students-list-put
  description: "Update an existing recipient list by specifying its ID in the URI
    path and use a\n**recipient list object** as the PUT request body. Use the **num_rcpt_errors**
    parameter to limit the number of recipient errors\nreturned.\n\nThe following
    are key points about updating your recipient lists:\n\n* If a non-scheduled transmission
    contains a recipient list, the recipient list cannot\nbe updated if the transmission
    is submitted or generating.\n\n* If a scheduled transmission contains a recipient
    list, the recipient list cannot be updated if the transmission is\ngenerating
    or submitted and within 10 minutes of the scheduled generation time.  \n\n* The
    \"id\" field is read only and cannot be changed.  If the recipient list \"id\"
    is provided in\nthe **recipient list object**, it must match the id parameter.\n\n*
    If a \"recipients\" array is provided in the update request, it must contain the
    complete recipient\nlist and all relevant recipient fields whether they are being
    changed or not.  The new recipients\nwill completely replace the existing recipients.
    \ The number of accepted recipients and the\nnumber of rejected recipients will
    only be returned if a \"recipients\" array is provided in the request.\n\n* If
    a \"name\" field is provided in the update request, it will replace the existing\n\"name\"
    field for the recipient list.\n\n* If a \"description\" field is provided in the
    update request, it will replace the existing\n\"description\" field for the recipient
    list.\n\n* If an \"attributes\" object is provided in the update request, it will
    completely replace the existing\n\"attributes\" object for the recipient list."
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/20663-sparkpost.jpg
  humanURL: http://sparkpost.com
  baseURL: https://api.sparkpost.com//api/v1
  tags: Marketing, Emails, New, Technology, SaaS, Mobile, Webhook Implementations
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/sparkpost/master/_listings/sparkpost/recipientlistsunique-id-4-graduate-students-list-put-openapi.md
- name: SparkPost API - Delete a Recipient List
  x-api-slug: recipientlistsunique-id-4-graduate-students-list-delete
  description: |-
    Permanently delete the specified recipient list.

    Once a recipient list is deleted, it
    cannot be recovered.  Before deleting a list, ensure that it is no longer needed and keep a backup copy.  If a deleted
    list is needed again, the list must be resubmitted with the CREATE API.

    If a transmission contains a recipient list, the recipient list cannot be deleted if the transmission is
    submitted or generating.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/20663-sparkpost.jpg
  humanURL: http://sparkpost.com
  baseURL: https://api.sparkpost.com//api/v1
  tags: Marketing, Emails, New, Technology, SaaS, Mobile, Webhook Implementations
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/sparkpost/master/_listings/sparkpost/recipientlistsunique-id-4-graduate-students-list-delete-openapi.md
- name: SparkPost API - Validate a Webhook
  x-api-slug: webhooks12affc24f18311e392343c15c2c818c2validate-post
  description: |-
    The validation sends an example message event batch from the Webhooks API to the
    target URL, validates that the target responds with HTTP 200,
    and returns detailed information on the response received from the target.

    #### Message Properties

    | Property   | Type   | Description | Required | Notes |
    |------------|--------|-------------|----------|-------|
    | message    | object | Example batch to send | yes | example: `{"msys": {}}`  |
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/20663-sparkpost.jpg
  humanURL: http://sparkpost.com
  baseURL: https://api.sparkpost.com//api/v1
  tags: Marketing, Emails, New, Technology, SaaS, Mobile, Webhook Implementations
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/sparkpost/master/_listings/sparkpost/webhooks12affc24f18311e392343c15c2c818c2validate-post-openapi.md
- name: SparkPost API - Samples
  x-api-slug: webhookseventssamples-get
  description: |-
    List an example of the event data that will be posted by a Webhook for the specified events.

    **Note:** the data that will arrive at your target URL will **not** contain the top level ``results`` key shown in the example response.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/20663-sparkpost.jpg
  humanURL: http://sparkpost.com
  baseURL: https://api.sparkpost.com//api/v1
  tags: Marketing, Emails, New, Technology, SaaS, Mobile, Webhook Implementations
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/sparkpost/master/_listings/sparkpost/webhookseventssamples-get-openapi.md
- name: SparkPost API - Create a Transmission (metadata with stored template and inline
    recipients)
  x-api-slug: transmissions-post
  description: "You can create a transmission in a number of ways. In all cases, you
    can use the **num_rcpt_errors** parameter to limit the number of recipient errors
    returned.\n\n**Note:** The \"return_path\" in the POST request body applies to
    SparkPost Elite only.\n\n**Note:** Sending limits apply to SparkPost only. When
    a transmission is created in SparkPost, the number of messages in the transmission
    is compared to the sending limit of your account. If the transmission will cause
    you to exceed your sending limit, the entire transmission results in an error
    and no messages are sent.  Note that no messages will be sent for the given transmission,
    regardless of the number of messages that caused you to exceed your sending limit.
    In this case, the Transmission API will return an HTTP 420 error code with an
    error detailing whether you would exceed your hourly, daily, or sandbox sending
    limit. \n\n#### Using Inline Email Part Content\n\nCreate a transmission using
    inline email part content.\n\n#### Using Inline RFC822 Content\n\nCreate a transmission
    using inline RFC822 content. Content headers are not generated for transmissions
    providing RFC822 content. They are expected to be provided as headers contained
    in the RFC822 content.\n\n#### Using a Stored Recipients List\n\nCreate a transmission
    using a stored recipients list by specifying the \"list_id\" in the \"recipients\"
    attribute.\n\n#### Using a Stored Template\n\nCreate a transmission using a stored
    template by specifying the \"template_id\" in the \"content\" attribute.  The
    \"use_draft_template\" field is optional and indicates whether to use a draft
    version or the published version of the template when generating messages.\n\n####
    Scheduling Transmissions\n\nCreate a scheduled transmission to be generated and
    sent at a future time by specifying \"start_time\" in the \"options\" attribute.\n\nScheduling
    a transmission that specifies a stored template will use the LATEST version of
    the template available at the time of scheduled generation.  The use of published
    versus draft versions follows the same logic in all transmission requests, whether
    scheduled or immediate generation. When \"use_draft_template\" is not specified
    (or set to false), the latest published version of the specified stored template
    is used. If \"use_draft_template\" is set to true, the latest draft version is
    used in the transmission instead.\n\nOnce message generation has been initiated,
    all messages in the transmission will use the template selected at the start of
    the generation. If a template update is made during the generation of a transmission
    that uses that template, the template update will succeed but the transmission
    will continue to use the version that was selected at the start of the generation."
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/20663-sparkpost.jpg
  humanURL: http://sparkpost.com
  baseURL: https://api.sparkpost.com//api/v1
  tags: Marketing, Emails, New, Technology, SaaS, Mobile, Webhook Implementations
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/sparkpost/master/_listings/sparkpost/transmissions-post-openapi.md
- name: SparkPost API - Deliverability Metrics by Binding Group
  x-api-slug: metricsdeliverabilitybindinggroup-get
  description: |-
    **Note:** This endpoint is available in SparkPost Elite only.

    Provides aggregate metrics grouped by binding group over the time window specified.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/20663-sparkpost.jpg
  humanURL: http://sparkpost.com
  baseURL: https://api.sparkpost.com//api/v1
  tags: Marketing, Emails, New, Technology, SaaS, Mobile, Webhook Implementations
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/sparkpost/master/_listings/sparkpost/metricsdeliverabilitybindinggroup-get-openapi.md
- name: SparkPost API - List all Relay Webhooks
  x-api-slug: relaywebhooks-get
  description: List all your relay webhooks.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/20663-sparkpost.jpg
  humanURL: http://sparkpost.com
  baseURL: https://api.sparkpost.com//api/v1
  tags: Marketing, Emails, New, Technology, SaaS, Mobile, Webhook Implementations
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/sparkpost/master/_listings/sparkpost/relaywebhooks-get-openapi.md
- name: SparkPost API - Create a Relay Webhook
  x-api-slug: relaywebhooks-post
  description: Create a relay webhook by providing a **relay webhooks object** as
    the POST request body.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/20663-sparkpost.jpg
  humanURL: http://sparkpost.com
  baseURL: https://api.sparkpost.com//api/v1
  tags: Marketing, Emails, New, Technology, SaaS, Mobile, Webhook Implementations
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/sparkpost/master/_listings/sparkpost/relaywebhooks-post-openapi.md
- name: SparkPost API - Documentation
  x-api-slug: messageeventseventsdocumentation-get
  description: List descriptions of the event fields that could be included in a response
    from the Message Events search endpoint. Fields will vary by event type.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/20663-sparkpost.jpg
  humanURL: http://sparkpost.com
  baseURL: https://api.sparkpost.com//api/v1
  tags: Marketing, Emails, New, Technology, SaaS, Mobile, Webhook Implementations
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/sparkpost/master/_listings/sparkpost/messageeventseventsdocumentation-get-openapi.md
- name: SparkPost API - Retrieve a Relay Webhook
  x-api-slug: relaywebhooks12013026328707075-get
  description: Retrieve a specific relay webhook by specifying the webhook ID in the
    URI path.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/20663-sparkpost.jpg
  humanURL: http://sparkpost.com
  baseURL: https://api.sparkpost.com//api/v1
  tags: Marketing, Emails, New, Technology, SaaS, Mobile, Webhook Implementations
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/sparkpost/master/_listings/sparkpost/relaywebhooks12013026328707075-get-openapi.md
- name: SparkPost API - Update a Relay Webhook
  x-api-slug: relaywebhooks12013026328707075-put
  description: Update a relay webhook by specifying the webhook ID in the URI path.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/20663-sparkpost.jpg
  humanURL: http://sparkpost.com
  baseURL: https://api.sparkpost.com//api/v1
  tags: Marketing, Emails, New, Technology, SaaS, Mobile, Webhook Implementations
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/sparkpost/master/_listings/sparkpost/relaywebhooks12013026328707075-put-openapi.md
- name: SparkPost API - Delete a Relay Webhook
  x-api-slug: relaywebhooks12013026328707075-delete
  description: Delete a relay webhook by specifying the webhook ID in the URI path.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/20663-sparkpost.jpg
  humanURL: http://sparkpost.com
  baseURL: https://api.sparkpost.com//api/v1
  tags: Marketing, Emails, New, Technology, SaaS, Mobile, Webhook Implementations
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/sparkpost/master/_listings/sparkpost/relaywebhooks12013026328707075-delete-openapi.md
- name: SparkPost API - Verify a Sending Domain
  x-api-slug: sendingdomainsverify-post
  description: |-
    The verify resource operates differently depending on the provided request fields:

      * Including the fields "dkim_verify" and/or "spf_verify" in the request initiates a check against the associated DNS record type for the specified sending domain.

      * Including the fields "postmaster_at_verify" and/or "abuse_at_verify" in the request results in an email sent to the specified sending domain's postmaster@ and/or abuse@ mailbox where a verification link can be clicked.

      * Including the fields "postmaster_at_token" and/or "abuse_at_token" in the request initiates a check of the provided token(s) against the stored token(s) for the specified sending domain.

    The domain's "status" object is returned on success.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/20663-sparkpost.jpg
  humanURL: http://sparkpost.com
  baseURL: https://api.sparkpost.com//api/v1
  tags: Marketing, Emails, New, Technology, SaaS, Mobile, Webhook Implementations
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/sparkpost/master/_listings/sparkpost/sendingdomainsverify-post-openapi.md
- name: SparkPost API - Retrieve Status Information
  x-api-slug: webhooks12affc24f18311e392343c15c2c818c2batchstatus-get
  description: |-
    Retrieve status information regarding batches that have been generated
    for the given webhook by specifying its id in the URI path. Status information includes the successes of batches
    that previously failed to reach the webhook's target URL and batches that
    are currently in a failed state.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/20663-sparkpost.jpg
  humanURL: http://sparkpost.com
  baseURL: https://api.sparkpost.com//api/v1
  tags: Marketing, Emails, New, Technology, SaaS, Mobile, Webhook Implementations
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/sparkpost/master/_listings/sparkpost/webhooks12affc24f18311e392343c15c2c818c2batchstatus-get-openapi.md
- name: SparkPost API - Deliverability Metrics by Watched Domain
  x-api-slug: metricsdeliverabilitywatcheddomain-get
  description: |-
    Provides aggregate metrics grouped by watched domain over the time window specified. The difference
    between domain and watched domain is that watched domains are comprised of the top 99% domains
    in the world.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/20663-sparkpost.jpg
  humanURL: http://sparkpost.com
  baseURL: https://api.sparkpost.com//api/v1
  tags: Marketing, Emails, New, Technology, SaaS, Mobile, Webhook Implementations
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/sparkpost/master/_listings/sparkpost/metricsdeliverabilitywatcheddomain-get-openapi.md
- name: SparkPost API - Documentation
  x-api-slug: webhookseventsdocumentation-get
  description: List descriptions of the events, event types, and event fields that
    could be included in a Webhooks post to your target URL.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/20663-sparkpost.jpg
  humanURL: http://sparkpost.com
  baseURL: https://api.sparkpost.com//api/v1
  tags: Marketing, Emails, New, Technology, SaaS, Mobile, Webhook Implementations
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/sparkpost/master/_listings/sparkpost/webhookseventsdocumentation-get-openapi.md
- name: SparkPost API - Deliverability Metrics by Campaign
  x-api-slug: metricsdeliverabilitycampaign-get
  description: Provides aggregate metrics grouped by campaign over the time window
    specified.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/20663-sparkpost.jpg
  humanURL: http://sparkpost.com
  baseURL: https://api.sparkpost.com//api/v1
  tags: Marketing, Emails, New, Technology, SaaS, Mobile, Webhook Implementations
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/sparkpost/master/_listings/sparkpost/metricsdeliverabilitycampaign-get-openapi.md
- name: SparkPost API - Preview a Template
  x-api-slug: templates11714265276872preview-post
  description: |-
    Preview the most recent version of an existing template by specifying {id}/preview in the URI path
    and providing "substitution_data" as part of the POST request body.
    The template's content will be expanded using the substitution data provided and returned
    in the response. By default, the most recently updated version is returned.  Use the **draft** query parameter to specify a draft or published
    template.

    See the Substitutions Reference section for more information.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/20663-sparkpost.jpg
  humanURL: http://sparkpost.com
  baseURL: https://api.sparkpost.com//api/v1
  tags: Marketing, Emails, New, Technology, SaaS, Mobile, Webhook Implementations
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/sparkpost/master/_listings/sparkpost/templates11714265276872preview-post-openapi.md
- name: SparkPost API - Retrieve a Recipient Suppression Status
  x-api-slug: suppressionlistrcpt-1example-com-get
  description: "Retrieve the suppression status for a specific recipient by specifying
    the recipient\u2019s email address in the URI path.\n\nIf the recipient is not
    in the customer-specific exclusion list, an HTTP status of 404 is returned. If
    the recipient is in the list, an HTTP status of 200 is returned with the full
    suppression status in the response body.\n\nIn addition to the list entry attributes,
    the response body also includes \"created\" and \"updated\" timestamps."
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/20663-sparkpost.jpg
  humanURL: http://sparkpost.com
  baseURL: https://api.sparkpost.com//api/v1
  tags: Marketing, Emails, New, Technology, SaaS, Mobile, Webhook Implementations
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/sparkpost/master/_listings/sparkpost/suppressionlistrcpt-1example-com-get-openapi.md
- name: SparkPost API - Delete a List Entry
  x-api-slug: suppressionlistrcpt-1example-com-delete
  description: |-
    Delete a recipient from the list by specifying the recipient's email address in the URI path.

    If the recipient is not in the customer-specific exclusion list, an HTTP status of 404 is returned. If the recipient is in the list, an HTTP status of 204 is returned indicating a successful deletion.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/20663-sparkpost.jpg
  humanURL: http://sparkpost.com
  baseURL: https://api.sparkpost.com//api/v1
  tags: Marketing, Emails, New, Technology, SaaS, Mobile, Webhook Implementations
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/sparkpost/master/_listings/sparkpost/suppressionlistrcpt-1example-com-delete-openapi.md
- name: SparkPost API - Delete a Transmission
  x-api-slug: transmissions11714265276872-delete
  description: |-
    Delete a transmission by specifying its ID in the URI path.

    Only transmissions which are scheduled for future generation may be deleted.

    Scheduled transmissions cannot be deleted if the transmission is within 10 minutes of the scheduled generation time.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/20663-sparkpost.jpg
  humanURL: http://sparkpost.com
  baseURL: https://api.sparkpost.com//api/v1
  tags: Marketing, Emails, New, Technology, SaaS, Mobile, Webhook Implementations
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/sparkpost/master/_listings/sparkpost/transmissions11714265276872-delete-openapi.md
- name: SparkPost API - Deliverability Metrics by Template
  x-api-slug: metricsdeliverabilitytemplate-get
  description: Provides aggregate metrics grouped by template over the time window
    specified.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/20663-sparkpost.jpg
  humanURL: http://sparkpost.com
  baseURL: https://api.sparkpost.com//api/v1
  tags: Marketing, Emails, New, Technology, SaaS, Mobile, Webhook Implementations
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/sparkpost/master/_listings/sparkpost/metricsdeliverabilitytemplate-get-openapi.md
- name: SparkPost API - Retrieve an Inbound Domain
  x-api-slug: inbounddomainsinbounddomain-test-com-get
  description: Retrieve an inbound domain by specifying its domain name in the URI
    path.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/20663-sparkpost.jpg
  humanURL: http://sparkpost.com
  baseURL: https://api.sparkpost.com//api/v1
  tags: Marketing, Emails, New, Technology, SaaS, Mobile, Webhook Implementations
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/sparkpost/master/_listings/sparkpost/inbounddomainsinbounddomain-test-com-get-openapi.md
- name: SparkPost API - Delete an Inbound Domain
  x-api-slug: inbounddomainsinbounddomain-test-com-delete
  description: Delete an inbound domain by specifying its domain name in the URI path.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/20663-sparkpost.jpg
  humanURL: http://sparkpost.com
  baseURL: https://api.sparkpost.com//api/v1
  tags: Marketing, Emails, New, Technology, SaaS, Mobile, Webhook Implementations
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/sparkpost/master/_listings/sparkpost/inbounddomainsinbounddomain-test-com-delete-openapi.md
- name: SparkPost API - Deliverability Metrics Summary
  x-api-slug: metricsdeliverability-get
  description: |-
    Provides high-level summary of aggregate metrics and lists the child endpoints that contain
    aggregate data, which can be used as "group by" qualifiers.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/20663-sparkpost.jpg
  humanURL: http://sparkpost.com
  baseURL: https://api.sparkpost.com//api/v1
  tags: Marketing, Emails, New, Technology, SaaS, Mobile, Webhook Implementations
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/sparkpost/master/_listings/sparkpost/metricsdeliverability-get-openapi.md
- name: SparkPost API - Bounce Reason Metrics By Domain
  x-api-slug: metricsdeliverabilitybouncereasondomain-get
  description: Provides deliverability metrics, specific to bounce events, grouped
    by the domain and bounce reasons.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/20663-sparkpost.jpg
  humanURL: http://sparkpost.com
  baseURL: https://api.sparkpost.com//api/v1
  tags: Marketing, Emails, New, Technology, SaaS, Mobile, Webhook Implementations
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/sparkpost/master/_listings/sparkpost/metricsdeliverabilitybouncereasondomain-get-openapi.md
- name: SparkPost API - List specific subaccount
  x-api-slug: subaccountssubaccountid-get
  description: Endpoint for retrieving information about a specific subaccount.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/20663-sparkpost.jpg
  humanURL: http://sparkpost.com
  baseURL: https://api.sparkpost.com//api/v1
  tags: Marketing, Emails, New, Technology, SaaS, Mobile, Webhook Implementations
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/sparkpost/master/_listings/sparkpost/subaccountssubaccountid-get-openapi.md
- name: SparkPost API - Edit a subaccount
  x-api-slug: subaccountssubaccountid-put
  description: |-
    Update an existing subaccount's information. You can update the following information associated with a subaccount:

    #### Request Body Attributes

    | Field   | Required   | Type   | Description                                        | Notes |
    | ------- | ---------- | ------ | -------------------------------------------------- | ----- |
    | name    | no         | string | User friendly identifier for a specific subaccount |       |
    | status  | no         | string | Status of the account                              | Value is one of `active`, `suspended`, or `terminated` |
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/20663-sparkpost.jpg
  humanURL: http://sparkpost.com
  baseURL: https://api.sparkpost.com//api/v1
  tags: Marketing, Emails, New, Technology, SaaS, Mobile, Webhook Implementations
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/sparkpost/master/_listings/sparkpost/subaccountssubaccountid-put-openapi.md
- name: SparkPost API - Delay Reason Metrics
  x-api-slug: metricsdeliverabilitydelayreason-get
  description: Provides deliverability metrics, specific to delay events, grouped
    by the delay reasons.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/20663-sparkpost.jpg
  humanURL: http://sparkpost.com
  baseURL: https://api.sparkpost.com//api/v1
  tags: Marketing, Emails, New, Technology, SaaS, Mobile, Webhook Implementations
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/sparkpost/master/_listings/sparkpost/metricsdeliverabilitydelayreason-get-openapi.md
- name: SparkPost API - Retrieve Webhook Details
  x-api-slug: webhooks12affc24f18311e392343c15c2c818c2-get
  description: Retrieve details about a webhook by specifying its id in the URI path.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/20663-sparkpost.jpg
  humanURL: http://sparkpost.com
  baseURL: https://api.sparkpost.com//api/v1
  tags: Marketing, Emails, New, Technology, SaaS, Mobile, Webhook Implementations
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/sparkpost/master/_listings/sparkpost/webhooks12affc24f18311e392343c15c2c818c2-get-openapi.md
- name: SparkPost API - Update a Webhook
  x-api-slug: webhooks12affc24f18311e392343c15c2c818c2-put
  description: |-
    Update a webhook's properties by specifying its id in the URI path and use a **webhooks object** as
    the PUT request body.

    Note that batches currently queued for delivery to this webhook will not be affected by these
    modifications.  For example, if you change the webhook's target URL, batches already queued for delivery will still be POSTed to the previous URL.

    As described in "Webhooks Object Properties", a change to the _target_ value entails a test POST request to the URL given. If this request does not receive an HTTP 200 response, your request to the Webhooks API will fail with HTTP 400, and the webhook will not be modified.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/20663-sparkpost.jpg
  humanURL: http://sparkpost.com
  baseURL: https://api.sparkpost.com//api/v1
  tags: Marketing, Emails, New, Technology, SaaS, Mobile, Webhook Implementations
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/sparkpost/master/_listings/sparkpost/webhooks12affc24f18311e392343c15c2c818c2-put-openapi.md
- name: SparkPost API - Delete a Webhook
  x-api-slug: webhooks12affc24f18311e392343c15c2c818c2-delete
  description: |-
    Delete a webhook from the system by specifying its id in the URI path.  The system will stop pushing data to the target URL after the batches currently queued to be
    delivered are drained.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/20663-sparkpost.jpg
  humanURL: http://sparkpost.com
  baseURL: https://api.sparkpost.com//api/v1
  tags: Marketing, Emails, New, Technology, SaaS, Mobile, Webhook Implementations
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/sparkpost/master/_listings/sparkpost/webhooks12affc24f18311e392343c15c2c818c2-delete-openapi.md
- name: SparkPost API - List all Bounce Domains
  x-api-slug: bouncedomains-get
  description: List all bounce domains.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/20663-sparkpost.jpg
  humanURL: http://sparkpost.com
  baseURL: https://api.sparkpost.com//api/v1
  tags: Marketing, Emails, New, Technology, SaaS, Mobile, Webhook Implementations
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/sparkpost/master/_listings/sparkpost/bouncedomains-get-openapi.md
- name: SparkPost API - Create a Bounce Domain
  x-api-slug: bouncedomains-post
  description: Create a bounce domain.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/20663-sparkpost.jpg
  humanURL: http://sparkpost.com
  baseURL: https://api.sparkpost.com//api/v1
  tags: Marketing, Emails, New, Technology, SaaS, Mobile, Webhook Implementations
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/sparkpost/master/_listings/sparkpost/bouncedomains-post-openapi.md
- name: SparkPost API - Time-Series Metrics
  x-api-slug: metricsdeliverabilitytimeseries-get
  description: |-
    Provides deliverability metrics ordered by a precision of time.

    The following table describes the validation for the **precision** parameter:

    | Value of         | Valid for time window of    |
    |---------------|-------------|
    |1min, 5min |day |
    |hour |month |
    |day, month |_any_ |
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/20663-sparkpost.jpg
  humanURL: http://sparkpost.com
  baseURL: https://api.sparkpost.com//api/v1
  tags: Marketing, Emails, New, Technology, SaaS, Mobile, Webhook Implementations
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/sparkpost/master/_listings/sparkpost/metricsdeliverabilitytimeseries-get-openapi.md
- name: SparkPost API - Retrieve a Recipient List
  x-api-slug: recipientlistsunique-id-4-graduate-students-get
  description: |-
    Retrieve details about a specified recipient list by specifying its id in the URI path.  To
    retrieve the recipients contained in a list, the list must be specified and the **show_recipients** parameter must be set to true.

    **Note:** The "return_path" in the POST request body applies to SparkPost Elite only.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/20663-sparkpost.jpg
  humanURL: http://sparkpost.com
  baseURL: https://api.sparkpost.com//api/v1
  tags: Marketing, Emails, New, Technology, SaaS, Mobile, Webhook Implementations
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/sparkpost/master/_listings/sparkpost/recipientlistsunique-id-4-graduate-students-get-openapi.md
- name: SparkPost API - Deliveries By Attempt
  x-api-slug: metricsdeliverabilityattempt-get
  description: Provides aggregate count of deliveries grouped by the attempt number.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/20663-sparkpost.jpg
  humanURL: http://sparkpost.com
  baseURL: https://api.sparkpost.com//api/v1
  tags: Marketing, Emails, New, Technology, SaaS, Mobile, Webhook Implementations
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/sparkpost/master/_listings/sparkpost/metricsdeliverabilityattempt-get-openapi.md
- name: SparkPost API - List all Webhooks
  x-api-slug: webhooks-get
  description: List currently extant webhooks.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/20663-sparkpost.jpg
  humanURL: http://sparkpost.com
  baseURL: https://api.sparkpost.com//api/v1
  tags: Marketing, Emails, New, Technology, SaaS, Mobile, Webhook Implementations
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/sparkpost/master/_listings/sparkpost/webhooks-get-openapi.md
- name: SparkPost API - Create a Webhook
  x-api-slug: webhooks-post
  description: |-
    Create a webhook by providing a **webhooks object** as the POST request body.  On creation, events will
    begin to be pushed to the target URL specified in the POST request body.

    As described in "Webhooks Object Properties", webhook creation entails a test POST request to the URL given as the _target_ value. If this request does not receive an HTTP 200 response, your request to the Webhook API will fail with HTTP 400, and the webhook will not be created. If created successfully, the webhook will begin to receive event data after 1 minute.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/20663-sparkpost.jpg
  humanURL: http://sparkpost.com
  baseURL: https://api.sparkpost.com//api/v1
  tags: Marketing, Emails, New, Technology, SaaS, Mobile, Webhook Implementations
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/sparkpost/master/_listings/sparkpost/webhooks-post-openapi.md
- name: SparkPost API - Delay Reason Metrics By Domain
  x-api-slug: metricsdeliverabilitydelayreasondomain-get
  description: Provides deliverability metrics, specific to delay events, grouped
    by the domain and delay reasons.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/20663-sparkpost.jpg
  humanURL: http://sparkpost.com
  baseURL: https://api.sparkpost.com//api/v1
  tags: Marketing, Emails, New, Technology, SaaS, Mobile, Webhook Implementations
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/sparkpost/master/_listings/sparkpost/metricsdeliverabilitydelayreasondomain-get-openapi.md
- name: SparkPost API - Bindings List
  x-api-slug: metricsbindings-get
  description: |-
    **Note:** This endpoint is available in SparkPost Elite only.

    Returns a list of bindings that the Metrics API contains data on.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/20663-sparkpost.jpg
  humanURL: http://sparkpost.com
  baseURL: https://api.sparkpost.com//api/v1
  tags: Marketing, Emails, New, Technology, SaaS, Mobile, Webhook Implementations
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/sparkpost/master/_listings/sparkpost/metricsbindings-get-openapi.md
- name: SparkPost API - List all Inbound Domains
  x-api-slug: inbounddomains-get
  description: List all your inbound domains.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/20663-sparkpost.jpg
  humanURL: http://sparkpost.com
  baseURL: https://api.sparkpost.com//api/v1
  tags: Marketing, Emails, New, Technology, SaaS, Mobile, Webhook Implementations
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/sparkpost/master/_listings/sparkpost/inbounddomains-get-openapi.md
- name: SparkPost API - Create an Inbound Domain
  x-api-slug: inbounddomains-post
  description: Create an inbound domain by providing an **inbound domains object**
    as the POST request body.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/20663-sparkpost.jpg
  humanURL: http://sparkpost.com
  baseURL: https://api.sparkpost.com//api/v1
  tags: Marketing, Emails, New, Technology, SaaS, Mobile, Webhook Implementations
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/sparkpost/master/_listings/sparkpost/inbounddomains-post-openapi.md
- name: SparkPost API - Insert or Update List Entries
  x-api-slug: suppressionlist-put
  description: |-
    Bulk insert or update entries in the customer-specific exclusion list by providing a JSON object, with a "recipients" key containing an array of recipients to insert or update, as the PUT request body. Maximum size of the JSON object is 50mb. At a minimum, each recipient must have a valid "email" address and at least one of the following keys: "transactional" or "non_transactional". The optional "description" key can be used to include an explanation of what type of message should be suppressed.

    If the recipient entry was added to the list by Compliance, it cannot be updated.

    If an email address is duplicated in a single request, only the first instance will be processed.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/20663-sparkpost.jpg
  humanURL: http://sparkpost.com
  baseURL: https://api.sparkpost.com//api/v1
  tags: Marketing, Emails, New, Technology, SaaS, Mobile, Webhook Implementations
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/sparkpost/master/_listings/sparkpost/suppressionlist-put-openapi.md
- name: SparkPost API - Deliverability Metrics by Domain
  x-api-slug: metricsdeliverabilitydomain-get
  description: Provides aggregate metrics grouped by domain over the time window specified.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/20663-sparkpost.jpg
  humanURL: http://sparkpost.com
  baseURL: https://api.sparkpost.com//api/v1
  tags: Marketing, Emails, New, Technology, SaaS, Mobile, Webhook Implementations
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/sparkpost/master/_listings/sparkpost/metricsdeliverabilitydomain-get-openapi.md
- name: SparkPost API - Campaigns List
  x-api-slug: metricscampaigns-get
  description: Returns a list of campaigns that the Metrics API contains data on.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/20663-sparkpost.jpg
  humanURL: http://sparkpost.com
  baseURL: https://api.sparkpost.com//api/v1
  tags: Marketing, Emails, New, Technology, SaaS, Mobile, Webhook Implementations
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/sparkpost/master/_listings/sparkpost/metricscampaigns-get-openapi.md
- name: SparkPost API - Nodes List
  x-api-slug: metricsnodes-get
  description: |-
    **Note:** This endpoint is available in SparkPost Elite only.

    Returns a list of nodes that the Metrics API contains data on.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/20663-sparkpost.jpg
  humanURL: http://sparkpost.com
  baseURL: https://api.sparkpost.com//api/v1
  tags: Marketing, Emails, New, Technology, SaaS, Mobile, Webhook Implementations
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/sparkpost/master/_listings/sparkpost/metricsnodes-get-openapi.md
- name: SparkPost API - Binding Groups List
  x-api-slug: metricsbindinggroups-get
  description: |-
    **Note:** This endpoint is available in SparkPost Elite only.

    Returns a list of binding groups that the Metrics API contains data on.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/20663-sparkpost.jpg
  humanURL: http://sparkpost.com
  baseURL: https://api.sparkpost.com//api/v1
  tags: Marketing, Emails, New, Technology, SaaS, Mobile, Webhook Implementations
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/sparkpost/master/_listings/sparkpost/metricsbindinggroups-get-openapi.md
- name: SparkPost API - Domains List
  x-api-slug: metricsdomains-get
  description: Returns a list of domains that the Metrics API contains data on.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/20663-sparkpost.jpg
  humanURL: http://sparkpost.com
  baseURL: https://api.sparkpost.com//api/v1
  tags: Marketing, Emails, New, Technology, SaaS, Mobile, Webhook Implementations
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/sparkpost/master/_listings/sparkpost/metricsdomains-get-openapi.md
- name: SparkPost API - Verify a Tracking Domain
  x-api-slug: trackingdomainsexample-domain-comverify-post
  description: Initiate a check against the CNAME DNS record for the specified tracking
    domain. The domain's `status` object is returned on success.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/20663-sparkpost.jpg
  humanURL: http://sparkpost.com
  baseURL: https://api.sparkpost.com//api/v1
  tags: Marketing, Emails, New, Technology, SaaS, Mobile, Webhook Implementations
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/sparkpost/master/_listings/sparkpost/trackingdomainsexample-domain-comverify-post-openapi.md
- name: SparkPost API - Samples
  x-api-slug: messageeventseventssamples-get
  description: List an example of the event data that will be included in a response
    from the Message Events search endpoint.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/20663-sparkpost.jpg
  humanURL: http://sparkpost.com
  baseURL: https://api.sparkpost.com//api/v1
  tags: Marketing, Emails, New, Technology, SaaS, Mobile, Webhook Implementations
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/sparkpost/master/_listings/sparkpost/messageeventseventssamples-get-openapi.md
- name: SparkPost API - Bounce Classification Metrics
  x-api-slug: metricsdeliverabilitybounceclassification-get
  description: Provides deliverability metrics, specific to bounce events, grouped
    by the bounce classification. (See [Bounce Classification Codes.](https://www.sparkpost.com/docs/bounce-classification-codes))
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/20663-sparkpost.jpg
  humanURL: http://sparkpost.com
  baseURL: https://api.sparkpost.com//api/v1
  tags: Marketing, Emails, New, Technology, SaaS, Mobile, Webhook Implementations
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/sparkpost/master/_listings/sparkpost/metricsdeliverabilitybounceclassification-get-openapi.md
x-common:
- type: x-api-gallery
  url: http://soundcloud.api.gallery.streamdata.io
- type: x-api-stack
  url: http://sparkpost.stack.network
- type: x-blog
  url: https://www.sparkpost.com/blog/?_ga=2.193809710.2006670344.1534051360-859907643.1534051360
- type: x-blog
  url: https://www.sparkpost.com/blog/
- type: x-blog-rss
  url: https://www.sparkpost.com/feed/
- type: x-crunchbase
  url: https://crunchbase.com/organization/message-systems
- type: x-developer
  url: https://developers.sparkpost.com/
- type: x-documentation
  url: https://www.sparkpost.com/docs/?_ga=2.193809710.2006670344.1534051360-859907643.1534051360
- type: x-getting-started
  url: https://www.sparkpost.com/docs/getting-started/
- type: x-github
  url: https://github.com/SparkPost
- type: x-linkedin
  url: https://www.linkedin.com/company/sparkpost/
- type: x-curated-source
  url: https://www.sparkpost.com/blog/webhooks-beyond-the-basics/#.VyI916MrKCQ
- type: x-website
  url: http://sparkpost.com
- type: x-twitter
  url: https://twitter.com/SparkPost
- type: x-webhook
  url: https://developers.sparkpost.com/api/webhooks/
- type: x-website
  url: https://developers.sparkpost.com
include: []
maintainers:
- FN: Kin Lane
  x-twitter: apievangelist
  email: info@apievangelist.com
---