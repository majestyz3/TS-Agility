Lab 6 – Configuring Telemetry Streaming With Third-Party Log Management & Analysis Tools (Part 2)
------------------------------------------------------------  
  
Task – Login to AWS Cloudwatch 
~~~~~~~~~~~~~~~~~~~~~~~~~~~ 
  
#. Navigate to UDF class view 

#. Click on Cloud Accounts and copy the Console Username and Console Password (keep this tab open for the next section). Click the Console URL. Paste in the Console Username and Console Password. 
    .. image:: ./cw1.jpg    

#. Once logged in, click the Services dropdown, search and select Cloudwatch 
    .. image:: ./cw2.jpg

#. On the left pane, under Logs select Log groups. Under the Actions dropdown select Create log group. 
    .. image:: ./cw3.jpg

#. Name the log group (ie my_log_group) and select the Create log group blue button. 

#. Click on the log group you just created. Select Create Log Stream and name your log stream (ie my_log_stream) 
    .. image:: ./cw4.jpg
 
 
 
Task – Edit the AWS Cloudwatch TS Declaration 
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 
  
#. Navigate to UDF class view 

#. Click on Jumphost and login with the credentials from previous sections. 

#. Launch Postman 

#. Open the Collection titled Telemetry with AWS Cloudwatch. Open the AWS Cloudwatch request. Open the Body tab of the request 
    .. image:: ./cw5.jpg

#. We will need to edit the My_Consumer. Go back to the Cloud Accounts tab you left open. Copy and paste the region. Edit logGroup to match your log group. Edit logStream to match your log stream. Edit username to match the API Key. Edit the cipherText to match the API Secret. 
    .. image:: ./cw1.jpg
    
    .. image:: ./cw7.jpg
 
#. Click the blue Send to POST the Telemetry Streaming declaration. Ensure a 200 OK response. 
 
 
 
 
Task – View the logs in AWS Cloudwatch 
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 
#. Navigate back to the UDF class view 
#. Log back into AWS Cloudwatch 
#. Navigate to the log stream you created. 
#. Notice that logs have been populated in the log stream. 
    .. image:: ./cw6.jpg
#. Expand the log. Scroll down and you will find data on the virtual servers, pools, and various other objects.  
#. On the left pane, select the subcategory Insights 
    .. image:: ./cw8.jpg
#. Click into the Select log group(s) search bar and select your group. Then click the Run query button. 
    .. image:: ./cw9.jpg
#. Explore AWS Cloudwatch 
 
 