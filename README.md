# Template Healthcare EHR Appointments Process API

Appointment scheduling is one of the most popular, yet most complex use cases in healthcare. Appointment scheduling requires an orchestration logic that retrieves and updates multiple resources to schedule a new appointment. This template provides an API implementation best practice to abstract that complexity with a light-weight RESTful interface that can be reused in other integrations projects such as building a mobile app for appointment scheduling. 

![](https://www.lucidchart.com/publicSegments/view/6c0eab9d-b684-43bd-96c5-61b323fd6399/image.png)

## Accelerator for Healthcare
This API implementation is one of many components included in [Accelerator for Healthcare](/exchange/68ef9520-24e9-4cf2-b2f5-620025690913/catalyst-accelerator-for-healthcare/). This API provides organizations with connectivity assets that accelerate project delivery in healthcare, including pre-built API designs and implementations that support core healthcare business processes.

# License Agreement
Using this template is subject to the conditions of this <a href="https://s3.amazonaws.com/templates-examples/AnypointTemplateLicense.pdf">MuleSoft License Agreement</a>. Review the terms of the license before downloading and using this template. In short, you are allowed to use the template for free with Mule Enterprise Edition, CloudHub, or as a trial in Anypoint Studio.

# Use Case
As a Healthcare Clinic Portal user I want a service to manage Appointment data from in EHR system.

This template should serve as a foundation for implementing an API that manages Appointments in the EHR FHIR System API and it is provided as part of the Healthcare Templates Solution. The API is defined using 
[RAML 1.0](http://raml.org) and this implementation uses [APIkit](https://docs.mulesoft.com/anypoint-platform-for-apis/apikit-basic-anatomy#basic-anatomy). 
EHR Appointments Process API triggers the underlying microservices defined in EHR FHIR System API in JSON 
(FHIR specification [version 3.0.1 STU3](https://www.hl7.org/FHIR/index.html)).

EHR Appointments Process API is part of the Healthcare Templates Solution and it is interconnected with EHR FHIR System API and Web Portal Experience API.

# Considerations
To run this template, there are certain preconditions that must be considered. Failing to do so could lead to unexpected behavior of the template. 

- **Compatibiliy:** Use Anypoint Studio v7.1.0+ and Mule Runtime 4.1.1+ to run this template.
- **API Security:** Deploy to CloudHub and manage using the API Platform Manager.
- **Expose External Endpoints with HTTP:** Trigger with the Web Portal Experience API using HTTP.
- **Expose Internal Endpoints with RAML and HTTP:** Interconnect internally with the EHR FHIR System API, which is deployed on a CloudHub.

# Run it!
Simple steps to get Healthcare EHR Appointments Process API running.
See below.

## Run On-Premises
In this section we detail the way you should run your Anypoint Template on your computer.

### Where to Download Anypoint Studio and the Mule Runtime

If you are new to Mule, download this software:

- [Download Anypoint Studio](https://www.mulesoft.com/platform/studio)
- [Download Mule runtime](https://www.mulesoft.com/lp/dl/mule-esb-enterprise)

### Import Template in Studio
In Studio, click the Exchange X icon in the upper left of the taskbar, log in with your
Anypoint Platform credentials, search for the template, and click **Open**.

### Run in Studio
After opening your template in Anypoint Studio, follow these steps to run it:

1. Locate the properties file `mule.dev.properties`, in src/main/resources.
2. Complete all the properties required as per the examples in the section "Properties to Configure".
3. Right click your template project folder.
4. Hover your mouse over `Run as`.
5. Click `Mule Application (configure)`.
6. Inside the dialog, select Environment and set the variable `mule.env` to the value `dev`.
7. Click `Run`.

### Run in Mule Runtime
Fill in all the properties in one of the property files, for example in mule.prod.properties) and run your app with the corresponding environment variable to use it. To follow the example, use `mule.env=prod`.

## Run in CloudHub
While creating your application on CloudHub, you need to go to Manage Application > Properties to set all environment variables detailed in "Properties to Configure".

### Deploy in CloudHub

In Studio, right click your project name in Package Explorer and select Anypoint Platform > Deploy on CloudHub.

### Applying Policies in CloudHub

When a Mule application is deployed using the Mule Runtime, the API Platform allows you to dynamically apply different policies that can be used for securing the application, among many other cases. More information can be found in [Policies for Mule 4](https://docs.mulesoft.com/api-manager/2.x/policies-mule4).

## Properties to Configure
To use this template you need to configure properties (APIs, Credentials, API Autodiscovery, etc.) either in properties file or in CloudHub as Environment Variables. Detail list with examples:

### Application Properties

- http.port `8081`
- ehr.host `ehr-system-api.cloudhub.io`
- ehr.port `80`
- ehr.basePath `/api`

