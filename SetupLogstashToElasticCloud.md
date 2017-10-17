**Log in**

Navigate to https://cloud.elastic.co/ and log in or sign up for a free (as in no credit card needed!) trial

![ScreenShot2017-10-16at9.48.16AM](/Users/droscigno/Desktop/Elastic/ScreenShot2017-10-16at9.48.16AM.png)

**Create a cluster**

You can accept the defaults, there is one option in there to ask for high availability across two data centers, this time I just took the default

![ScreenShot2017-10-16at9.48.38AM](/Users/droscigno/Desktop/Elastic/ScreenShot2017-10-16at9.48.38AM.png)

**Don't Panic**

I know it mentions $120 per month, that is if you decide to keep it.  They will not bill you automatically, in fact they will ask you at the end if you want to subscribe and will even store your data for a bit after the 14 days

![ScreenShot2017-10-16at9.49.37AM](/Users/droscigno/Desktop/Elastic/ScreenShot2017-10-16at9.49.37AM.png)

**Store your password in a safe place**

![ScreenShot2017-10-16at9.50.20AM](/Users/droscigno/Desktop/Elastic/ScreenShot2017-10-16at9.50.20AM.png)

**Save this URL**

Take note of your endpoint, this is where you will send data to

![ScreenShot2017-10-16at9.50.59AM](/Users/droscigno/Desktop/Elastic/ScreenShot2017-10-16at9.50.59AM.png)

**Save your Kibana URL**

The Kibana URL is under Configuration

![ScreenShot2017-10-16at9.55.13AM](/Users/droscigno/Desktop/Elastic/ScreenShot2017-10-16at9.55.13AM.png)

**Connect to Kibana**

Log in as user **elastic** with the password you wrote down above

![ScreenShot2017-10-16at9.59.59AM](/Users/droscigno/Desktop/Elastic/ScreenShot2017-10-16at9.59.59AM.png)

**Ignore the index warning**

When you send data in you will be able to choose a default index, don't worry about this for now.  Click on Management in the left navigation, and then on Management in the breadcrumbs on the right

![ScreenShot2017-10-16at10.00.25AM](/Users/droscigno/Desktop/Elastic/ScreenShot2017-10-16at10.00.25AM.png)

**Closeup of the right side breadcrumb**

![ScreenShot2017-10-16at10.01.35AM](/Users/droscigno/Desktop/Elastic/ScreenShot2017-10-16at10.01.35AM.png)

**See the docs on authentication**

There are docs for setting up authentication (try not to make every account a superuser!) at http://bit.ly/2zuiaRz .  The Logstash account does not need very many privileges, but does need to be able to create indexes and write to them.

![ScreenShot2017-10-16at10.15.21AM](/Users/droscigno/Desktop/Elastic/ScreenShot2017-10-16at10.15.21AM.png)

**Create a Role with X-Pack**

Back in Kibana, under Management, Management click on Roles

![ScreenShot2017-10-16at10.19.29AM](/Users/droscigno/Desktop/Elastic/ScreenShot2017-10-16at10.19.29AM.png)

**Create a logstash_writer role**

In the **Name** and **Indices** fields you type in the role name and either a specific index name, or a wildcard.  I use this role for multiple Logstash streams, so I use a wildcard (see below).  Check the box for the **manage_index_templates** Cluster Privilege, and then click in the Index Privileges box and choose the privileges below (which match the docs we looked at above)

![ScreenShot2017-10-16at10.19.09AM](/Users/droscigno/Desktop/Elastic/ScreenShot2017-10-16at10.19.09AM.png)



**Add a user**

Add a user with the role created above.  I use the suffix **_agent** to indicate that a process running on an external machine is using this account.  Store the username and password with the rest of your notes.

![ScreenShot2017-10-16at10.21.18AM](/Users/droscigno/Desktop/Elastic/ScreenShot2017-10-16at10.21.18AM.png)

**Get some data**

