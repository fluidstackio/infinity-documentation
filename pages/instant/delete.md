# Delete

___

## Overview

Deleting instant deployment servers is super easy.   

*Keep in mind that this is only for servers that have instant deployment enabled (see our plans page)*

## Request

Our REST API endpoint for plans is available here: 
<br>
`GET` `https://infinity.fluidstack.io/api/delete/single`

You need to include the following:

| Name | Type | Description |
| --- | --- | --- |
| api_key | String | Your API key |
| api_token | String | Your API token |
| server | String | The ID of your server |


## Response
| Name | Type | Description |
| --- | --- | --- |
| success | Boolean | Whether your request succeeded |

### Example

Example request:

    curl "https://infinity.fluidstack.io/api/delete/single?api_key=API_KEY&api_token=API_TOKEN&server=myServerID" 

Example response: 

    {
        "success":true
    }