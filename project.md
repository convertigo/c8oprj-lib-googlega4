
# ![](https://github.com/convertigo/convertigo/blob/develop/engine/src/com/twinsoft/convertigo/beans/core/images/project_color_16x16.png?raw=true "Project") lib_GoogleGA4

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


<details><summary><span style="color:DarkGoldenRod"><i>Connectors</i></span></summary><blockquote><p>


## ![](https://github.com/convertigo/convertigo/blob/develop/engine/src/com/twinsoft/convertigo/beans/connectors/images/sqlconnector_color_16x16.png?raw=true "SqlConnector") void

void connector, replace or don't use it

<details><summary><span style="color:DarkGoldenRod"><i>Transactions</i></span></summary><blockquote><p>


### ![](https://github.com/convertigo/convertigo/blob/develop/engine/src/com/twinsoft/convertigo/beans/transactions/images/sqltransaction_color_16x16.png?raw=true "SqlTransaction") void

does nothing
</p></blockquote></details>
</p></blockquote></details>

<details><summary><span style="color:DarkGoldenRod"><i>Mobile Application</i></span></summary><blockquote><p>


## ![](https://github.com/convertigo/convertigo/blob/develop/engine/src/com/twinsoft/convertigo/beans/core/images/mobileapplication_color_16x16.png?raw=true "MobileApplication") Application

Describes the mobile application global properties

<details><summary><span style="color:DarkGoldenRod"><i>Pages</i></span></summary><blockquote><p>


<details><summary><b>Page</b> : My First Page as root page</summary><blockquote><p>


### ![](https://github.com/convertigo/convertigo/blob/develop/engine/src/com/twinsoft/convertigo/beans/ngx/components/images/pagecomponent_color_16x16.png?raw=true "PageComponent") Page

My First Page as root page
</p></blockquote></details>

<details><summary><b>Page1</b> : My First Page as root page</summary><blockquote><p>


### ![](https://github.com/convertigo/convertigo/blob/develop/engine/src/com/twinsoft/convertigo/beans/ngx/components/images/pagecomponent_color_16x16.png?raw=true "PageComponent") Page1

My First Page as root page
</p></blockquote></details>

<details><summary><b>Page2</b> : My First Page as root page</summary><blockquote><p>


### ![](https://github.com/convertigo/convertigo/blob/develop/engine/src/com/twinsoft/convertigo/beans/ngx/components/images/pagecomponent_color_16x16.png?raw=true "PageComponent") Page2

My First Page as root page
</p></blockquote></details>
</p></blockquote></details>

<details><summary><span style="color:DarkGoldenRod"><i>Shared Actions</i></span></summary><blockquote><p>


<details><summary><b>InstallGA4</b> : Installs the Google analytics client side</summary><blockquote><p>


### ![](https://github.com/convertigo/convertigo/blob/develop/engine/src/com/twinsoft/convertigo/beans/ngx/components/images/uiactionstack_color_16x16.png?raw=true "UIActionStack") InstallGA4

Installs the Google analytics client side. Must be called when the app Starts.


<span style="color:DarkGoldenRod">Variables</span>

<table>
<tr>
<th>
name
</th>
<th>
comment
</th>
</tr>
<tr>
<td>
<img src="https://github.com/convertigo/convertigo/blob/develop/engine/src/com/twinsoft/convertigo/beans/ngx/components/images/uistackvariable_16x16.png?raw=true "  alt="UIStackVariable" >&nbsp;G_ID
</td>
<td>
The MeasurementID found in GA4 console in the form of G-XXXXXXXXXX
</td>
</tr>
</table>

</p></blockquote></details>

<details><summary><b>NotifyEvent</b> : Call this when you want to notify a special event</summary><blockquote><p>


### ![](https://github.com/convertigo/convertigo/blob/develop/engine/src/com/twinsoft/convertigo/beans/ngx/components/images/uiactionstack_color_16x16.png?raw=true "UIActionStack") NotifyEvent

Call this when you want to notify a special event

<span style="color:DarkGoldenRod">Variables</span>

<table>
<tr>
<th>
name
</th>
<th>
comment
</th>
</tr>
<tr>
<td>
<img src="https://github.com/convertigo/convertigo/blob/develop/engine/src/com/twinsoft/convertigo/beans/ngx/components/images/uistackvariable_16x16.png?raw=true "  alt="UIStackVariable" >&nbsp;EventData
</td>
<td>

</td>
</tr>
<tr>
<td>
<img src="https://github.com/convertigo/convertigo/blob/develop/engine/src/com/twinsoft/convertigo/beans/ngx/components/images/uistackvariable_16x16.png?raw=true "  alt="UIStackVariable" >&nbsp;EventName
</td>
<td>

</td>
</tr>
</table>

</p></blockquote></details>

<details><summary><b>PageEvent</b> : Must be called when a Page changes</summary><blockquote><p>


### ![](https://github.com/convertigo/convertigo/blob/develop/engine/src/com/twinsoft/convertigo/beans/ngx/components/images/uiactionstack_color_16x16.png?raw=true "UIActionStack") PageEvent

Must be called when a Page changes. The best way to call this is within a **onCanActivate** AppGuard event
</p></blockquote></details>
</p></blockquote></details>
</p></blockquote></details>
