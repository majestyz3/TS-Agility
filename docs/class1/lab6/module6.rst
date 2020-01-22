Lab 6 – Configuring Telemetry Streaming With Third-Party Log Management & Analysis Tools (Part 2)
-----------------------------------

In this lab we will configure our Telemetry Streaming JSON declaration to establish a connection between our consumer, AWS CloudWatch, and our BIG-IP. 

------------------------------------------------ 

**Exercise 1 - Configure AWS CloudWatch as the Telemetry Consumer**

#. Open Postman. 

#. Open the Postman collection `Setup Telemetry Streaming`. 

#. Click the `Declare 2 Consumers` request. 

#. Click on the Body tab - notice that this is similar to the previous request with an appended class for AWS CloudWatch configuration details. 

    .. image:: ./awscw.jpg

**HINT:** Here is what is important from this declaration: 

   * MY_CW_Consumer sets up a Cloudwatch consumer

#. Send the POST request by clicking the blue 'Send' button. Ensure a 'Status: 200 OK' response.  

    .. image:: ./awscwresponse.jpg

**NOTE:** By sending this GET request to ``https://10.1.1.9/mgmt/shared/telemetry/declare`` with the correct credentials and current body we've established a connection between our consumer and our BIG-IP. 

**NOTE:** To learn more about AS3, visit https://clouddocs.f5.com/products/extensions/f5-telemetry-streaming/latest/

------------------------------------------------ 
 

**Exercise 2 - Generate Traffic on OpenCart**



------------------------------------------------ 

**Exercise 3 - Analyze Telemetry via AWS CloudWatch**



------------------------------------------------ 

**Exercise 4 - Create a AWS CloudWatch Dashboard**



------------------------------------------------ 