I like to use known sample data that is pretty common.  Generally I use either syslog data or Apache HTTP Server logs.  There is a sample data set and tutorial at http://bit.ly/2ijecXK .  In fact, I recommend going through the tutorial later to learn about using Kibana templates and geoip (it is a great tutorial).  For now, just grab the Appache HTTP Server logs and Logstash config files.

![ScreenShot2017-10-16at10.27.11AM](/Users/droscigno/Desktop/Elastic/ScreenShot2017-10-16at10.27.11AM.png)

b

![ScreenShot2017-10-16at10.29.05AM](/Users/droscigno/Desktop/Elastic/ScreenShot2017-10-16at10.29.05AM.png)

c

![ScreenShot2017-10-16at10.30.25AM](/Users/droscigno/Desktop/Elastic/ScreenShot2017-10-16at10.30.25AM.png)

b

![ScreenShot2017-10-16at10.29.36AM](/Users/droscigno/Desktop/Elastic/ScreenShot2017-10-16at10.31.38AM.png)

b

![ScreenShot2017-10-16at10.39.22AM](/Users/droscigno/Desktop/Elastic/ScreenShot2017-10-16at10.39.22AM.png)

b

![ScreenShot2017-10-16at10.39.44AM](/Users/droscigno/Desktop/Elastic/ScreenShot2017-10-16at10.39.44AM.png)

b

![ScreenShot2017-10-16at11.19.39AM](/Users/droscigno/Desktop/Elastic/ScreenShot2017-10-16at11.19.39AM.png)

b

![ScreenShot2017-10-16at11.19.11AM](/Users/droscigno/Desktop/Elastic/ScreenShot2017-10-16at11.19.11AM.png)

b

![ScreenShot2017-10-16at11.20.16AM](/Users/droscigno/Desktop/Elastic/ScreenShot2017-10-16at11.20.16AM.png)

b

![ScreenShot2017-10-16at11.25.31AM](/Users/droscigno/Desktop/Elastic/ScreenShot2017-10-16at11.25.31AM.png)

b

![ScreenShot2017-10-16at11.27.01AM](/Users/droscigno/Desktop/Elastic/ScreenShot2017-10-16at11.27.01AM.png)

b

![ScreenShot2017-10-16at11.37.27AM](/Users/droscigno/Desktop/Elastic/ScreenShot2017-10-16at11.37.27AM.png)

b

![ScreenShot2017-10-16at11.37.43AM](/Users/droscigno/Desktop/Elastic/ScreenShot2017-10-16at11.37.43AM.png)

b

![ScreenShot2017-10-16at11.37.53AM](/Users/droscigno/Desktop/Elastic/ScreenShot2017-10-16at11.37.53AM.png)

a

a![ScreenShot2017-10-16at11.38.34AM](/Users/droscigno/Desktop/Elastic/ScreenShot2017-10-16at11.38.34AM.png)

![ScreenShot2017-10-16at11.48.25AM](/Users/droscigno/Desktop/Elastic/ScreenShot2017-10-16at11.48.25AM.png)

a

![ScreenShot2017-10-16at11.48.39AM](/Users/droscigno/Desktop/Elastic/ScreenShot2017-10-16at11.48.39AM.png)

a

![ScreenShot2017-10-16at11.48.52AM](/Users/droscigno/Desktop/Elastic/ScreenShot2017-10-16at11.48.52AM.png)

a

![ScreenShot2017-10-16at11.49.42AM](/Users/droscigno/Desktop/Elastic/ScreenShot2017-10-16at11.49.42AM.png)



a

![ScreenShot2017-10-16at11.50.55AM](/Users/droscigno/Desktop/Elastic/ScreenShot2017-10-16at11.50.55AM.png)

a

