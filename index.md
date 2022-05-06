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

During the duration of the lab you have been granted access to use a cloud tenant. Your cloud tenant URL should have been sent to you prior to this workshop. if you don't have received your credentials, please speak to your instructor to get your tenant URL. The URL will look something like ``https://<tenant>.my.centrify.net/``
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

For this step to work, you need to connect to the virtualised Skytap environment which is running in a Data Centre in London, Singapore, or in the USA.

## Checking the Skytap instance

After you have received the assignment of your lab environment, login to the provided URL. An extra password might be needed. Your training can provide you with that password so you are able to see the lan environment as shown at the beginning of the lab.

![Configuration Platform 1.0](images/lab-A-005.png)

If the environment is stopped, please start it by using the "play" button in the top right corner to start the environment 

![Start Skytap lab environment](images/lab-A-006.png)

and wait till both VMs are started.  

![Start Skytap lab environment](images/lab-A-007.png)

## Deploy the Cloud Connector

Now that the lab environment is in a running state, follow the below steps to get the Cloud Connector deployed.

1. Click on the **SSPM** desktop to open the console of the SSPM server
2. Log into the server user the following credentials:

   - **Username:** THYLAB\adm-training
   - **Password:** *Provided by the trainer*

3. Open Chrome and navigate to the URL of your cloud tenant ``https://<tenant>.my.centrify.net`` and login using the same account (**admin@lab\<tenant\.>**) using *your set password*. The same as you did before on your machine.

   ![Start Cloud environment](images/lab-A-008.png)

4. Click the **Next** button in the *Welcome...* Screen

   ![Connector lab environment](images/lab-A-009.png)

5. Click **Centrify Connector** in *Download and Install*

   ![Connector lab environment](images/lab-A-010.png)

6. Extract the downloaded Zip file and run the **Centrify-Connector-Installer-22.1.exe** to install the Connector in the extracted folder

   ![Connector lab environment](images/lab-A-011.png)

7. In the *Security Warning* click **Run**

   ![Connector lab environment](images/lab-A-012.png)

8. Click **Next** in the window that opened
9. Check the "I have read and accept the terms...." and click **Next**
10. In the next screen, leave everything default and click **Next**
11. Click **Install** to have the connector installed
12. In the last screen, click **Finish** to end the installation phase

## Configure the Cloud Connector

Now that the cloud connector has been installed it needs to be configured so it can "talk" to the Cloud Tenant

1. After the installation is done, a new screen opens
2. Click **Next**

   ![Connector lab environment](images/lab-A-013.png)

3. Leave the checkbox checked and click **Next**

   ![Connector lab environment](images/lab-A-014.png)

4. Leave all default and click **Next**
5. In the next screen provide **YOUR cloud tenant** (you can copy and paste it from the Chrome address bar). Leave the **Temporarily add...** checked

   ![Connector lab environment](images/lab-A-015.png)

6. Click **Next**
7. Login as the admin@lan.\<tenant\> user in the screen that opens up
8. If the credentials were ok, a new screen will open. Leave all default (*Use Current user credentials*) and click **Next**

   ![Connector lab environment](images/lab-A-016.png)

9. In the *Please select the monitored domain...*, select the **thylab.local** account and click **Next**

   ![Connector lab environment](images/lab-A-017.png)

10. In the popup windows, click **Yes**

    ![Connector lab environment](images/lab-A-018.png)

11. Checks will be run to make sure all is ready for the connector to connect to the Cloud Tenant

    ![Connector lab environment](images/lab-A-019.png)

12. Click **Next** to proceed
13. This will Register the Connector to the Cloud Tenant and start the needed services.
14. If all went 100% you will get the below screen

    ![Connector lab environment](images/lab-A-020.png)

15. Click **Finish**
16. A new screen pops up and show that the software is up to date and connected successful (status tab)

    ![Connector lab environment](images/lab-A-021.png)

17. On the Connector tab, you can see where the connector is registered and if the Connector is running

    ![Connector lab environment](images/lab-A-022.png)

18. Click **Close**
19. Return to the Chrome session and you should now see that a **Connector Ready** message

    ![Connector lab environment](images/lab-A-023.png)

20. Click **Next**
21. In the *Discover Systems* click **Cancel**

    ![Connector lab environment](images/lab-A-024.png)

---

**Note**

The reason for canceling this step is that we will get the systems "pushed" out of the Secret Server installation. If you let the Cloud tenant discover systems, there is a change that the systems and corresponding secrets are NOT imported if the secrets have the same machine name in it. This will be solved in a new version of the RAS solution.

---

22. Navigate to **Settings > Network > Centrify Connector** and you will see the connector called **SSPM** mentioned

    ![Connector lab environment](images/lab-A-025.png)

23. Refresh you browser. The *Welcome to...* screen will appear
24. Check the **Do not show again** 

    ![Connector lab environment](images/lab-A-026.png)

25. Click **Cancel**

# Integrating existing Secret Server

Now that the Cloud Connector has been installed we can proceed in integrating the Secret Server that is installed in the Skytap environment

## Log into the Secret Server

1. Open the Secret Server UI by opening a new tab and navigate to https://sspm.thlab.local/secretserver 

   ---

   **Note**
   
   As this is the first time the UI is started, it will take some time as IIS needs to start the processes and load it into memory

   ---

