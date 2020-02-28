Lab 5 – Configuring Telemetry Streaming With Third-Party Log Management & Analysis Tools
-----------------------------------

In this lab we will configure our Telemetry Streaming JSON declaration to establish a connection between our Elastic Stack consumer and our BIG-IP. 

------------------------------------------------ 

**Exercise 1 - Configure Kibana as the Telemetry Consumer**

#. Open the Postman collection `Telemetry with ElasticSearch and Kibana`. 

#. Click the `ELK Consumer` request.

#. Click on the Body tab. 

    .. image:: ./elkbody.jpg

#. Send the POST request by clicking the blue 'Send' button. Ensure a 'Status: 200 OK' response.  

    .. image:: ./elkresponse.jpg

**HINT** Here is what is important from this declaration: 

   * The Listener collects event logs from several BIG-IP sources including LTM, ASM, AFM, APM, and AVR. You can configure all of these by posting a single declaration. 

   * The Consumer class is the third party consumer we wish to send our telemetry data to. 

**NOTE:** By sending this GET request to ``https://10.1.1.9/mgmt/shared/telemetry/declare`` with the correct credentials and current body we've established a connection between our consumer and our BIG-IP. 

.. TODO:: Now we will build the Kibana database and mapping. 

#. Click the `Elastic Create Database` request. Send the PUT request by clicking the blue 'Send' button. A 400 `response_already_exists_exception` response is ok.

#. Click the `Elastic create mapping` request. Send the PUT request by clicking the blue 'Send' button.


------------------------------------------------ 

**Exercise 2 - Generate Traffic on OpenCart**
  
#. From the UDF page, find the host named Traffic Gen and select SSH from the Access drop-down 

#. Accept the SSH warning and you should be authenticated 

#. Run ./baseline_menu.sh

#. You should have root access but if the script fails, type "su" and the password "toor" and retry

#. From the menu, choose 2) Alternate and let it run while you continue with the labs 

------------------------------------------------ 


**Exercise 3 - Analyze Telemetry via Kibana**

#. Open a new tab in Chrome and click the Kibana bookmark.

#. Select the Discover tab on the top left.

#. Ensure that `f5` is selected in the dropdown and that a reasonable time range is selected in the top right (ie 15 minutes in the screenshot below).

    .. image:: ./f5selected.jpg

#. Now you should see some logs coming in. 

------------------------------------------------ 

**Exercise 4 - Create a Simple Kibana Visualization**

#. In Discover type ``data.http_code \: 40*``. This will show you all HTTP resonses starting with 40.

    .. image:: ./kib_1.png

#. Click the Visualize tab on the left and click Create a Visualization

#. You can explore various types of graphs. For this exercise we will select the Line graph

#. Under Select Index select f5\*

#. On the left, under Buckets select X-Axis. Select Date Histogram from the Aggregation dropdown, data.event_timestamp from the Field dropdown, and Auto from the Interval dropdown.

    .. image:: ./kib_2.png

#. Now select the Apply Changes play button next to Panel Settings. Press the blue Refresh button on the top right. View your visualization. These options are circled in the screenshot below.

    .. image:: ./kib_3.png

------------------------------------------------ 
