Lab 3 – Configuring and Deploying A Simple HTTP Application via Application Services v3 (AS3)
-----------------------------------

In this lab we will setup Postman, an API Development tool that will allow us to structure our API calls and interact with our BIG-IP.
We will use Postman to query our BIG-IP's status and details of the RPM files needed to use and interact with the AS3 RESTful API.

------------------------------------------------ 

**Exercise 1 - Explore BIG-IP**


#. Open the web browser and navigate to the BIG-IP GUI (https://10.1.1.4) or by clicking the bookmark. 

    .. image:: /docs/_static/.jpg

#. Login to the BIG-IP with the following credentials:

   +---------------+------------------------------------+
   | Username      |        admin                       |
   +---------------+------------------------------------+
   | Password      |    AgilityIsFun123!                |
   +---------------+------------------------------------+


#. Once you are logged in, navigate to 'Local Traffic' -> 'Virtual Servers' -> 'Virtual Servers List'. 

    .. image:: /docs/_static/.jpg

#. Note that you are in the 'Common' partition (top-right) and the BIG-IP has no Virtual Servers, Pools or Pool Members configured. 

    .. image:: /docs/_static/.jpg

------------------------------------------------ 

**Exercise 2 - Configure and Deploy the HTTP Application via AS3 With The Appropriate Telemetry Streaming Configuration**

The focus for this exercise is to deploy an application with the appropriate Telemetry Streaming configuration objects.

#. Open Postman 

#. Open the the Postman collection `AS3` 

#. Click the `Create Application via AS3` request 

#. Click on the body tab and examine the request body. 

.. HINT:: Here is what is important from this declaration: 

  

   #. The telemetry_local_rule allows traffic through port 6514  

   #. The telemetry_traffic_log_profile builds a logging profile which specifies the log parameters 

#. Send the POST request by clicking the blue Send button 

    |as3_post| 

  

.. NOTE:: By sending this GET request to ``https://10.1.1.9/mgmt/shared/appsvcs/declare`` with the correct credentials and current body we've built an application declaratively via AS3. 

.. NOTE:: To learn more about AS3, visit https://clouddocs.f5.com/products/extensions/f5-appsvcs-extension/latest/ 

  

  

 @@




~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 



Task – Verify Build 

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 

  

#. Open Chrome 

#. Click the BIG-IP bookmark 

#. Login with credentials - admin / AgilityIsFun123! 

#. Click Local Traffic, Virtual Servers, Virtual Server List. 

#. Notice that you are currently in the ``Common`` partition and that there is now an application buiilt named ``opencart_vs`` and ``telemetry_local``. 

  

  

Task – Verify App 

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 

  

#. Open Chrome 

#. Click the opencart bookmark 

#. Verify the application is working by clicking a few tabs and viewng products 

 