2. Login as

   - **Username:** ss_admin
   - **Password:** *Provided by trainer*
   - **Domain:** Local

   ![Connector lab environment](images/lab-A-027.png)

3. Click on the **Secret Server** "button"

   ![Connector lab environment](images/lab-A-028.png)

4. Now all you will see all secrets that have been created

## Create a "sync" user

For the integration between the Secret Server and the Cloud tenant, we are going to setup an account that will be used to "sync" the secrets.

1. Navigate to **Admin > User Management** and click on the **Create User** button

   ![Connector lab environment](images/lab-A-029.png)

2. Create a user using the following parameters:

   - **Username:** sync_user
   - **Display Name:** Sync User
   - **Domain:** Local
   - **New Password:** *Choose your own*
   - **Confirm Password:** *Choose your own*
   - **Application Account:** Checked
   - **Enabled:** Checked

   ![Connector lab environment](images/lab-A-030.png)

3. Click **Add User**
4. Click the **sync_user** and open the *Roles* tab
5. Clik the **Edit** text next to the *User Roles* and Remove the User and add the Administrator Role to the account
6. Your configuration for the roles should look like the below screenshot

   ![Connector lab environment](images/lab-A-043.png)

The steps on the Secret Server are now done and we need to switch to the Cloud tenant to integrate the Secret Server.
## Configure Cloud Tenant

To integrate the following steps will be configured:

1. Create a new role
2. Add the Vault
3. Configure the Vault integration
4. Synchronisation of the secrets

### Create a new Role
1. Open in the browser the Tab on which your cloud tenant is active
2. Navigate to **Access > Roles**
3. Click **Add Role**
4. Name the New Role **PAS User** and provide the description: *PAS User role for Users that need some access to the cloud tenant*
5. Click on the left side of the pane, **Administrative Rights**
6. Click the **Add** button

   ![Connector lab environment](images/lab-A-036.png)

7. Check the **Privileged Access Service User**

   ![Connector lab environment](images/lab-A-037.png)

8. Click **Add**
9. Click **Save**
10. Your role should be shown in the list of roles

    ![Connector lab environment](images/lab-A-038.png)

Now that we have the Role ready we can proceed to next step. Adding the Secret Server to the Cloud tenant

### Connect the Secret Server

2. Navigate to **Resources > Vaults**
3. Click **Add Vault** next to the *Search bar*
4. Fill out the fields using the following information:

   - **Name:** On Prem - Secret Server SSPM
   - **Description:** On Prem - Secret Server SSPM
   - **Vault Type:** Secret Server
   - **Vault Location:** On-premises
   - **URL:** https://sspm.thylab.local/SecretServer
   - **User name:** sync_user
   - **Password:** *The password you set during the creation of the account*
   - **Enable Sync Interval:** Unchecked for now

   ![Connector lab environment](images/lab-A-032.png)

5. Click **Next**
6. In the *Add Secret Server Vault* we can only change the **Add to Sets** section (as mentioned in the Information bar, we cannot do anything else AFTER we added an on-prem Secret Server)
7. Change the *Add to Sets* to **Create Sets based on Secret Server folder hierarchy**

   ![Connector lab environment](images/lab-A-033.png)

8. Click **Done**
9. Your definition will be shown

   ![Connector lab environment](images/lab-A-034.png)

### Configure the connected vault
10. Click the definition
11. Click on the **Connectors** setting
12. Select the **Choose** and click the **checkbox** in front of the SSPM connector.

    ![Connector lab environment](images/lab-A-035.png)

13. Click the **Permissions**
14. Click the **Add** button

    ![Connector lab environment](images/lab-A-039.png)

15. In the Search bar type *PAS* and select teh **PAS User**

    ![Connector lab environment](images/lab-A-040.png)

16. Click **Add**
17. Make sure the PAS User has the *View* checked (default)
18. Click the **Template Mapping**
19. Set the *Windows Systems* to include the following Templates:

    - Windows Account

20. Set the *Unix Systems (Password Credentials)* to include the following Templates:

    - Unix Account (SSH)
    - Unix Account (SSH)(Session Connector)
    - Unix Root Account (SSH)

21. Set the *Unix Systems (SSH Key Credentials)* to include the following Templates:

    - Unix Account (Privileged Account SSH Key Rotation - No Password)
    - Unix Account (Privileged Account SSH Key Rotation)
    - Unix Account (SSH Key Rotation - No Password)
    - Unix Account (SSH Key Rotation)

22. Set the *Active Directories* to include the following Templates:

    - Active Directory (Hidden Details)
    - Active Directory (Multiple Launchers)
    - Active Directory (No Heartbeat)
    - Active Directory (Restricted Launcher
    - Active Directory (Session Connector)
    - Active Directory Account

23. Your configuration should look like the below screenshot

    ![Connector lab environment](images/lab-A-044.png)

24. Click **Save**

### Synchronisation of Secrets

1. Click **Actions > Verify** to see that the connection can be made to the Secret Server. If the connection was successful, you will see this appear at the top of the screen

    ![Connector lab environment](images/lab-A-042.png)

2. Click **Actions > Sync** to start the synchronisation of the secrets in Secret server

   ![Connector lab environment](images/lab-A-041.png)

3. While still in the settings of the Vault, click on History to see that the synchronsation has taken place

# Test configuration

