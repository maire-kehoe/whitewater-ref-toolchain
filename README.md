# whitewater-ref-toolchain

Used to show the Whitewater GitHub oauth Authorize button. References the existent Whitewater server, but a non-existent repo on that server.
The Whitewater internal IBM server is at [https://github.ibm.com](https://github.ibm.com)


[![Deploy To IBM Cloud](https://cloud.ibm.com/devops/graphics/create_toolchain_button.png)](https://cloud.ibm.com/devops/setup/deploy?repository=https%3A//github.com/maire-kehoe/whitewater-ref-toolchain&env_id=ibm:yp:us-south) production us-south

[![Deploy To IBM Cloud](https://cloud.ibm.com/devops/graphics/create_toolchain_button.png)](https://dev.console.test.cloud.ibm.com/devops/setup/deploy?repository=https%3A//github.com/maire-kehoe/whitewater-ref-toolchain&env_id=ibm:yp:us-south) dev

Instructions

These steps can be used to prevent authorization errors when using tool-chain links that assume authorization has already been given. 
Clicking on the buttons will kick off the creation of a (fake) tool chain. This is only used to get you to the step of authorizing access (of the Whitewater server) to your repository - which is needed to create your own tool chain later. After authorizing you will cancel this tool-chain creation and can continue with the creation of your own toolchain.
1. Click on the button to use either the IBM production or the IBM test cloud (https://test.cloud.ibm.com) depending where you want to deploy to
2. You will presented with the "create tool chain" screen. You can ignore all and click the "authorize button" and follow the repo authorization.
3. After the repo is authorized, click `Cancel`to cancel the tool chain creation (it's pointing to a fake/placeholder repo anyway).
You can now continue with the creation of your own toolchain.

Alternatively you can add your repo access token to the URL that creates "your" tool chain <your-Cloud-URL>/devops/setup/deploy/?repository=<your-repo-URL>&repository_token=<GHE_PAT>[&branch=<branch if not default branch>]

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


### Note on the page of authorizations for git servers

To see the list of existing authorizations in a region open a URL like this url for us-south / Dallas.
- https://cloud.ibm.com/devops/git?env_id=ibm:yp:us-south

for an IBMer user it will show if the user is Authorized for the Whitewater server,
e.g. for me (mkehoe) it shows:

**Git Servers**
| Title                         | Type        | URL                    | Date Created  | Username | Status     |
| ----------------------------- |-------------| -----------------------| --------------| ---------| -----------|
| Whitewater GitHub Enterprise  | GitHub      | https://github.ibm.com | 28/10/2020    | MKEHOE   | Authorized |

if the status for you is not "Authorized" then you may need to follow the above steps to see the Authorize button.
