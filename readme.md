


# lib_GoogleGA4

This library connects your application with Google Analytics 4. It provides a set of SharedActions you can use in your project.

## How to use

Install the library, and call the **InstallGA4** SharedAction in your application. The best place to call it is in a **[onNetWorkReachable](https://doc.convertigo.com/documentation/latest/reference-manual/convertigo-objects/mobile-application/components/control-components/appevent/)** Application Event. In this way the GA4 analytics will be installed when your application starts.

This shared Action will require à **Measurement ID** you will find in you Google Analytics Console **Data streams**. A **Measurement ID** is in the form of **G-XXXXXXXXXX**. You can pass this id in the **G_ID** variable.

## How to track visited pages

The library provides a **PageEvent** sharedAction you can use to Track visited pages of your app. The best place to call it is in an **[AppGuard](https://doc.convertigo.com/documentation/latest/reference-manual/convertigo-objects/mobile-application/ngx-components/control-components/appguard/)** Application Event

This way way each time a user navigates on page the **AppGuard** event will be triggered and your sharedAction will be called. 

Note:  To be sure that you page will be entered correctly do not forget to add a **[CustomAction](https://doc.convertigo.com/documentation/latest/reference-manual/convertigo-objects/mobile-application/components/action-components/customaction/)** after calling the **PageEvent** SharedAction with a 

`return true`

JavaScript line to instruct the AppGuard to let the user navigate on the page.. 

# How to notify special events

The library also provides a **NotifyAevent** SharedAction to let you notify special events to Google Analytics 4  Just call this SharedAction anywhere in your application providing the **EventType* and **EventData** variables. You can have documenttation of the various G4 event types [here](https://developers.google.com/analytics/devguides/collection/ga4/reference/events?client_type=gtag) 

# Sample App

You will find in this project a Sample Application using these shared actions for reference.



For more technical informations : [documentation](./project.md)

- [Installation](#installation)
- [Mobile Library](#mobile-library)
    - [Shared Actions](#shared-actions)
        - [InstallGA4](#installga4)
        - [NotifyEvent](#notifyevent)
        - [PageEvent](#pageevent)


## Installation

1. In your Convertigo Studio click on ![](https://github.com/convertigo/convertigo/blob/develop/eclipse-plugin-studio/icons/studio/project_import.gif?raw=true "Import a project in treeview") to import a project in the treeview
2. In the import wizard

   ![](https://github.com/convertigo/convertigo/blob/develop/eclipse-plugin-studio/tomcat/webapps/convertigo/templates/ftl/project_import_wzd.png?raw=true "Import Project")
   
   paste the text below into the `Project remote URL` field:
   <table>
     <tr><td>Usage</td><td>Click the copy button at the end of the line</td></tr>
     <tr><td>To contribute</td><td>

     ```
     lib_GoogleGA4=/Users/olivierpicciotto/wrks/lib_GoogleGA4/.git:branch=master
     ```
     </td></tr>
     <tr><td>To simply use</td><td>

     ```
     lib_GoogleGA4=/Users/olivierpicciotto/wrks/lib_GoogleGA4//archive/master.zip
     ```
     </td></tr>
    </table>
3. Click the `Finish` button. This will automatically import the __lib_GoogleGA4__ project


## Mobile Library

Describes the mobile application global properties

### Shared Actions

#### InstallGA4

Installs the Google analytics client side. Must be called when the app Starts.


**variables**

<table>
<tr>
<th>name</th><th>comment</th>
</tr>
<tr>
<td>G_ID</td><td>The MeasurementID found in GA4 console in the form of G-XXXXXXXXXX</td>
</tr>
</table>

#### NotifyEvent

Call this when you want to notify a special event

**variables**

<table>
<tr>
<th>name</th><th>comment</th>
</tr>
<tr>
<td>EventData</td><td></td>
</tr>
<tr>
<td>EventName</td><td></td>
</tr>
</table>

#### PageEvent

Must be called when a Page changes. The best way to call this is within a **onCanActivate** AppGuard event



