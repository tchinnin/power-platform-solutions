# Enable Power Apps Sharing with Microsoft 365 Groups

  

This **Dataverse For Teams** Solution contains a Power Apps Canvas application that allows a user to set the **"SecurityEnabled"** flag of each Microsoft 365 Groups he owns.

By default, sharing a Power Apps Canvas with a Microsoft 365 Group (so a Microsoft Teams also), is not possible. As stated in this [documentation](https://docs.microsoft.com/en-us/powerapps/maker/canvas-apps/share-app#share-an-app-with-microsoft-365-groups), the **"SecurityEnable"** must be enabled to allow it.
This is achievable using PowerShell, but not all Power Apps makers are familiar with it. 

This canvas application uses the Office365Group connector to show the connected  user all the groups he owns. 
For each group, the user can see whether the SeurityEnabled flag is true or false, and to change the configuration.
Once a button is clicked, a Power Automate Flow is triggered. The flow uses the Office365Group connector to send a HTTP Request to Graph API to change the SecurityEnabled flag.

 - The Office365Group connector is standard. There is no need for premium licences to run this Power Apps
 - As the flow is triggered from Power Apps, it uses the connection of the application user. The GraphAPI call is done through Delegated permission as a group owner (that is required to be allowed to set up the SecurityEnabled property)

### Version History

Version| Date | Description

--- | --- | ---

1.0.211217.0| 2021/12/17 | First version of the solution