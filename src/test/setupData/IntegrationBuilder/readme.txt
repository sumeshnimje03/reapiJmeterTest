-- Set-up reqiered to run Integration Builder via xm-api endpoints on new environment through Jmeter--


1. Import Engine 'CloudToCloud' to your company

2. Enable CloudToCloud

3. Enable C-C-Form : Form and Web Service

4. Get the Integration Builder UUID(Engine > Integration Builder > Inbound Integrations > TestIntegration Plan > Integration URL) and put this UUID to integration_uuid in jmeter.property

5. Get the Form UUID(Engine > Form > Access Web Service URL) and put this UUID to application_uuid in jmeter.property

6. Get the client secret ID

7. Load 'IntegrationBuilder-xmapi.jmx' on Jmeter

8. Click play button to run 'IntegrationBuilder-xmapi.jmx'



Note:
1.  Client secret Id is 7d2854b1-3459-4223-9f1b-c2b8dce86658