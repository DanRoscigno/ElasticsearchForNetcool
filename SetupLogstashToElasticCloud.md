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

![ScreenShot2017-10-16at11.51.08AM](/Users/droscigno/Desktop/Elastic/ScreenShot2017-10-16at11.51.08AM.png)

a

