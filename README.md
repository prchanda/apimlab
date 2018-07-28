# APIM Troubleshooting Series
This project contains all the required source code / binaries to setup labs for APIM troubleshooting series. Here are the perquisites you need to follow in sequential fashion to setup the lab:

1.	Install Git client for windows. You can download the setup file from here.
2.	Git clone or download the backend API project from this GitHub repo : https://github.com/prchanda/ProductStore
3.  Create an APIM instance. You can refer this article : https://docs.microsoft.com/en-us/azure/api-management/get-started-create-service-instance
4.  Download the APIM lab GitHub repository 'apimlab.scm.azure-api.net.zip' and extract it. Navigate to the extracted directory and run the following got commands in sequence to push the local repository to your APIM instance.
5.	Navigate to the extracted directory and run the following got commands in sequence to push the local repository to your APIM instance.

    a.	git remote set-url origin <Your APIM repository URL>
   b.	git push -f origin master

6.	Open the ProductStore solution (which you have downloaded in Step - 2) using Visual Studio and deploy / publish it to a new or existing App Service.
