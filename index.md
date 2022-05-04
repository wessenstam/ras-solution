# Remote Access Solutions Lab

This lab is emulating a scenario in which an organisation (thylab.local) has wants to dismantle their VPN solution for their third party that manages an important router in their infrastructure. The organisation has found out that there is a solution based on Delinea where the connection is being made over https and no VPN software or server/appliance has to be deployed or managed.

Below is a diagram of the lab infrastructure and the entire connection including you the attendees. The Router VM is not available in the Skytap environment for you to control, but you will be able to access it after you have ran all configuration steps from outside the lab environment. Your real physical laptop.

![Lab Infrastructure](images/lab-A-001.png)

This lab will highlight the following topics:
1. Log into a cloud tenant of Delinea solution (platform 1.0)
2. Deploying the Cloud Connector so the cloud tenant can communicate with the organisation's infrastructure 
3. Integration of the existing Secret Server installation with Platform 1.0
4. Configure Platform 1.0
5. Test the configuration


# Log into Platform 1.0

During the duration of the lab you have been granted access to use a cloud tenant. Your cloud tenant URL should have been sent to you prior to this workshop. if you don't have received your credentials, please speak to your instructor to get your tenant URL. The URL will kook something like ``https://<tenant>.my.centrify.net/``
The username to use will be ``admin@lab.<tenant>``. The password will be set default to **Delinea/4u**, unless you have received the invitation email and already logged into the tenant and change the password.

The invitation email, a screenshot below as example, should be sent to you earlier. 

![Invitation email](images/lab-A-002.png)

By clicking on the Login Now button, you will be redirected to the URl and automatically logged in. After you're logged in, you have to set a new password. This is yours to choose. Just remember it as it is your environment.

![Initial login Platform 1.0](images/lab-A-003.png)

---

**Note**

We can help you if you have forgotten your password, BUT to be able to help you, please leave the **mspadmin@\<tenant\>.lab** in the environment. **Do not delete it**.

---

1. Click on the **Cancel** button on the *Welcome to Centrify Privileged Access Service* screen and close the two popup screens that are shown in the right bottom corner.

   ![Configuration Platform 1.0](images/lab-A-004.png)
   
3. As you are now able to log in, you are ready to start the next step in the lab; deploying the cloud connector into the lab environment.

# Deploy the Cloud Connector

For this step to work, you need to connect to the virtualised Skytap environment which is running in a data centre, in London, Singapore, or in the USA.
After you have received the assignment of your lab environment, login to the provided URL. An extra password might be needed. Your training can provide you with that password so you are abel to see the lan environment as shown at the beginning of the lab.

![Configuration Platform 1.0](images/lab-A-005.png)

If the environment is stopped, please start it by using the "play" button in the top right corner to start the environment 

![Start Skytap lab environment](images/lab-A-006.png)

and wait till both VMs are started.  

![Start Skytap lab environment](images/lab-A-007.png)

Now that the lab environment is in a running state, follow the below steps to get the Cloud Connector deployed.

1. Click on the **SSPM** desktop to open the console of the SSPM server
2. Log into the server user the following credentials:

   - **Username:** THYLAB\adm-training
   - **Password:** *Provided by the trainer*

3. If Chrome did open up, close it.

# Integration existing Secret Server

# Configure Platform 1.0

# Test configuration

