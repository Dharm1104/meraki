# Meraki Dashboard API #
A RESTful API to programmatically manage and monitor Meraki networks at scale.
![cloud-code](https://github.com/Dharm1104/meraki/assets/141824759/a1a097d0-a470-4a6d-ba33-38912c2a248c)
## What can you do with it? ##
* Add new organizations, admins, networks, devices, VLANs, and more
* Configure thousands of networks in minutes
* On-board and off-board new employees’ teleworker setup automatically
* Build your own dashboard for store managers, field techs, or unique use cases
Checkout out the [Explore](https://developer.cisco.com/meraki/explore/) section for open source projects, or browse the [Marketplace](https://apps.meraki.io/en-US/home) for partner solutions.
## Authorization ##
Dashboard API v1 supports Bearer Auth using the standard Authorization header parameter. The value will be a string that begins with the word Bearer, followed by your Meraki API key.

***Note:*** *When developing scripts, it's a best practice to create a local environment variable MERAKI_DASHBOARD_API_KEY and set it to your API key, so that you can omit it from your source code. Instructions vary by operating system, so please consult your OS vendor for more information.*
## Obtaining your Meraki API key ##
In order to interact with the Dashboard API, you must first obtain an API key.
* Open your Meraki dashboard: [https://dashboard.meraki.com](https://account.meraki.com/login/dashboard_login?go=%2F)
* Once logged in, navigate to the * Organization > Settings * page.
* Ensure that the API Access is set to “Enable access to the Cisco Meraki Dashboard API”

[](images/dashEnableOrgAPI.png)
Then go to your profile by clicking on your account email address (on the upper-right) > My profile to generate the API key.

*save this key in a secure location, as it represents your admin credentials*

[](<img width="372" alt="dashGenerateAPIkey" src="https://github.com/Dharm1104/meraki/assets/141824759/dea080ba-a2d3-4e6f-b2e3-61a3378a0dcc">)

## Troubleshooting ##
If you get a 401 Unauthorized error (with message "Missing API key") when using dashboard API v1 with Bearer token, check the following to troubleshoot:
1. As an example, when using your API key to retrieve the [GET /organizations](https://developer.cisco.com/meraki/api-v1/get-organizations/) endpoint, you should see the same data as shown when navigating to [https://api.meraki.com/api/v1/organizations](https://api.meraki.com/api/v1/organizations) in your browser, using an authenticated session with the credentials that generated the API key.
2. Next, check that your API call has the correct header with the following (and not v0's 'X-Cisco-Meraki-API-Key')
3. X-Cisco-Meraki-API-Key **--location-trusted** flag is included.
4. If making the API call in Postman, check that the setting “_Follow Authorization header_” is enabled.
   
| Parameters | Description | Meraki Python library |
|------------|-------------|-----------------------|
|confirmed|Set to true for immediate execution. Set to false if the action should be previewed before executing.|
|synchronous|Force the batch to run synchronous. There can be at most 20 actions in synchronous batch.|
