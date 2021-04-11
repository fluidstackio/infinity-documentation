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


## Response
| Name | Type | Description |
| --- | --- | --- |
| success | Boolean | Whether your request succeeded |
| server | Array | Array of the following parameters |
| id | String | ID of the new VM |
| links | Array | Links to the resource in question |

### Example

Example request:

    curl -X POST -d "api_key=API_KEY&api_token=API_TOKEN&admin_pass=myC0MP1EXpassW0RD&admin_user=jonathan&name=jonathans-server.fluidstack.io&plan=rec3gucteDeyzXXyL" https://infinity.fluidstack.io/api/deploy/single

Example response: 

    {
        "server":
        {
            "id":"rectu1BNbJRDcqVHb",
            "links":[
                {
                    "href":"https://infinity.fluidstack.io/manage/rectu1BNbJRDcqVHb",
                    "rel":"self"
                }
            ]
        },
        "success":true
    }

**Once your request succeeds, you will need to wait for a few minutes for the server to boot up for you to be able to access it.**

# Checking Deployment Status

## Overview

If you want to check your server's deployment status, you can send the following request. 
Please limit this to every 5 seconds. If the server has not booted within 1 minute, please send us a message. 

## Request

Our REST API endpoint for plans is available here: 
<br>
`POST` `https://infinity.fluidstack.io/api/deploy/status`


You need to include the following:

| Name | Type | Description |
| --- | --- | --- |
| api_key | String | Your API key |
| api_token | String | Your API token |
| id | String | The ID of the server returned in the request deploying the server |

## Response

You will receive an array of different statuses. 

### Example

Example request:

    curl -X POST -d "id=SERVER&api_key=API_KEY&api_token=API_TOKEN" https://infinity.fluidstack.io/api/deploy/status

Example response:

    {
        "status":[
            {
                "lastTransitionTime":"2021-04-11T06:18:28Z",
                "message":"Waiting for VirtualMachineInstance to be ready",
                "reason":"Initializing",
                "status":"False",
                "type":"Ready"
            },
            {
                "lastTransitionTime":"2021-04-11T06:18:28Z",
                "message":"ServicesReady",
                "reason":"ServicesReady",
                "status":"True",
                "type":"ServicesReady"
            },
            {
                "lastTransitionTime":"2021-04-11T06:18:29Z",
                "message":"VirtualServerReady",
                "reason":"VirtualServerReady",
                "status":"True",
                "type":"VirtualMachineReady"
            },
            {
                "lastTransitionTime":"2021-04-11T06:18:29Z",
                "message":"Waiting for VirtualMachineInstance to be ready",
                "reason":"Pending",
                "status":"False",
                "type":"VirtualServerStarted"
            }
    ]}