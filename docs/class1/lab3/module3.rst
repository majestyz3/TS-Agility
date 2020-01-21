Lab 3 – Getting Familiar With Postman 
-----------------------------------

In this lab we will setup Postman, an API Development tool that will allow us to structure our API calls and interact with our BIG-IP.
We will use Postman to query our BIG-IP's status and details of the RPM files needed to use and interact with the AS3 RESTful API.

------------------------------------------------ 

**Exercise 1 - Setting Up Postman Environment**


#. Open Postman

------------------------------------------------ 

**Exercise 2 - Check Application Services 3 Extension (AS3) RPM Availability**
  
#. Open Postman 

#. Open the the Postman collection `RPMs`

    .. image:: /docs/_static/as3post.jpg

#. Click the `Get AS3 RPM Package` request 

#. Examine the request. Note that we are sending a 'GET' request with an empty body. Send the GET request by clicking the blue 'Send' button.

    .. image:: /docs/_static/send1.jpg

#. You should see a similar response. 

    .. image:: /docs/_static/as3rpm.jpg

**NOTE:** By sending this GET request to 'https://10.1.1.9/mgmt/shared/appsvcs/info' with the correct credentials, the response shows details of the AS3 API available on this BIG-IP. 

**NOTE:** This AS3 RPM package was pre-installed. For instructions, visit the link here: https://clouddocs.f5.com/products/extensions/f5-appsvcs-extension/latest/userguide/installation.html 


------------------------------------------------ 

**Exercise 3 - Check Telemetry Streaming RPM Availability**
  
#. Open the the Postman collection `RPMs`

#. Click the `Get TS RPM Package` request 

#. Examine the request. Note that we are sending a 'GET' request with an empty body. Send the GET request by clicking the blue 'Send' button. 

    .. image:: /docs/_static/sendts.jpg

#. You should see a similar response. 

    .. image:: /docs/_static/tsrpm.jpg

**NOTE:** By sending this GET request to 'https://10.1.1.4/mgmt/shared/telemetry/info' with the correct credentials, the response shows details of the TS API available on this BIG-IP. 

**NOTE:** This Telemetry Streaming RPM package was pre-installed. For instructions, visit the link here: https://clouddocs.f5.com/products/extensions/f5-appsvcs-extension/latest/userguide/installation.html 

------------------------------------------------ 
