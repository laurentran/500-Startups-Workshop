# 500 Startups Workshop: Microsoft Azure
## Deploy your Website on Azure App Service

This lab steps through how to deploy a Node.js website on Azure Web Apps.  If you have a different backend than Node (Python, PHP, Java), you can still follow along and let us know if you have any questions or need help.

### Part 1: Create your Web App

1. Log into your Azure portal at [portal.azure.com](http://portal.azure.com) using the Microsoft Account email that you used to register for BizSpark.

2. On the left pane, click the green + sign to create a new resource.  

3. Click **Web + Mobile** -> **Web App**.

> <img src="/images/new-web-app.jpg" width="500">

4.	Fill out the **App Name**, and under the **Subscriptions** drop down, choose the correct subscription.  Your $360k subscription will be named something like **Microsoft Azure Sponsorship**.  Choose the **Microsoft Azure Sponsorship**.

> <img src="/images/web-app-details.png" width="300">
   
5.	Under **Resource Group**, create a new resource group.  This is a logical grouping for your services, so choose a name that makes sense for the resources.  
(For example, use **Website_RG**.  In the future, you can put resources like storage/databases that serve content for your website in the same resource group.)

6.	Under **App Service Plan/Location**, choose **Create New**, and enter the **App Service Plan** name and **Location**.  For **Pricing Tier**, choose **S2 or S3 Standard** depending on your needs.  We recommend **S3 Standard**.

> ![](/images/new-app-service.png)

7.	Click **Ok**, check **Pin to dashboard**, and click **Create**.
 
> <img src="/images/pin-to-dashboard.png" width="200">


### Part 2: Deploy your code from Github or other source control

8.	Let the Web App deploy, and once it’s deployed, it will show up under **All Resources** on your Azure portal dashboard.  It will also be pinned to your dashboard.  

* Click on your Web App.

> ![](/images/dashboard-resources.png)

9.	Go to **Deployment options** to set up your deployment source.  We’ll choose **Github**, but you can choose any of the options shown. 

> <img src="/images/deployment-options.png" width="300"><img src="/images/deployment-source.png" width="500">

10)	Configure your **Deployment Source**.  For Github:  Under **Authorization**, add your Github account.  Then choose your **Organization**, and the right **Project** and **Branch** that you want to deploy from.  [If you do not already have a Node.js app to deploy, fork this sample app from: [https://github.com/Azure-Samples/nodejs-docs-hello-world](https://github.com/Azure-Samples/nodejs-docs-hello-world), and point the deployment source to your fork.]

> <img src="/images/deployment-source-config.png" width="300">

11)	Click **Ok**, and Azure will deploy your code to your Web App.

12)	Navigate to your web app at **{yourAppName}.azurewebsites.net** to see your website!

 
### Part 3: The Kudu Console

13)	Navigate to the Kudu Console at **{yourAppName}.scm.azurewebsites.net**.  The Kudu Console is a tool that gives you both command line and file browser access to your sites.

14)	Click on the **Debug Console** on the top navigation pane, and **CMD** for the command line.

> ![](/images/kudu-console-1.png)

15)	Navigate around using the Folder UI.  For example, instead of typing 'cd site', you can just click on the site folder in the folder UI.  The console window automatically navigates to the same folder, so the two halves of the Console are working together.

* Navigate to **site** -> **wwwroot** to view the files that you deployed from Github (or other source).

> <img src="/images/kudu-console-2.png" width="400">

> <img src="/images/kudu-console-3.png" width="400">

> ![](/images/kudu-console-4.png)

16)	From the command line, you can do most standard console operations: changing folder, copy/rename/delete files, etc.

* You can use it to run arbitrary external commands. One good use case is to run git commands against your repository (if you are using git). For example, you can run 'git log', 'git status'. You can generally run arbitrary git commands, which can be useful to diagnose certain issues.

* You can use it for your **npm** commands if you are using Node.  For example, **npm update**, **npm install** …

17)	For other things you can do with the Kudu Console, see [https://github.com/projectkudu/kudu/wiki/Kudu-console](https://github.com/projectkudu/kudu/wiki/Kudu-console).


