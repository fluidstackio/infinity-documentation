# List

___

## Overview

To keep track of all of your instant deploy servers, you can use our list feature 

*Keep in mind that this is only for servers that have instant deployment enabled (see our plans page)*

## Request

Our REST API endpoint for plans is available here: 
<br>
`GET` `https://infinity.fluidstack.io/api/list`

You need to include the following:

| Name | Type | Description |
| --- | --- | --- |
| api_key | String | Your API key |
| api_token | String | Your API token |


## Response
| Name | Type | Description |
| --- | --- | --- |
| success | Boolean | Whether your request succeeded |
| servers | Object | Object of a list of servers, each with the following parameters |
| id | String | ID of the server |
| name | String | The custom name that you set for the server on creation |
| gpu_count | Integer | Number of graphics cards |
| gpu_model | String | Type of graphics card attached |
| cost | Object | List of costs of the resource |
| links | Object | Links to the resource in question |
| status | String | "Provisioning," "Running," or "Terminated" |

### Example

Example request:

    curl "https://infinity.fluidstack.io/api/list?api_key=API_KEY&api_token=API_TOKEN" 

Example response: 

    {
        "servers":
        {
            "id": "superRandomID",
            "name":"jonathans-server.fluidstack.io",
            "gpu_count": 8,
            "gpu_model": "V100 16GB NVLink",
            "cost": 25,
            "links":
            [
                {
                    "href":"https://infinity.fluidstack.io/api/get/single?server=superRandomID",
                    "rel":"self"
                }
            ],
            "status": "Running"
        },
        {
            "id": "superRandomID2",
            "name":"jonathans-server2.fluidstack.io",
            "gpu_count": 4,
            "gpu_model": "A100 40GB NVLink",
            "cost": 25,
            "links":
            [
                {
                    "href":"https://infinity.fluidstack.io/api/get/single?server=superRandomID2",
                    "rel":"self"
                }
            ],
            "status": "Provisioning"
        },
        "success":true
    }