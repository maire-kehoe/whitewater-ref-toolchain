# whitewater-ref-toolchain

Used to show the Whitewater GitHub oauth Authorize button. References the existent Whitewater server, but a non-existent repo on that server.
The Whitewater internal IBM server is at [https://github.ibm.com](https://github.ibm.com)


[![Deploy To IBM Cloud](https://cloud.ibm.com/devops/graphics/create_toolchain_button.png)](https://cloud.ibm.com/devops/setup/deploy?repository=https%3A//github.com/maire-kehoe/whitewater-ref-toolchain&env_id=ibm:yp:us-south) production us-south

[![Deploy To IBM Cloud](https://cloud.ibm.com/devops/graphics/create_toolchain_button.png)](https://dev.console.test.cloud.ibm.com/devops/setup/deploy?repository=https%3A//github.com/maire-kehoe/whitewater-ref-toolchain&env_id=ibm:yp:us-south) dev


Note, the Whitewater tool integration is only available in accounts associated with IBM users.  
Non-IBM users who open the click the above button will see an error dialog like:
> Service(s) Unavailable  
> This template references one or more services that are not available in the Dallas region. Please choose a different template or region.  
> Missing service: 'github_integrated'

IBM users who have not yet authorized in the current region will see  
the following text and an Authorize button:
> You must authorize before you can configure this tool integration.  
> Authorize

IBM users who have previously authorized in this region will see  
a checkbox for "I understand",
and because the repository reference doesn't exist, will see the following expected red error text:
> Unable to read the repository on: https://github.ibm.com/otc-compliance/some-fake-non-existent-repo.git. User is not authorized, or repository does not exist

Note, the above button is for us-south / Dallas.  
If you wish to authorize for a different region, change the value in the Region dropdown and wait for the page to refresh.
