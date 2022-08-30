# Test the basic configuration

Now putting everything together a test is to be run to see if the scenario can be solved using the configuration and setup that have been done.

1. Using your physical machine, open a new tab and navigate to the URL of your cloud tenant ``https://<tenant>.my.centrify.net`` and login with **alex.johnson@lab.<tenant\>** using the initially set password

    ![Connector lab environment](../images/lab-A-056.png)

2. As the default system is set to change the password, provide the new password for the account

    ![Connector lab environment](../images/lab-A-057.png)

3. After you have set the new password, and it has been accepted by the system, click the **Start Over** text in the top right corner

    ![Connector lab environment](../images/lab-A-058.png)

4. Login using the new password and the UI should open.

    ![Connector lab environment](../images/lab-A-059.png)

5. Navigate to **Resources > Systems** and the *fin-rtr.thylab.local* system should be shown
    ![Connector lab environment](../images/lab-A-061.png)

6. Right click the system and select **Select/Request Account**

    ![Connector lab environment](../images/lab-A-062.png)

7. The *vyos* account should be shown

    ![Connector lab environment](../images/lab-A-063.png)

8. Select the *vyos* account, and click **Select** a new window will open where the connection should be made. After a few seconds the screen will show the commandline of the vyos router

    ![Connector lab environment](../images/lab-A-065.png)

9. Close the connection by typing *<CTRL\>+D* and click **Close** on the information screen which will close the screen

    ![Connector lab environment](../images/lab-A-066.png)