## Provision an Azure Function App Using the Azure Portal
The app should be provisioned under the Consumption plan, with a backing storage account.

## Deploy a C# .NET Core Function in the App Based on the HTTP Trigger Template
The function code should be modified to return a simple greeting using the student’s name.
The app tests successfully by returning a simple greeting when run.

#### Reference: https://gorillalogic.com/blog/azure-developer-tutorial-http-trigger-functions-with-c-and-net-core/

## Extend the Project by Adding a NuGet Package Configuration
A function.proj file should be created in the function project.
The function.proj file includes the proper NuGet package reference to an HTML parser library.

## Extend the Function Code to Scrape a Website and Return a URL
The code should be modified to find a specific link on the supplied NPPES web page.
The function tests successfully by returning the URL.

refer: https://github.com/linuxacademy/content-Intro-to-serverless-on-Azure

```
Additional Resources
GitHub repository with readme file and code snippets: https://github.com/linuxacademy/content-Intro-to-serverless-on-Azure

Imagine you need to regularly download and process a public data set of physicians, but the naming convention of the file 
is not strictly enforced, requiring frequent human intervention to retrieve the most recent file from a link on a website. 
Further, the posting date of the monthly file is inconsistent, so you need to be able to check for the most current file 
name so that downstream processes can determine when a refresh is appropriate. The rest of your workflow is already automated; 
you just need to add a custom application to sort out the file name to fully automate the integration pipeline.

This is one kind of challenge that Azure Functions were designed to address. You will first learn how to provision a 
Function App, then create and test a canned C# .NET function in that app using an HTTP trigger template. 
After testing the canned function, we will modify its configuration and C# code to scrape a government website. 
Our goal will be to retrieve the URL of the latest monthly file containing U.S. physicians and their national identifiers. 
The URL string will be returned for further processing by a data pipeline.
```
