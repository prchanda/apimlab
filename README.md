# APIM Troubleshooting Series Lab Instructions
This project contains all the required source code / binaries to setup labs for [APIM troubleshooting series](https://blogs.msdn.microsoft.com/pratyay/2018/07/29/azure-api-management-troubleshooting-series/). Here are the steps you need to follow in sequential fashion to setup the lab:-

1.	Install Git client for windows. You can download the setup file from here : https://git-scm.com/download/win
2.	Git clone or download the backend API project from this GitHub repo : https://github.com/prchanda/ProductStore
3.  Deploy / publish the ProductStore solution (backend API project) to a new or existing App Service using Visual Studio or any other deployment tool of your choice.
4.  Create an APIM instance. You can refer this article : https://docs.microsoft.com/en-us/azure/api-management/get-started-create-service-instance
5.  Download the APIM lab GitHub repository *apimlab.scm.azure-api.net.zip* from here : https://github.com/prchanda/apimlab/blob/master/apimlab.scm.azure-api.net.zip and extract it in your local drive.
6.	Navigate to the extracted directory and run the following git commands in sequence to push the local repository to your APIM instance.

    **git remote set-url origin {Your APIM repository URL}**
        
    **git push -f origin master**

7. Open up the Azure Portal and navigate to your APIM instance created in step 4. Under APIs blade change the backend url of the `ProductStore` API to the your App Service endpoint like below and Save it.
<br />


![Image of Yaktocat](https://github.com/prchanda/apimlab/blob/Images/ProductStore%20setting.png)



### Common Git Errors
----------------------

While pushing your local Git content to APIM, you may encounter few errors like below. Solution to those errors are included as well.

- **fatal: Authentication failed for 'https://apimlab.scm.azure-api.net/'**

This type of error can occur if your Git credentials are out of sync with your local windows credential manager. Try the following steps to Edit or Remove the saved credentials:

1. Click Start and type: `Credential Manager`.
2. Double click `Windows Credentials Manager` shortcut to open the application.
3. Once the application is opened, click on the `Windows Credentials` tab.
4. Locate the credentials that you want to remove/update, they will start with "git:" and might begin with "ada:".
5. Click on the credential entry, it will open a details view of the entry.
7. Click Edit or Remove as required and confirm.


If your local Git repository is corrupted you may get these below errors. Running `git repack` command should fix the corruption.

- **remote: error: unable to write sha1 filename ./objects/pack/pack-5aa087b92d89d817608f3f7809848e2297dea2d6.pack: Permission denied**
- **remote: fatal: cannot store pack file**
- **error: remote unpack failed: index-pack abnormal exit**
