# How to Connect Watson Assistant with WatsonX and Watson Discovery

Today we are going to setup Watson Assitant with Watson Discovery and WatsonX.
We are going to use the standard toolkit of IBM Developer.

# Step 1 - Create services in IBM Cloud.
First we need to login to IBM Cloud

https://cloud.ibm.com/

We need to create the following services
1. [WatsonX](https://www.ibm.com/watsonx?)
2. [Watson Discovery](https://www.ibm.com/products/watson-discovery)
3. [Watson Assistant](https://cloud.ibm.com/catalog/services/watson-assistant)

After you have created those services, we have to setup them.

# Step 2. Setup of WatsonX
After you have created your instance in WatsonX
![](assets/20230808211802.png)
we open a simple prompt lab
![](assets/20230808212344.png)

we click over view code
![](assets/20230808212502.png)
and click create personal API key
and we create
![](assets/20230808213210.png)
and we download the `API key` that we will use.

Then we return back to our Prompt Lab and in the view code we copy our 
`project_id`.
So we should have the following two numbers, for exaple:

1. **API Key**
2. **project_id**
   
# Step 3 - Setup of Watson Discovery
In the menu of IBM cloud we go to resource list, and in the section of
`AI / Machine Learning`

![](assets/20230808214104.png)
we go click to Watson Discovery service and then
![](assets/20230808214243.png)
we have two additional numbers to conserve here
1. **API Key**
2. **URL**

Notice that this API key is different to our previous case. This is for this service.

Now lunch this service and we create New project
![](assets/20230808214539.png)

In this example we are goint to analize Bitcoins, so the project will be named `Bitcoin`
![](assets/20230808214617.png)
then we select`Conversational Search`
we have different options to retreive the data, we choose `Web crawl` and click `Next`
![](assets/20230808214827.png)
We choose a crawling each month

![](assets/20230808215007.png)

and we chose the url to crawl
https://bitcoin.org/en/faq
![](assets/20230808215030.png)
and finally click finish.
After few minutes. You can get sometihng like
![](assets/20230808215134.png)
then you go to your menu and click `Integrate and Deploy`and you will get another `project_id`
![](assets/20230808215249.png)
so we will have our third important number to keeep for the Watson Assistant.
3. **project_id**

# Step 4 - Setup Watson Assistant.
Let us return back to our IBM cloud and there in resource list, let lunch Watson Assistant and create a new assitant
![](assets/20230808220116.png) and you will get something like

![](assets/20230808220241.png)

then in the menu click integrations, we will install two integrations.
Click on `Build extensions`
![](assets/20230808220353.png)
1. Watson Discovery Extension
   First, we name it as Watson Discovery Extension
   ![](assets/20230808220502.png)
   then you have to download the openapi of this extension here
  [https://github.com/ruslanmv/How-to-create-a-Chatbot-with-WatsonX-and-Watson-Discovery/blob/master/watson-discovery-query-openapi.json](https://github.com/ruslanmv/How-to-create-a-Chatbot-with-WatsonX-and-Watson-Discovery/blob/master/watson-discovery-query-openapi.json)

  ![](assets/20230808221657.png)
  and then click Finish

  ![](assets/20230808221723.png)
  then we click add and then we paste our **API Key** and **URL** from Watson Discovery setup.
 ![](assets/20230808222046.png) and click finish
 ![](assets/20230808222241.png)


2. WatsonX Extension
   We repeat the same, we go to Extensions and Build a new custom extension

   ![](assets/20230808222348.png)
   which we call WatsonX extension

   ![](assets/20230808222420.png)
   then we download the openapi of WatsonX from here
   [https://github.com/ruslanmv/How-to-create-a-Chatbot-with-WatsonX-and-Watson-Discovery/raw/master/watson-discovery-query-openapi.json](https://github.com/ruslanmv/How-to-create-a-Chatbot-with-WatsonX-and-Watson-Discovery/raw/master/watson-discovery-query-openapi.json)


   ![](assets/20230808222534.png)
   and we click Finish

   ![](assets/20230808222949.png)
   On the Extensions we click `Add`

   ![](assets/20230808223023.png)
   we paste our API Key that was created in the WatsonX setup
   ![](assets/20230808223206.png)
   we click `Next` and then `Finish`

   ![](assets/20230808223234.png)

In the Integrations menu you should have the active two integrations

![](assets/20230808223324.png)
with the word `Open`

# Step 5 - Creation of Applications fo Watson Assitant.

In this part we are going to build some standard applications.
Go to `Actions` then Click on the button `Global Settings`
![](assets/20230808223632.png)
On the menu, go to the last tab called `Upload/Download`

![](assets/20230808223735.png)
and then download this file from here
[https://github.com/ruslanmv/How-to-create-a-Chatbot-with-WatsonX-and-Watson-Discovery/raw/master/discovery-watsonx-actions.json](https://github.com/ruslanmv/How-to-create-a-Chatbot-with-WatsonX-and-Watson-Discovery/raw/master/discovery-watsonx-actions.json)

and upload it
![](assets/20230808223806.png)


click upload and replace

![](assets/20230808224016.png)
go to  `Variables ` then in the tab `Created by You`
![](assets/20230808224204.png)
 You have to edit the following variables:
 1. **discovery_project_id** -  From the Discovery Setup  you can copy the Project ID
![](assets/20230808224359.png)
![](assets/20230808224428.png)
2.**watsonx_project_id** - From you WatsonX Setup you copy your **project_id**
![](assets/20230808224624.png)

After you have updated all variables. You can test by click `Try`
and you can ask like
`How are bitcoin transactions?`

![](assets/20230808231106.png)
`What is bitcoin?`

![](assets/20230808231150.png)
