# Template Healthcare EHR Appointmetns Process API

+ [License Agreement](#licenseagreement)
+ [Use Case](#usecase)
+ [Considerations](#considerations)
	* [Cloudhub security considerations](#cloudhubsecurityconsiderations)
	* [APIs security considerations](#apissecurityconsiderations)
+ [Run it!](#runit)
	* [Running on premise](#runonopremise)
	* [Running on Studio](#runonstudio)
	* [Running on Mule ESB stand alone](#runonmuleesbstandalone)
	* [Running on CloudHub](#runoncloudhub)
	* [Deploying your Anypoint Template on CloudHub](#deployingyouranypointtemplateoncloudhub)
	* [Creating externally reachable proxy and applying policies](#proxy)
	* [Properties to be configured (With examples)](#propertiestobeconfigured)

# License Agreement <a name="licenseagreement"/>
Note that using this template is subject to the conditions of this [License Agreement](AnypointTemplateLicense.pdf).
Please review the terms of the license before downloading and using this template. In short, you are allowed to use the template for free with Mule ESB Enterprise Edition, CloudHub, or as a trial in Anypoint Studio.

# Use Case <a name="usecase"/>
As a Healthcare Clinic Portal user I want a service to manage Appointment data from in EHR system.

This template should serve as a foundation for implementing an API that manages Appointments in the EHR FHIR System API and it is 
provided as part of the Healthcare Templates Solution. The API is defined using 
[RAML 1.0](http://raml.org) and this implementation uses [APIkit](https://docs.mulesoft.com/anypoint-platform-for-apis/apikit-basic-anatomy#basic-anatomy). 
EHR Appointments Process API triggers the underlying microservices defined in EHR FHIR System API in JSON 
(FHIR specification [version 1.0.2 DSTU2](https://www.hl7.org/FHIR/DSTU2/index.html)).

EHR Appointments Process API is part of the Healthcare Templates Solution and it is interconnected with EHR FHIR System API and Web Portal Experience API.

# Considerations <a name="considerations"/>
To run this Anypoint Template, there are certain preconditions that must be considered. **Failling to do so could lead to unexpected behavior of the template.**
Use Anypoint Studio v6.1.0+ and Mule ESB 3.8.1+ to run this template.

## APIs security considerations <a name="apissecurityconsiderations"/>
This Process API is meant to be deployed to CloudHub and managed using the API Platform Manager.

### Exposing external endpoints with HTTP
+ It is triggered by Web Portal Experience API using HTTP

### Exposing internal endpoints with RAML and HTTP
+ It is also interconnected internally with EHR FHIR System API, which are deployed on a CloudHub.


### Running the application

# Run it! <a name="runit"/>
Simple steps to get Healthcare EHR Appointments Process API running.
See below.

## Running on premise <a name="runonopremise"/>
In this section we detail the way you should run your Anypoint Template on your computer.

### Where to Download Anypoint Studio and Mule ESB
First thing to know if you are a newcomer to Mule is where to get the tools.

+ You can download Anypoint Studio from this [Location](http://www.mulesoft.com/platform/studio)
+ You can download Mule ESB from this [Location](http://www.mulesoft.com/platform/soa/mule-esb-open-source-esb)

### Importing an Anypoint Template into Studio
Anypoint Studio offers several ways to import a project into the workspace, for instance: 

+ Anypoint Studio generated Deployable Archive (.zip)
+ Anypoint Studio Project from External Location
+ Maven-based Mule Project from pom.xml
+ Mule ESB Configuration XML from External Location

You can find a detailed description on how to do so in this [Documentation Page](https://docs.mulesoft.com/anypoint-studio/v/6/importing-and-exporting-in-studio).

### Running on Studio <a name="runonstudio"/>
Once you have imported you Anypoint Template into Anypoint Studio you need to follow these steps to run it:

+ Locate the properties file `mule.dev.properties`, in src/main/resources
+ Complete all the properties required as per the examples in the section [Properties to be configured](#propertiestobeconfigured)
+ Once that is done, right click on you Anypoint Template project folder 
+ Hover you mouse over `"Run as"`
+ Click on  `"Mule Application"`

### Running on Mule ESB stand alone <a name="runonmuleesbstandalone"/>
Fill in all the properties in one of the property files, for example in [mule.prod.properties](../master/src/main/resources/mule.prod.properties) and run your app with the corresponding environment variable to use it. To follow the example, this will be `mule.env=prod`.

## Running on CloudHub <a name="runoncloudhub"/>
While [creating your application on CloudHub](http://www.mulesoft.org/documentation/display/current/Hello+World+on+CloudHub) (Or you can do it later as a next step), you need to go to `"Manage Application"` > `"Properties"` to set all environment variables detailed in **Properties to be configured**.
Follow other steps defined [here](#runonpremise) and once your app is all set and started, there is no need to do anything else.

### Deploying your Anypoint Template on CloudHub <a name="deployingyouranypointtemplateoncloudhub"/>
Anypoint Studio provides you with really easy way to deploy your Template directly to CloudHub, for the specific steps to do so please check this [link](https://docs.mulesoft.com/mule-fundamentals/v/3.8/deploying-mule-applications#deploy-to-the-anypoint-platform)

### Applying policies on CloudHub <a name="applyingpolicies"/>
When a Mule application is deployed using the Mule API Gateway Runtime, the API Platform allows to dynamically apply different policies that can be used for securizing the application, among many other cases. More information can be found in [Anypoint Platform for APIs](https://docs.mulesoft.com/anypoint-platform-for-apis/applying-runtime-policies)

## Properties to be configured (With examples) <a name="propertiestobeconfigured"/>
In order to use this Mule Anypoint Template you need to configure properties (APIs, Credentials, API Autodiscovery, etc.) either in properties file or in CloudHub as Environment Variables. Detail list with examples:
### Application properties


### Application properties
+ http.port `8081`

+ baseUri `http://localhost:8081/api`

+ ehr.host `ehr-system-api.cloudhub.io`
+ ehr.port `80`
+ ehr.basePath `/api`