![ScreenShot2017-10-16at11.51.08AM](https://user-images.githubusercontent.com/25182304/31694616-36654442-b373-11e7-9e8f-c9be22a6825e.png)
<img width="869" alt="screenshot2017-10-16at11 51 08am" src="https://user-images.githubusercontent.com/25182304/31694616-36654442-b373-11e7-9e8f-c9be22a6825e.png">

a

<img width="1073" alt="screenshot2017-10-16at9 48 16am" src="https://user-images.githubusercontent.com/25182304/31694577-33ad18f6-b373-11e7-80ef-1f6e61b37c2d.png">
<img width="1028" alt="screenshot2017-10-16at9 48 38am" src="https://user-images.githubusercontent.com/25182304/31694578-33bd5946-b373-11e7-8fb4-34f33657a979.png">
<img width="299" alt="screenshot2017-10-16at9 49 37am" src="https://user-images.githubusercontent.com/25182304/31694579-33cee788-b373-11e7-89f8-05df1d7e1b8e.png">
<img width="945" alt="screenshot2017-10-16at9 50 20am" src="https://user-images.githubusercontent.com/25182304/31694580-33d9f3d0-b373-11e7-9e4a-213e5747e944.png">
<img width="1215" alt="screenshot2017-10-16at9 50 59am" src="https://user-images.githubusercontent.com/25182304/31694581-33e88ac6-b373-11e7-8704-46127606fc06.png">
<img width="849" alt="screenshot2017-10-16at9 55 13am" src="https://user-images.githubusercontent.com/25182304/31694582-33fabcd2-b373-11e7-88f1-af4724891d7f.png">
<img width="643" alt="screenshot2017-10-16at9 59 59am" src="https://user-images.githubusercontent.com/25182304/31694583-340a21ea-b373-11e7-947c-10cbea71790f.png">
<img width="915" alt="screenshot2017-10-16at10 00 25am" src="https://user-images.githubusercontent.com/25182304/31694584-3418e392-b373-11e7-95c5-8146ddceac13.png">
<img width="137" alt="screenshot2017-10-16at10 01 35am" src="https://user-images.githubusercontent.com/25182304/31694585-3428af66-b373-11e7-9dbf-1016fab56941.png">
<img width="639" alt="screenshot2017-10-16at10 15 21am" src="https://user-images.githubusercontent.com/25182304/31694586-34387edc-b373-11e7-8036-91d029631b1c.png">
<img width="732" alt="screenshot2017-10-16at10 19 09am" src="https://user-images.githubusercontent.com/25182304/31694587-344b0c14-b373-11e7-816c-6b6b7a92df20.png">
<img width="278" alt="screenshot2017-10-16at10 19 29am" src="https://user-images.githubusercontent.com/25182304/31694588-345c8c1e-b373-11e7-93ac-b0f0580a5e0e.png">
<img width="391" alt="screenshot2017-10-16at10 21 18am" src="https://user-images.githubusercontent.com/25182304/31694589-346d6d0e-b373-11e7-8c87-4004669ad2c8.png">
<img width="484" alt="screenshot2017-10-16at10 21 45am" src="https://user-images.githubusercontent.com/25182304/31694590-347d616e-b373-11e7-94c6-578dfaa9d4d8.png">
<img width="1142" alt="screenshot2017-10-16at10 27 11am" src="https://user-images.githubusercontent.com/25182304/31694591-348b554e-b373-11e7-92c8-6a4cfa4b15c4.png">
<img width="582" alt="screenshot2017-10-16at10 29 05am" src="https://user-images.githubusercontent.com/25182304/31694592-349a2f74-b373-11e7-8271-89c9d60cb753.png">
<img width="980" alt="screenshot2017-10-16at10 29 36am" src="https://user-images.githubusercontent.com/25182304/31694594-34ab610e-b373-11e7-92ef-bddda5982afd.png">
<img width="474" alt="screenshot2017-10-16at10 30 25am" src="https://user-images.githubusercontent.com/25182304/31694595-34bd3ae6-b373-11e7-9f4e-b7701d64b484.png">
<img width="956" alt="screenshot2017-10-16at10 31 38am" src="https://user-images.githubusercontent.com/25182304/31694596-34ccfed6-b373-11e7-8154-124c0b634258.png">
<img width="1228" alt="screenshot2017-10-16at10 39 22am" src="https://user-images.githubusercontent.com/25182304/31694597-34de3f66-b373-11e7-9c14-a4de7c29522a.png">
<img width="1272" alt="screenshot2017-10-16at10 39 44am" src="https://user-images.githubusercontent.com/25182304/31694598-34ee1e04-b373-11e7-868e-5987820fd391.png">
<img width="350" alt="screenshot2017-10-16at10 54 06am" src="https://user-images.githubusercontent.com/25182304/31694599-34ff0a70-b373-11e7-868a-8b5e734add38.png">
<img width="862" alt="screenshot2017-10-16at11 18 38am" src="https://user-images.githubusercontent.com/25182304/31694600-352339f4-b373-11e7-8947-025a88682968.png">
<img width="863" alt="screenshot2017-10-16at11 19 11am" src="https://user-images.githubusercontent.com/25182304/31694601-3538f3b6-b373-11e7-945d-5f5d1d71f331.png">
<img width="686" alt="screenshot2017-10-16at11 19 39am" src="https://user-images.githubusercontent.com/25182304/31694602-354a1466-b373-11e7-88c7-3d2f98018f3a.png">
<img width="691" alt="screenshot2017-10-16at11 20 16am" src="https://user-images.githubusercontent.com/25182304/31694603-3560d6b0-b373-11e7-84c6-64f58d529551.png">
<img width="609" alt="screenshot2017-10-16at11 25 31am" src="https://user-images.githubusercontent.com/25182304/31694604-356e518c-b373-11e7-80e0-23c3a61d6637.png">
<img width="1030" alt="screenshot2017-10-16at11 27 01am" src="https://user-images.githubusercontent.com/25182304/31694605-357a7bc4-b373-11e7-923c-07cfcfae9c7f.png">
<img width="356" alt="screenshot2017-10-16at11 37 27am" src="https://user-images.githubusercontent.com/25182304/31694606-3586805e-b373-11e7-916c-5dc3556adc72.png">
<img width="172" alt="screenshot2017-10-16at11 37 43am" src="https://user-images.githubusercontent.com/25182304/31694607-3598b9b8-b373-11e7-915e-d188b7d25211.png">
<img width="422" alt="screenshot2017-10-16at11 37 53am" src="https://user-images.githubusercontent.com/25182304/31694608-35a8bc1e-b373-11e7-8f31-83dcd90c33dd.png">
<img width="1316" alt="screenshot2017-10-16at11 38 34am" src="https://user-images.githubusercontent.com/25182304/31694609-35c733f6-b373-11e7-902d-d9271269770c.png">
<img width="1015" alt="screenshot2017-10-16at11 48 25am" src="https://user-images.githubusercontent.com/25182304/31694610-35e2cd64-b373-11e7-92cc-e17ce945af74.png">
<img width="340" alt="screenshot2017-10-16at11 48 39am" src="https://user-images.githubusercontent.com/25182304/31694611-3600c972-b373-11e7-94f7-ca77244cd51d.png">
<img width="1003" alt="screenshot2017-10-16at11 48 52am" src="https://user-images.githubusercontent.com/25182304/31694612-3610b846-b373-11e7-99bc-ce720483bc62.png">
<img width="548" alt="screenshot2017-10-16at11 49 10am" src="https://user-images.githubusercontent.com/25182304/31694613-3627e3d6-b373-11e7-829f-b8754dc99125.png">
<img width="593" alt="screenshot2017-10-16at11 49 42am" src="https://user-images.githubusercontent.com/25182304/31694614-36387f5c-b373-11e7-8ccc-ea4dbb2a382f.png">
<img width="842" alt="screenshot2017-10-16at11 50 55am" src="https://user-images.githubusercontent.com/25182304/31694615-364a9c8c-b373-11e7-88d3-7fdd3ee05fc4.png">

