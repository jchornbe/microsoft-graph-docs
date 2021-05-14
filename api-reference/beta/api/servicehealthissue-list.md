---
title: "List serviceHealthIssues"
description: "Gets all service health issues information for the tenant. The operation returns a list of the [serviceHealthIssue](../resources/servicehealthissue.md) objects and their properties."
author: "payiAzure"
localization_priority: Normal
ms.prod: "m365-servicecommsplatform"
doc_type: apiPageType
---

# List serviceHealthIssues
Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Gets all service health issues information for the tenant. The operation returns a list of the [serviceHealthIssue](../resources/servicehealthissue.md) objects and their properties.

## Permissions
One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

|Permission type|Permissions (from least to most privileged)|
|:---|:---|
|Delegated (work or school account)|ServiceHealth.Read.All|
|Delegated (personal Microsoft account)|ServiceHealth.Read.All|
|Application|ServiceHealth.Read.All|

## HTTP request

<!-- {
  "blockType": "ignored"
}
-->
``` http
GET /admin/serviceAnnouncement/issues
```

## Optional query parameters
This method supports some of the OData query parameters to help customize the response. For general information, see [OData query parameters](/graph/query-parameters).

## Request headers
|Name|Description|
|:---|:---|
|Authorization|Bearer {token}. Required.|

## Request body
Do not supply a request body for this method.

## Response

If successful, this method returns a `200 OK` response code and a collection of [serviceHealthIssue](../resources/servicehealthissue.md) objects in the response body.

## Examples

### Request
<!-- {
  "blockType": "request",
  "name": "list_servicehealthissue"
}
-->
``` http
GET https://graph.microsoft.com/beta/admin/serviceAnnouncement/issues
```


### Response
**Note:** The response object shown here might be shortened for readability.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "Collection(m365ServiceHealth.readServices.commercialWebService.models.serviceHealthIssue)"
}
-->
``` http
HTTP/1.1 200 OK
Content-Type: application/json

{
  "value": [
    {
      "@odata.type": "#m365ServiceHealth.readServices.commercialWebService.models.serviceHealthIssue",
      "startDateTime": "2020-11-13T21:00:00Z",
      "endDateTime": "2020-11-14T17:15:00Z",
      "lastModifiedDateTime": "2020-11-14T18:20:24.767Z",
      "title": "Limited number of users unable to send or receive email through the Exchange Online service",
      "id": "EX226792",
      "impactDescription": "Users may have been unable to send or receive email through the Exchange Online service.",
      "classification": "Incident",
      "origin": "Microsoft",
      "status": "ServiceRestored",
      "service": "Exchange Online",
      "feature": "Mailflow - delayed delivery from Internet",
      "featureGroup": "E-Mail timely delivery",
      "isResolved": true,
      "highImpact": false,
      "details": [
        {
          "name": "NotifyInApp",
          "value": "True"
        }
      ],
      "posts": [
        {
          "contentType": "Text",
          "content": "Title: Limited number of users unable to send or receive email through the Exchange Online service\n\nUser Impact: Users may be unable to send or receive email through the Exchange Online service.\n\n..."
        },
        ...
      ]
    },
    ...
  ]
}
```
