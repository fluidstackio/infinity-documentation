# Plans

___

## Overview

Plans are different machine configurations.

## Request

Our REST API endpoint for plans is available here: 
<br>
`GET` `https://infinity.fluidstack.io/api/plans`

There is no authentication required, so a simple `GET` request is sufficient.

Optionally, you can any of the following:

| Name | Type | Description |
| --- | --- | --- |
| limit | Int | Limit the number of servers that will be retuned |


### Response
| Name | Type | Description |
| --- | --- | --- |
| plans | Array | An array of flavor objects |
| id | String | A string of the flavor's ID |
| name | String | A string of the flavor's name. Typically this is the same as the ID | 
| fast_deploy | Boolean | Whether you can deploy this server via our instant deployment API |
| disk | Int | The disk size, in GB |
| gpu_count | Int | The number of GPUs |
| gpu_model | String | The name of the GPU |
| os_options | String | The operating systems that can be deployed. Linux (Ubuntu 18.04), Windows (Windows 10), or Any (either) |
| ram | Int | MB of RAM | 
| stock | Int | Number of machines in-stock. If the number is 999, we are not exactly sure of the stock, but we will contact you if we run out. |
| swap | Int | Swapfile size of the operating system image, typically zero |
| vcpus | Int | Number of CPU threads |
| links | Array | Links to the resources in question |
| cost | Object | Costs for different commit periods | 
| extra_specs | Object | Miscellaneous information | 
| extra_specs: region | String | Region of the machine. `North America`, `Central America`, `South America`, `Europe`, `Africa`, `Asia`, or `Oceania` |
| extra_specs: country | String | Country of the machine |
| extra_specs: cpu_model | String | CPU model |
| extra_specs: network_speed | Float | Network Speed, in gigabits per second |
| extra_specs: storage_type | String | `SATA SSD`, or `NVMe SSD` |
| extra_specs: virtualization | String | `Bare Metal`, or `Virtual Machine` for KVM virtual machines |


### Example Response
    "plans": [
        {
            "id": "rec3gucteDeyzXXyL",
            "name": "rec3gucteDeyzXXyL",
            "disk": 3000,
            "gpu_count": 8,
            "gpu_model": "V100 16GB NVLink",
            "os_options": "Linux",
            "ram": 386048,
            "stock": 999,
            "swap": 0,
            "vcpus": 16,
            "links": [
                {
                    "href":"https://infinity.fluidstack.io/order_details/rec3gucteDeyzXXyL",
                    "rel":"details"
                },
                {
                    "href": "https://infinity.fluidstack.io/order_configure/rec3gucteDeyzXXyL",
                    "rel": "configure"
                },
                {
                    "href": "https://infinity.fluidstack.io/api/plans/rec3gucteDeyzXXyL",
                    "rel": "self"
                }
            ],
            "cost": {
                "month": 3400,
                "quarter": 9000,
                "week": 880,
                "year": 33000
            },
            "extra_specs": {
                "region": "North America",
                "country": "United States",
                "cpu_model": "Intel Xeon Silver 4208",
                "network_speed": 0.1,
                "storage_type": "SATA SSD",
                "virtualization": "Bare Metal"
            }
        }
    ]