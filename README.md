# Creditor Commerce Library Web
[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)

### Overview
As part of Pay by Account (PbA) Request for Payment product, SDK need to provide the ability for a Debtor to initiate non-Proxy journeys from the Merchant/Creditor web application.  Creditor Commerce Library/SDK facilitates this payment ability for Debtors. It can be integrated on any Website by following a few simple steps. The SDK enables distributors to get details of banks/DSP and to invoke the bank apps using the SDK. 
If the banking app is not available, the SDK alternatively allows the debtor to fall back on to the configured URL (which is configured by bank) usually net-banking on the on the device browser and proceed with for a quick and successful payment.

### Audience
External Participants to support the implementation and subsequent use of the Creditor Commerce Library for Pay by Account (PbA) Request for Payment product.

###	Scope
It covers integration and implementation of the Creditor Commerce SDK

## Contents
- [Functional overview](#functional-overview)
  - [Introduction](#functional-overview)
  - [Flow Diagram](#flow-diagram)
  - [Journey Use Cases](#journey-use-cases)
- [Technical overview](#technical-overview)
  - [Introduction](#technical-overview)
  - [Pre- requisites](#pre--requisites)
  - [Certified Browsers and Devices](#certified-browsers-and-devices)
  - [Folder Components](#folder-components)
  - [Creditor Commerce Library Integration Steps](#creditor-commerce-library-integration-steps)
    - [General requirements](#general-requirements)
    - [Integration Steps](#integration-steps)
  - [Creditor Commerce Library API Interface](#creditor-commerce-library-api-interface)
  - [Usages](#usages)
    - [Get DSP Details](#get-dsp-details)
    - [Invoke Bank App](#invoke-bank-app)
    - [Get Universal Link](#get-universal-link)
- [Appendices](#appendices)
  - [Template file](#template-file)
  - [Error Codes](#error-codes)
  - [Troubleshooting](#troubleshooting)
 

## Functional overview
### <u>Introduction</u>
The Creditor Commerce Library is a web library that enables a Merchant/Creditor to enable payments through a consumer selected debtor participant on a single device.

The SDK APIs/Functions enable the Merchant/Creditor to get information about the DSPs Participant banks which enabled for PBA-RFP. This information can be used by the Merchant/Creditor to display supported banks on their website during an invoice presentment. A consumer can see the available banks then select and launch a specific one which they want to pay with.


### <u>Flow Diagram</u>
![Generic Flow diagram of SDK user journey](https://user-images.githubusercontent.com/90037467/192294911-dbc328a8-0ae3-4658-8175-8dac7c393cf6.JPG)

###### Figure 1: Generic Flow diagram of SDK user journey 

### <u>Journey Use Cases</u>

**1. Pay Only Use Case (Single Immediate Payment) -** <br />
Pay only journey allows Consumers to use Pay by Account (PbA) Request for Payment method. A sample Pay only Consumer journey includes the following steps:
 - Consumer on merchant/creditor website presented with debtor’s list after checkout steps.
 - On selection of preferred debtor, bank app is launched with the help of Universal/App link. 
 - Consumer receives the transaction details and confirms the payment on the DSPs Participant bank App.
 - Consumer is presented the payment confirmation on the DSPs Participant bank App.
 - When the payment confirmation has been completed, Merchant/Creditor website displays the success page or cancel page based on transaction status.

The following sequence diagram shows the interaction between the Merchant/Creditor website and DSP Bank app:
![Non proxy journey Pay Without Agreement Sequence Diagram](img-url)
###### Figure 2: Non proxy journey Pay Without Agreement Sequence Diagram

**2. Pay and Link Use Case (Pay with Agreement)-** <br />
This journey will allow Merchants to encourage Consumers to make the payment and link their account for their next checkout.

A sample Pay and Link journey includes the following steps:
 -  Consumer on Merchant/Creditor website presented with debtor’s list after checkout steps.
 - On selection of preferred debtor, bank app is launched with the help of Universal/App link. 
 - Consumer receives the transaction details and confirms the payment on the DSPs Participant bank App. Also choose the account for linking for there next checkout.
 - Consumer is presented the Order confirmation on the DSP App.
 - When the order confirmation (Pay with Agreement) has been completed, Merchant/Creditor website displays the success page or cancel page based on transaction status.

The following sequence diagram shows the interaction between the Merchant/Creditor website and DSP app:
![Non proxy journey Pay with Agreement Diagram](img-url)
###### Figure 3: Non proxy journey Pay with Agreement Diagram

**3. Link Account Use Case –** <br />
Link Account journey allows the Consumer to link their account to the Merchant/Creditor.

A sample Link Account journey includes the following steps:
 - Consumer on Merchant/Creditor website presented with debtor’s list after checkout steps.
 - On selection of preferred debtor, bank app is launched with the help of Universal/App link 
 - Consumer receives the linking details and link the account on the DSPs Participant bank App. 
 - Consumer is presented the linking confirmation on the DSP App.
 - When the linking confirmation has been completed, Merchant/Creditor website displays the success page or cancel page based on linking status.

The following sequence diagram shows the interaction between the Merchant/Creditor website and DSP app:
![Non proxy journey Agreement Without Pay Diagram](img-url)
###### Figure 4: Non proxy journey Agreement Without Pay Diagram

## <u>Technical overview</u>
### <u>Introduction</u>
This section provides the instructions for integration of the Creditor Commerce Library with Merchant/Creditor’s web application's.

### <u>Pre- requisites</u>
Please ensure that the Mastercard process of Merchant/Creditor on boarding has been completed.

### <u>Certified Browsers and Devices</u>
Zapp has certified the Creditor Commerce SDK to work with the following browsers and respective devices:

|	|  Browser Name | Browser Version |
|---------------|---------------------------| -----------| 
| `Mobile (Android)` |	 |  |
|  |	Chrome | 104.0.5112.101	|
|  |	Firefox | 103.2.0	|
|  |	Edge | 104.0.1293.63	|
| `Mobile (iOS)` |	| 	|
|  |	Safari | 14.7.1	|
| `Desktop Windows` |	 | 	|
|  |	Chrome | 104.0.5112.101	|
|  |	Firefox | 103.0.2	
|  |	Edge | 104.0.1293.63	|
| `Mac` |	| 	|
|  |	Safari | 15.3	|
###### Table 1: 	Certified Browsers and devices

### <u>Folder Components</u>
The Creditor Commerce Library is a Vanilla JavaScript based component. It consists of a JavaScript file and a template file in a folder. 
The overall folder structure is represented in Figure below and contains:
1.	A **artefact.js** is a library file released in the form of versions of library.
2.	A **artefact.test.js** is a test file of library functions are unit tested with JavaScript testing framework.
3.	An **externalJs.template** file which contains sample code explaining the use of the library and how to invoke the APIs.
4.	A **LICENSE** is MasterCard license file to pe published with library.
5.	A **CONTIBUTING.md** file which contains a description for how developers can contribute the project
6.	A **README.md** file which contains a brief description about the SDK.
7.	A **CHANGELOG.md** file which contains a curated, chronologically ordered list of notable changes for each version of a project.

![Creditor Commerce Library folder structure](img-url)
###### Figure 5: Creditor Commerce Library folder structure

### <u>Creditor Commerce Library Integration Steps</u>
#### General Requirements
If Merchant/Creditor is integrating Creditor Commerce library into plain web-based HTML web application, then consider jQuery plugin to handle the html DOM manipulation work otherwise we don’t need jQuery plugin.
jQuery library version which is considered while integration:

|Component |                                    	Version                   |
|----------|----------------------------------------------------------------------|
| JQuery   |	3.5.1                                                             |
###### Table 3: Web Merchant/Creditor Library SDK – jQuery requirements

jQuery is used by the Merchant/Creditor website to perform various operations. It should be the first script to be imported in the project. jQuery can be included by printing the following HTML script tag in the parent HTML page in the header section on our project index page. This will import jQuery plugin into the project.

```javascript
	<head>
	...
    	<script src="http://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js"></script>
	...
    </head>
```

**Note**: This version of jQuery is the current certified version for Web Merchant/Creditor API functioning on the supported browsers and devices. Support for the latest version of jQuery is on the SDK Product Roadmap and will be considered for future releases of it.

#### Library Integration
The file name is: **Creditor_Commerce_Library_Api.zip** (see section Certified Browsers and Devices for downloading the version compatible). Alternatively, you can also clone the project. 

Extract the **Creditor_Commerce_Library_Api.zip** and add the **artefact.js** in the project. Import the JavaScript library **artefact.js** in the parent page where the bank list needs to be displayed by adding the script tag in the html page.

**Procedure steps** 

**A)** Import the library file **artefact.js** (downloaded on the Merchants/Creditors web application) in the parent page where the DSP’s needs to be displayed. 
```javascript
<html>
    <head>
    	<script src="../zapp-creditor-commerce-library-web/1.0.0/assets/artefact-1.0.0.js"></script>
    </head>
</html>
```

**B)** The Creditor Commerce library could be added into Merchant/Creditor web application by adding invoking getDspDetails function with cdnUrl location. Please follow sample code snapshot for the same.
	
**Note**: This will fetch DSP list. Merchant can show case the list as per their implementation.
```javascript
var dspCdnLocation = "https://mastercard-provided-cdn-file-location"; // CDN location to fetch the DSP details
$(document).ready(function() {
	/*
	* The only data that is required to be passed is cdn file url to get the onboarded DSP list and its details to show
	*    the details on merchant side.
	*/
	var invokeGetDspDetailsApi = function() {
		zappCreditorCommerceApi.getDspDetails(dspCdnLocation).then(function(result) {
			merchantFunctionToRenderDspLogoAndDetails();
		})
		.catch(function (error) {
			console.log(error);
		});
	};
	invokeGetDspDetailsApi();
});
```

**Note**: 
For integration of library into website developed using frontend framework like Angular or ReactJs then follow native steps. For Angular application V2+ add library path into angular.json file like below snapshot. 
Example:
```javascript
"architect":{
	"build":{
		"options": {
			"scripts": [
				...
				...
				"../zapp-creditor-commerce-library-web/1.0.0/assets/artefact-1.0.0.js"
			]
		}
	}
}
```

### <u>Creditor Commerce Library API Interface</u>
The Creditor Commerce Library API interface has the following functions and objects to be integrated by the Merchant/Creditor web application.

**1. Journey Type Object**:<br />
Merchant website can use **zappCreditorCommerceJourneyTypes** object to access the journey types provided by SDK. Merchant can access the object via **zappCreditorCommerceApi** global instance.

```javascript
zappCreditorCommerceApi.zappCreditorCommerceJourneyTypes = {
	requestToPay:"RequestToPay",
    requestToLink:"RequestToLink"
};
```

**Note**: 
 	If Creditor/Merchant wants to initiated Payment Request Journey then request type must be passed to SDK is ***“requestToPay”***  
	If Creditor/Merchant wants to initiated Link Account Journey, then request type must be passed to SDK is ***“requestToLink”***  

**2. getDspDetails(cdnUrl)**:<br />
Fetch the list of supported DSPs Participant banks by using this function. It accepts one parameter **cdnUrl** (provided by MasterCard onboarding team)
The function returns the JSON array which contains following DSP details, 

 - *dspName* 
 - *dspApiVersion*
 - *dspLogoURL*
 - *dspUniqueId* 
 - *appIconHash*

**Note**: 
	Use this function for Pay only, Pay and Link, Link only journey’s and it returns the DSP list.

|     Request Parameter name    |     Parameter description                                                                                                             |     Parameter source                                                                                                                                                       |
|-------------------------------|---------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| cdnUrl                        | This   CDN file is containing DSP related information.  SDK will provide the DSPs list to creditor by consuming CDN URL provided.     | Merchant   needs to provide this URL as a parameter to invoke the function.     Note:   CDN URL must be the HTTPS URL provided by Mastercard at the time of onboarding.    |


|     Response Parameter name    |     Parameter description                                                                                  |
|--------------------------------|------------------------------------------------------------------------------------------------------------|
|     dspLogo                    |     Absolute   path for the logo of the debtor                                                             |
|     dspName                    |     It   contains the DSP name of particular DSP.                                                          |
|     dspUniqueId                |     Unique   Id created for specific Debtor.                                                               |
|     dspApiVersion              |     Parameter   value refer to the API version the DSP is currently on (V4/V5). It’s an   integer value    |
|     appIconHash                |     Hash   value for Debtor logo.                                                                          |


**3. InvokeApp (dspId, secureToken, businessType, journeyType)**:<br />
Function invokes the universal link for the selected DSP’s. Merchant can use this library method to launch the bank app.

|     Request Parameter name    |     Parameter description                              |     Parameter source                                                                                                            |
|-------------------------------|--------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------|
|     **dspId**                     |     This   is the dspUniqueId of the selected bank.    |     Creditor/Merchant   needs to provide the selected dspId value, which received from the **getDspDetails**   function response    |
| **secureToken** | **secureToken** value should be **paymentRequestLifecycleId** value if Creditor invoked Create Payment API **OR** **secureToken** value should be **agreementLifecycleId** value if Creditor invoked Create Link API.  | It is returned by Zapp in response to create payment Request API / create link API   **paymentRequestLifecycleId / agreementLifecycleId**   |
|     **businessType**    |     businessType is a predefined domain or   commercial product under which this API request is being sent. The   Participant must be enrolled for the valid business type and for product PBA   RFP the business type value is **2**.    |     Merchant/Creditor needs to provide   this value to SDK.      |
|     **journeyType**    |     **journeyType**   value will be either of the below constant ENUM provided by library   **journeyType** object exposed above.     journeyType   object exposed by SDK:      **zappCreditorCommerceJourneyTypes**           <br />Creditor   needs to pass      **zappCreditorCommerceJourneyTypes.requestToPay** if creditor   invoked Create Payment API.<br />           Creditor   needs to pass      **zappCreditorCommerceJourneyTypes.requestToLink** if creditor   invoked Create Link API.    |     This Object is exposed by Creditor   Commerce SDK in the form ENUM object.     Creditor needs to provide the   appropriate value while calling the function.     |


**4. getUniversalLink (dspId, secureToken, businessType, journeyType)**:<br />
This is optional API/function exposed by Creditor Commerce SDK. 

If Merchant/Creditor don’t want to use the library’s invokeApp functionality and want to invoke the app by their own implementation, then this method provides the response of Universal link in parameterised form. Creditor will use the response of the function to invoke the bank app.

|     Request Parameter name    |     Parameter description                              |     Parameter source                                                                                                            |
|-------------------------------|--------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------|
|     **dspId**                     |     This   is the dspUniqueId of the selected bank.    |     Creditor/Merchant   needs to provide the selected dspId value, which received from the **getDspDetails**   function response    |
| **secureToken** | **secureToken** value should be **paymentRequestLifecycleId** value if Creditor invoked Create Payment API **OR** **secureToken** value should be **agreementLifecycleId** value if Creditor invoked Create Link API.  | It is returned by Zapp in response to create payment Request API / create link API   **paymentRequestLifecycleId / agreementLifecycleId**   |
|     **businessType**    |     businessType is a predefined domain or   commercial product under which this API request is being sent. The   Participant must be enrolled for the valid business type and for product PBA   RFP the business type value is **2**.    |     Merchant/Creditor needs to provide   this value to SDK.      |
|     **journeyType**    |     **journeyType**   value will be either of the below constant ENUM provided by library   **journeyType** object exposed above.     journeyType   object exposed by SDK:      **zappCreditorCommerceJourneyTypes**     <br />      Creditor   needs to pass      **zappCreditorCommerceJourneyTypes.requestToPay** if creditor   invoked Create Payment API.  <br />         Creditor   needs to pass      **zappCreditorCommerceJourneyTypes.requestToLink** if creditor   invoked Create Link API.    |     This Object is exposed by Creditor   Commerce SDK in the form ENUM object.     Creditor needs to provide the   appropriate value while calling the function.     |


|     Response                    |     Parameter description                                                                                                                        |     Parameter source                                   |
|---------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------|
|     **Parameterised URI String**    |     This   is the parameterised URI String, which is combination of dspUniversalLink,   and the request parameters passed to these functions.    |     Response   from Creditor Commerce Library          |

Below are the details regarding query parameters which will be passed along with universal/app link –
```
{{<<host>>://<<dsp bank domain>>/<<path>>}}? lifeCycleId={{<<lifecycle value>>}}&businessType={{<<businesstype value>>}}&journeyType={{<<Journey Type>>}}
```
### <u>Usages</u>
Use the following steps to invoke the SDK’s API in the Merchant/Creditor web application.

#### **Get DSP Details**
Use this library method to fetch the registered DSP’s participant bank and render on merchant web application. 
Function Name: 
```
zappCreditorCommerceApi.getDspDetails(cdnUrl):
```

**Note**: CDN URL file path is provide by Mastercard Zapp during onboarding. Creditor/Merchant’s needs to use this path at the time of getDspDetails function call as a parameter. 
```
var cdnUrl = "https://mastercard-provided-cdn-file-URL";// CDN URL to get the DSP details
$(document).ready(function() {
    var CreditorFunctionToInvokeGetDspDetailsApi = function () {
        zappCreditorCommerceApi.getDspDetails(cdnUrl).then(function(result) {
    
            //Promise is resolved, use the zappCreditorCommerceApiobjects to display the bank details.
            //Two zappCreditorCommerceApiobjects are:
    
            //zappCreditorCommerceApi.getDspDetails – A list of banks with the following details.
            //dspLogo: Bank logo "https://cdn/..../bankName-bank.png"
            //dspName: The name of DSP’s participant bank
            //dspUniqueId: Unique Id created for specific Debtor.
            //dspApiVersion: DSP API versions
            //appIconHash: This is bank logo base64encoded hash value
    
            //zappCreditorCommerceApi.dspCount– Total number of banks configured
    
            //renderDspList();
            
            }).catch(function (error) {
            // Merchant/Creditor specific code for exception handling
        });
    };
}
```
Sample Response: 
```
[ {
    "dspUniqueId": "partnerBankV5001",
    "dspName": "Partner Bank",
    "dspLogo": "https://www.ghobank.com/dsp-logos/partner-bank.png",
    "dspApiVersion": 4,
    "dspAppIconHash": "JtRQFjnON6ny_Gps_cBHuYiR4ZeKaEL50miNUrI8X28="
},
...
]
```
#### **Invoke Bank App**:
To invoke the universal/App link use this library method. This method uses browser native functionality to open link in a new tab when we select particular DSP. If the bank app is installed then respective bank app will launch, if not then its configured Netbanking URL will get open.

Function Name:
```
zappCreditorCommerceApi.invokeApp = function (dspId, secureToken, businessType, journeyType)
```
**Note**: Request parameters are provided by the merchant to the library function.
```
$(document).ready(function() {
    var MerchantFunctionToinvokeAppApi = function () {
    //- invoke app function is used to invoke a parameterised universal link for a perticular DSP selected by merchant

   //These parameters are required for invokeApp function

   /** if selected journey is requestToPay **/

   zappCreditorCommerceApi.invokeApp(dspUniqueId, paymentRequestLifecycleId, businessType, zappCreditorCommerceApi.zappCreditorCommerceJourneyTypes.requestToPay);
    
    //a. dspUniqueId - Selected bank uniqueId.
    //b. paymentRequestLifeCycleId - It will received from createPaymentAPI() response
    //c. businessType – ‘2’ for PBA-RFP product
    //d. journeyType – ‘RequestToPay’
    
   /** if selected journey is requestToLink&Pay **/
    zappCreditorCommerceApi.invokeApp(dspUniqueId, paymentRequestLifecycleId, businessType, zappCreditorCommerceApi.zappCreditorCommerceJourneyTypes.requestToPay);
    //The only difference in this journey we append "agreementType" parameter in POST data
    //when we call createPayment gateway API

    //a. dspUniqueId - Selected bank uniqueId.
    //b. paymentRequestLifeCycleId - It will received from createPaymentAPI() response
    //c. businessType – ‘2’ for PBA-RFP product
    //d. journeyType – ‘requestToLink’

    /** if selected journey is requestToLink **/
    zappCreditorCommerceApi.invokeApp(dspUniqueId, agreementLifecycleId, businessType, zappCreditorCommerceApi.zappCreditorCommerceJourneyTypes.requestToLink);
    
    //a. dspUniqueId - Selected bank uniqueId.
    //b. agreementLifecycleId - It will received from createLinkAPI() response
    //c. businessType – ‘2’ for PBA-RFP product
    //d. journeyType – ‘requestToLink’
    };
}
```
**Note**: As a response we can see the library opens up the bank app, for a selected DSP.

#### **Get Universal Link**:
Function returns the parameterised universal link for the selected DSP’s which merchant can use as per the way they want to launch bank app.
Function Name: 
```
zappCreditorCommerceApi.getUniversalLink = function (dspId, secureToken, businessType, journeyType);
```
**Note**: Request parameters are provided by the merchant to the library function.
```
$(document).ready(function() {
    var MerchantFunctionTogetUniversalLinkApi = function () {
		//- getUniversalLink app function is used to fetch a parameterised universal link from library method and  merchant then can use this url as per their implementation.

	   //These parameters are required for getUniversalLink function

	   /** if selected journey is requestToPay **/
		
		var parameterisedLink = 
	   zappCreditorCommerceApi.getUniversalLink(dspUniqueId, paymentRequestLifecycleId, businessType, zappCreditorCommerceApi.zappCreditorCommerceJourneyTypes.requestToPay);
		
		//a. dspUniqueId - Selected bank uniqueId.
		//b. paymentRequestLifeCycleId - It will received from createPaymentAPI() response
		//c. businessType – ‘2’ for PBA-RFP product
		//d. journeyType – ‘RequestToPay’
		
	   /** if selected journey is requestToLink&Pay **/
	   var parameterisedLink = 
		zappCreditorCommerceApi.getUniversalLink(dspUniqueId, paymentRequestLifecycleId, businessType, zappCreditorCommerceApi.zappCreditorCommerceJourneyTypes.requestToPay);
		//The only difference in this journey we append "agreementType" parameter in POST data
		//when we call createPayment gateway API

		//a. dspUniqueId - Selected bank uniqueId.
		//b. paymentRequestLifeCycleId - It will received from createPaymentAPI() response
		//c. businessType – ‘2’ for PBA-RFP product
		//d. journeyType – ‘requestToLink’

		/** if selected journey is requestToLink **/
		var parameterisedLink = 
		zappCreditorCommerceApi.getUniversalLink(dspUniqueId, agreementLifecycleId, businessType, zappCreditorCommerceApi.zappCreditorCommerceJourneyTypes.requestToLink);
		
		//a. dspUniqueId - Selected bank uniqueId.
		//b. agreementLifecycleId - It will received from createLinkAPI() response
		//c. businessType – ‘2’ for PBA-RFP product
		//d. journeyType – ‘requestToLink’
    };
}
```
Sample Response: 
```
// For Request to Pay
var parameterisedLink =    "https://zts1.co.uk/sbi-demo-bank/?lifeCycleId={{response.lifecycleId}}&businessType={{predefined-commercial-product-type}}&journeyType=RequestToPay";

// For Request to Link
var parameterisedLink = "https://zts1.co.uk/sbi-demo-bank/?lifeCycleId={{response.lifecycleId}}&businessType={{predefined-commercial-product-type}}&journeyType=RequestToLink";    
```

## <u>Appendices</u>
### <u>Template file</u>
The **externalJs.template** file contains the sample code to demonstrate the use of the Creditor Commerce Library SDK. This code also depicts the implementation of the custom method to post payment request to the Merchant/Creditor Server. This file resides in the Creditor Commerce Library SDK folder along with the artefact.js file. 

**Note**: Any data elements and comments in Italic are a Merchant/Creditor specific data element which must be provided by the Merchant/Creditor. 

**Assumption**	This is the JS file used on the Merchant/Creditor’s website.


##### Sample code:

```javascript	
/** This configuration file template is used to define and override variables and functions for the creditor commerce library
 **/
/* Define the variables */
var zappVersion = "1.0.0"; // Current web merchant button library version.
var merchantPollInterval = 5000; // Merchant poll interval of 5 seconds to poll the merchant server for link and payment notification.
var dspCdnLocation = "https://domain-name/cdn-file-location"; // CDN location to fetch the DSP details
var merchantCustomUniversalLink = null; // This variable holds the reference to the custom parameterised universal-link return to merchant rather than invoke function

/* Override the 
merchantFunctionToRenderDspLogoAndDetails() 
and 
merchantFunctionToHandleInvokeFunctionApi()
and 
merchantFunctionToHandleGetUniversalLinkFunctionApi() 
functions.
*/

$(document).ready(function () {
    /* 
     * 1. The only data that is required to be passed is cdn file url to get the onboarded DSP list and its details to show
     *    the details on merchant side. 
     * 
     */

    var invokeGetDspDetailsApi = function () {
        zappCreditorCommerceApi.getDspDetails(dspCdnLocation).then(function (result) {
            merchantFunctionToRenderDspLogoAndDetails();
        })
            .catch(function (error) {
                console.log(error);
            });
    };
    invokeGetDspDetailsApi();
});

/* 
 *
 *  2.  SUCCESSFUL RESPONSE - Upon receipt of a successful response from the server:
 *      
 *      A.  Library creates a response object dspDetail by populating the following mandatory attributes:
 *      dspUniqueId, dspName, dspLogo, dspApiVersion, dspAppIconHash
 *      NOTE: dspCount is length of list that is created by library with required attributes. 
 *      At merchant side we have to use this object to populate the list as per merchants requirements.
 *      Below sample represents list-group for representation of dsp list
 *
 */

merchantFunctionToRenderDspLogoAndDetails = function () {
    for (i = 0; i < zappCreditorCommerceApi.dspCount; i++) {
        $("#merchantBankListContainer").append(`<li class='list-group-item'><img class="cfiLogo" src="${zappCreditorCommerceApi.dspDetail[i].dspLogo}" alt="${zappCreditorCommerceApi.dspDetail[i].dspName}"/>` +
            `<span class="cfiNameLabel"><p class="mb-0">${zappCreditorCommerceApi.dspDetail[i].dspName}</p><span>Bank Account</span></span><a id="${zappCreditorCommerceApi.dspDetail[i].dspUniqueId}" href="#" class="select-link" onclick="submitUserChoice('${zappCreditorCommerceApi.dspDetail[i].dspUniqueId}','${zappCreditorCommerceApi.dspDetail[i].dspName}')">Select</a></li>`);
    }
};

/* 
 *
 *  3.  Library has two methods;
        A. Invoke Universal-link 
 *      
 *      B. Return parameterised universal-link to merchant as a string so that merchant can select their own way to use it.
 *      merchantCustomUniversalLink = true;
 *      
 *      CreatePayment API details or CreateLink API Details can be used based on journey Type 
 */

function merchantFunctionToHandleInvokeFunctionApi(bankId) {
    var dspID = bankId.id;
    var response = '';
    var merchantRequestForPayPostData = {
        // Merchant Request for Payment Post Data 
    };
    CreatePayment() {
        jQuery.ajax({
            url: { APIURL },
            dataType: "json",
            contentType: "application/json; charset=UTF-8",
            type: "put",
            async: false,
            data: JSON.stringify(postData),
            success: function (merchantRequestForPaymentResponseObject) {
                ajaxFlag = true; // flag to indicate that ajax call is completed successfully
                response = {
                    success: true,
                    secureToken: merchantRequestForPaymentResponseObject.paymentRequestLifeCycleId,
                    retrievalExpiryInterval: res.retrievalExpiryTimeInterval,
                    confirmationExpiryInterval: res.confirmationExpiryTimeInterval
                    //other details
                };
            },
            error: function (merchantRequestForPaymentResponseObject) {
                // Merchant specific code to handle error
            }
        });
    }

    CreateLink() {
        jQuery.ajax({
            url: { APIURL },
            dataType: "json",
            contentType: "application/json; charset=UTF-8",
            type: "put",
            async: false,
            data: JSON.stringify(postData),
            success: function (merchantRequestForPaymentResponseObject) {
                ajaxFlag = true; // flag to indicate that ajax call is completed successfully
                response = {
                    success: true,
                    secureToken: merchantRequestForPaymentResponseObject.agreementLifecycleId,
                    retrievalExpiryInterval: res.retrievalExpiryTimeInterval,
                    confirmationExpiryInterval: res.confirmationExpiryTimeInterval
                    //other details
                };
            },
            error: function (merchantRequestForPaymentResponseObject) {
                // Merchant specific code to handle error
            }
        });
    }

    // If the merchantCustomUniversalLink is false then invokeApp function is invoked to launch universal link

    if (merchantCustomUniversalLink == false) {
        //Web Merchant API function to invoke Bank APP
        zappCreditorCommerceApi.invokeApp(dspUniqueId, response.paymentRequestLifeCycleId, businessType, journeyType);  // These parameters are required for opening the bank app
    }
    else {
        var libReturnUrl = zappCreditorCommerceApi.getUniversalLink(dspUniqueId, response.paymentRequestLifeCycleId, businessType, journeyType);
        displayResponse(libReturnUrl);
    }
}

/* 
 *  3.  Merchant can decide to keep this optional way of notify about transaction,
 *      There are various way to fetch transaction status back,
 *      A: Using Notify function call or 
 *      B: Using window.event emitter. Merchant call back URL is function at merchant side can be used to handle to show    *       receipt of transaction
 */

function merchantFunctionToHandleInvokeNotifyApi(secureToken) {

    /*  NOTE: If jQuery.ajax is used for polling the merchant server and the method is GET then Zapp suggests doing the following to prevent caching:
     * 
     *  Step 1: Add the following property to AJAX call:
     *          cache: false
     *  
     *  Step 2: Add a cache busting parameter to the polling URL. This parameter can be any random number (for example, date timestamp) 
     *          appended to the polling URL. For example, if the polling URL is "/responseForPayment.aspx?secureToken=12345678&orderId=12345" then
     *          the URL with a cache busting parameter called time would be:  
     *          "/responseForPayment.aspx?secureToken=12345678&orderId=12345&time="+Date.now()
     *  
     */

    /*  1.  This method polls the merchant server for a response every X seconds.
     *      X is the value for merchantPollInterval.
     *
     *  2.  secureToken must be passed to the merchant server to enable polling the zapp server for a 
     *      Payment notification.
     *
     *  3.  SUCCESSFUL RESPONSE - Upon receipt of a successful response from the merchant server:
     *
     *      A.  abort transaction and display result
     *
     */
    var abort = false;
    data.success = true;
            /*
             *      B.  if not then , Continue further order processing.
             *
             */
             
             * 5.  ERROR - Upon receipt of an error from the merchant server:
             *      
             * A.Create a error object and return error code with messages
    *
             * /
            var abort = true;

    jQuery.ajax({
        url: merchantPollingUrl
    })
        , success : function(data) {
        }
            , error: function(data) {
    }
}

/* Place any other error handling logic here. Error codes returned from library handled here with eventType 'zappCreditorCommerceApiError' */

function listener(event) {
    var evData = event.data;
    // event.data contains the Error object with the following information
    //      errorDesc
    //      errorId
    //      errorTimestamp

    if (evData.eventType == "zappCreditorCommerceApiError") {
        console.log(evData.data); // Merchant specific code to handle the errors
    }
}

if (window.addEventListener) {
    addEventListener("message", listener, false)
} else {
    attachEvent("onmessage", listener)
}
```

---
### <u>Error Codes</u>
The Creditor Commerce Library captures some errors. It defines a set of predefined errors which are reported to the merchant web applications.
The SDK returns an event which contains object with error Id, error description and a timestamp. Below mentioned table describes all the predefined error codes in Creditor Commerce Library.
##### Sample error object:

```javascript
zappCreditorCommerceApiError:{
“errorDesc”: "Error Description",
“errorId”: "Sxxx",
“errorTimestamp”: "Mon, 24 Aug YYYY 00:09:02 GMT"
}
```
###### Table 4: 	Creditor Commerce Library API SDK – Error Codes

Error codes|Error description|Cause of the error
-----------|-----------------|------------------
S1001|DSP Id is undefined|When **zappCreditorCommerceApi.invokeApp** function is invoked without DSP Id.<br><br>Example: **zappCreditorCommerceApi.invokeApp(undefined,paymentRequestLifeCycleId,’2’, 'journeyType')**|
S1002|DSP Id is null or empty|When **zappCreditorCommerceApi.invokeApp** function is invoked with empty DSP Id or with null value.<br><br>Example: **zappCreditorCommerceApi.invokeApp(‘’, paymentRequestLifeCycleId, ’2’, 'journeyType')**<br>Or<br>**zappCreditorCommerceApi.invokeApp(null, paymentRequestLifeCycleId, ’2’, 'journeyType')**
S1003|paymentRequestLifeCycleId is undefined|When **zappCreditorCommerceApi.invokeApp** function is invoked without paymentRequestLifeCycleId.<br><br>Example: **zappCreditorCommerceApi.invokeApp(dspUniqueId,undefined,’2’, 'journeyType')**
S1004|PaymentRequestLifeCycleId is null or empty|When **zappCreditorCommerceApi.invokeApp** function is invoked with null PaymentRequestLifeCycleId.<br><br>Example: **zappCreditorCommerceApi.invokeApp(dspUniqueId, null, ’2’, 'journeyType')**<br>Or<br>**zappCreditorCommerceApi.invokeApp(dspUniqueId, ’’, ’2’, 'journeyType')**
S1005|Business type is undefined|When **zappCreditorCommerceApi.invokeApp** function is invoked with Business type is undefined.<br><br>Example: **zappCreditorCommerceApi.invokeApp(dspUniqueId, paymentRequestLifeCycleId, undefined, 'journeyType')**<br>Or<br>**zappCreditorCommerceApi.invokeApp(dspUniqueId,null, ’2’, 'journeyType')**
S1006|Business type is null or empty|When **zappCreditorCommerceApi.invokeApp** function is invoked with empty productType or with null value.<br><br>Example: **zappCreditorCommerceApi.invokeApp(dspUniqueId, paymentRequestLifeCycleId, '', 'journeyType')**<br>Or<br>**zappCreditorCommerceApi.invokeApp(dspUniqueId, paymentRequestLifeCycleId, null, 'journeyType')**
S1007|No data present for DSP Id in provided CDN file|When No data present for DSP Id in provided CDN file then library throw error.
S1008|Empty URL, check and reconfigure DSP File URL.|When library gets Empty url of cdn then it throw error.
S1009|Invalid protocol. Secure protocol https is only supported.|When CDN URL is provied with invalid protocol then it throw error.
S1011, S1012, S1013, S1014, S1015, S1016, S1017, S1018, S1019 |Configuration file dsplist.json is invalid. Please recheck and configure.| When there is wrong configuration file dsplist.json and due to which its invalid then in this case library checks for that and throw error.
S1020| Journey type is undefined|When **zappCreditorCommerceApi.invokeApp** function is invoked with Journey type is undefined.<br><br>Example: **zappCreditorCommerceApi.invokeApp(dspUniqueId, paymentRequestLifeCycleId, '2', undefined)**
S1021| Journey type is null or empty|When **zappCreditorCommerceApi.invokeApp** function is invoked with Journey type value is null or empty passed.<br><br>Example: **zappCreditorCommerceApi.invokeApp(dspUniqueId, paymentRequestLifeCycleId, '2', null)**<br>Or<br>**zappCreditorCommerceApi.invokeApp(dspUniqueId, paymentRequestLifeCycleId, '2', '')**
S1022| Agreement life cycle id is undefined|When **zappCreditorCommerceApi.invokeApp** function is invoked with Journey type is linking and Agreement life cycle id is undefined.<br><br>Example: **zappCreditorCommerceApi.invokeApp(dspUniqueId, undefined, '2', 'journeyType')**
S1023| Agreement life cycle id is null or empty|When **zappCreditorCommerceApi.invokeApp** function is invoked with Journey type is link and Agreement life cycle id is is null or empty passed.<br><br>Example: **zappCreditorCommerceApi.invokeApp(dspUniqueId, '', '2', 'journeyType')**<br>Or<br>**zappCreditorCommerceApi.invokeApp(dspUniqueId, null, '2', 'journeyType')**
MC1001| Technical error occurred | If Api gets Failed, Response is not 200
MC1002| Technical error occurred | If Api gets Failed, Response is not 201
MC1003| Technical error occurred | If Api gets Failed, Response is not 202
MC1004| Technical error occurred | If Api gets Failed, Response is not 203


---
### <u>Troubleshooting</u>
This section covers the different troubleshooting scenarios and the behaviour of the Creditor Commerce Library API. 
1. For the SDK to work as expected the default browser settings should allow pop ups to open on the mobile device.
2. If merchant is using jquery ajax call to invoke Submit RFP then merchant must wait for the ajax call to complete to invoke the **zappCreditorCommerceApi.invokeApp** function of the SDK. Alternatively merchant can use the async: false parameter when making an ajax call. Refer the template file in the SDK for an example.
3. The Creditor Commerce Library API SDK opens a new tab to redirect to the universal link provided by the bank. If the bank app is not installed on the consumer’s device then the page displayed on the new opened tab is handled by the bank. 
 
 #### Contributing
For major changes, please open an issue first to discuss what you would like to change.
Please make sure to update tests as appropriate.


#### License
Copyright 2022 Mastercard


Licensed under the Apache License, Version 2.0 (the "License"); you may not use this file except in compliance with
the License. You may obtain a copy of the License at:


http://www.apache.org/licenses/LICENSE-2.0


Unless required by applicable law or agreed to in writing, software distributed under the License is distributed on
an "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied. See the License for the
specific language governing permissions and limitations under the License.
