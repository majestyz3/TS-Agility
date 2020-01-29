Lab 5 – Configuring Telemetry Streaming With Third-Party Log Management & Analysis Tools
-----------------------------------

In this lab we will configure our Telemetry Streaming JSON declaration to establish a connection between our consumer and our BIG-IP. 

------------------------------------------------ 

**Exercise 1 - Configure Kibana as the Telemetry Consumer**

#. Open Postman.

#. Open the Postman collection `Setup Telemetry Streaming`. 

#. Click the `ELK Consumer` request.

#. Click on the Body tab. 

    .. image:: ./elkbody.jpg

**HINT** Here is what is important from this declaration: 

   * The Listener collects event logs from all BIG-IP sources, including LTM, ASM, AFM, APM, and AVR. You can configure all of these by POSTing a single AS3 declaration or you can use TMSH or the GUI to configure individual modules.  

   * The Consumer class is the third party consumer we wish to send our captured data to. 

#. Send the POST request by clicking the blue 'Send' button. Ensure a 'Status: 200 OK' response.  

    .. image:: ./elkresponse.jpg

**NOTE:** By sending this GET request to ``https://10.1.1.9/mgmt/shared/telemetry/declare`` with the correct credentials and current body we've established a connection between our consumer and our BIG-IP. 

**NOTE:** To learn more about AS3, visit https://clouddocs.f5.com/products/extensions/f5-telemetry-streaming/latest/ 

------------------------------------------------ 

**Exercise 2 - Generate Traffic on OpenCart**


In this exercise, we will launch a traffic generation script targeting the newly created app service. 

#. From the UDF page, under the 'Systems' column, find the host named “Traffic Gen” and select SSH from the Access drop-down 

    .. image:: ./trafgen.jpg

#. Accept the SSH warning and type su for sudo user access, the password is “toor”  

#. Run the traffic script by entering **./baseline_menu.sh** and hit enter 

#. From the menu, choose 2) Alternate and let it run  


------------------------------------------------ 

**Exercise 3 - Analyze Telemetry via Kibana**



------------------------------------------------ 

**Exercise 4 - Create a Simple Kibana Visualization**



------------------------------------------------ 
