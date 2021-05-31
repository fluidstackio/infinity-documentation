# View

___

## Overview

Once you have deployed an instant server, you may want to view it! 

*Keep in mind that this is only for servers that have instant deployment enabled (see our plans page)*

## Request

Our REST API endpoint for plans is available here: 
<br>
`GET` `https://infinity.fluidstack.io/api/get/single`

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
| server | Object | Object of the following parameters |
| id | String | ID of the server |
| name | String | The custom name that you set for the server on creation |
| os | String | Operating System |
| gpu_count | Integer | Number of graphics cards |
| gpu_model | String | Type of graphics card attached |
| cost | Object | List of costs of the resource |
| disk | Integer | Integer of the GB of storage on the VM |
| ram | Integer | MB of RAM |
| vcpus | Integer | Number of CPU threads allocated | 
| links | Object | Links to the resource in question |
| status | String | "Provisioning," "Running," or "Terminated" |

### Example

Example request:

    curl "https://infinity.fluidstack.io/api/get/single?api_key=API_KEY&api_token=API_TOKEN&server=myServerID" 

Example response: 

    {
        "server":
        {
            "id": "myServerID",
            "name":"jonathans-server.fluidstack.io",
            "os":"Ubuntu 18.04",
            "gpu_count": 8,
            "gpu_model": "V100 16GB NVLink",
            "disk": 3000,
            "ram":386048,
            "vcpus": 16,
            "cost":
            {
                "hour": 25
            },
            "links":
            [
                {
                    "href":"https://infinity.fluidstack.io/manage/myServerID",
                    "rel":"self"
                }
            ],
            "status": "Running"
        },
        "success":true
    }