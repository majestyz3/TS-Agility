Lab 3 – Configuring and Deploying A Simple HTTP Application via Application Services v3 (AS3)
-----------------------------------

In this lab we will setup Postman, an API Development tool that will allow us to structure our API calls and interact with our BIG-IP.
We will use Postman to query our BIG-IP's status and details of the RPM files needed to use and interact with the AS3 RESTful API.

------------------------------------------------ 

**Exercise 1 - Explore BIG-IP**


#. Open the web browser and navigate to the BIG-IP GUI (https://10.1.1.4) or by clicking the bookmark. 

    .. image:: /docs/_static/bigipbm.jpg

#. Login to the BIG-IP with the following credentials:

   +---------------+------------------------------------+
   | Username      |        admin                       |
   +---------------+------------------------------------+
   | Password      |    AgilityIsFun123!                |
   +---------------+------------------------------------+


#. Once you are logged in, navigate to 'Local Traffic' -> 'Virtual Servers' -> 'Virtual Servers List'. 

    .. image:: /docs/_static/vslist.jpg

#. Note that you are in the 'Common' partition (top-right) and the BIG-IP has no Virtual Servers, Pools or Pool Members configured. 

    .. image:: /docs/_static/vslistdisplay.jpg

------------------------------------------------ 

**Exercise 2 - Configure and Deploy the HTTP Application via AS3 With The Appropriate Telemetry Streaming Configuration**

The focus for this exercise is to deploy an application with the appropriate Telemetry Streaming configuration objects.

#. Open Postman 

#. Open the the Postman collection `AS3` 

#. Click the `Create Application via AS3` request 

#. Click on the body tab and examine the request body. 

    .. image:: /docs/_static/jsonbody.jpg

    **HINT:** Here is what is important in this declaration: 

   * The telemetry_local_rule allows traffic through port 6514  

   * The telemetry_traffic_log_profile builds a logging profile which specifies the log parameters 

    .. image:: /docs/_static/as3snippet.jpg

#. Send the POST request by clicking the blue Send button.

#. Ensure you recieved a 'Status: 200 OK' response. 

    .. image:: /docs/_static/200response.jpg

**NOTE:** By sending this GET request to ``https://10.1.1.9/mgmt/shared/appsvcs/declare`` with the correct credentials and current body we've built an application declaratively via AS3. 

**NOTE:** To learn more about AS3, visit https://clouddocs.f5.com/products/extensions/f5-appsvcs-extension/latest/ 

  

------------------------------------------------ 

**Exercise 3 - Verify Successful Deployment via BIG-IP GUI**


#. Open Chrome 

#. Click the BIG-IP bookmark or navigate to 'https://10.1.1.4'

#. Login to the BIG-IP with the following credentials:

   +---------------+------------------------------------+
   | Username      |        admin                       |
   +---------------+------------------------------------+
   | Password      |    AgilityIsFun123!                |
   +---------------+------------------------------------+


#. Once you are logged in, navigate to 'Local Traffic' -> 'Virtual Servers' -> 'Virtual Servers List'. 

    .. image:: /docs/_static/vslist.jpg

#. Notice that you are currently in the `Common` partition and that there is now an application built named `opencart_vs`. 

    .. image:: /docs/_static/ocbigip.jpg


------------------------------------------------ 

**Exercise 4 - Verify Web Application**


#. In your web browser, click on the 'OpenCart' bookmark. 

    .. image:: /docs/_static/ocbookmark.jpg

#. Verify the application is working by clicking a few tabs and viewng products. 

    .. image:: /docs/_static/opencart.jpg

------------------------------------------------ 


