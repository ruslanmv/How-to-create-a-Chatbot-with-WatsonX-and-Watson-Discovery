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

# Step 2. Setup WatsonX
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
   
# Step 3 - Setup Watson Discovery
In the menu of IBM cloud we go to resource list, and in the section of
`AI / Machine Learning`

![](assets/20230808214104.png)
we go click to Watson Discovery service and then
![](assets/20230808214243.png)
we have two additional numbers to conserve here
1. API key
2. URL

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
