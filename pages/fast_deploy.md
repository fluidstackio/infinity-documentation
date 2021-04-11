# Fast Server Deployment

___

## Overview

Typically, most orders placed through our website are delivered within 24 hours due to manual fraud checks and/or the need for us to tell one of our suppliers to manually deploy a machine. 

For machines that you need now, obviously this isn't ideal. Instead, we've worked with some of our providers to directly integrate into their API. 

**Within 2 seconds, you can place an order for a server that is typically ready within 1 minute**

*Keep in mind that this is only for servers that have fast deployment enabled (see our plans page)*

## Request

Our REST API endpoint for plans is available here: 
<br>
`POST` `https://infinity.fluidstack.io/api/deploy/single`

You need to include the following:

| Name | Type | Description |
| --- | --- | --- |
| api_key | String | Your API key |
| api_token | String | Your API token |
| plan | String | The plan ID to provision |
| name | String | The hostname of your new server |
| admin_user | String | Your desired administrator username |
| admin_pass | String | Your desired administrator password |


### Response
| Name | Type | Description |
| --- | --- | --- |
| success | Boolean | Whether your request succeeded |
| server | Array | Array of the following parameters |
| id | String | ID of the new VM |
| links | Array | Links to the resource in question |