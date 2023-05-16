# WebDev Note｜NodeJS 03｜用餐厅的比喻来理解API
> 此篇笔记是**「WebDev笔记」系列NodeJS专题**的第3篇，记录了通过用餐厅的比喻来介绍API的概念以及通过NodeJS调用Open Weather API实现一个查询城市温度和天气的功能。
> - 1
> - 2
### 1. An Analogy for API
![](https://files.mdnice.com/user/1474/eefaf325-5324-4c90-996d-986a560dee3a.png)
In the last note we wrote that suppose you are the owner of a restaurant, hired the front-of-house waiters and the back-of-house chefs, have developed their workflow and the food menu, finally selected a location to open the restaurant.

![](https://files.mdnice.com/user/1474/8e052084-212d-4988-bec8-a7b41a5d803a.png)

The **waiter** represents the **interface** between the **customer (the developer)** and the **kitchen (the application)**. The customer, who is **unfamiliar with the restaurant's dishes (services/products) and prices**, relies on the **menu (API catalogue)** to place an order with the waiter, who then forwards the order to the kitchen. 
- Customers do not need to (and cannot) go to kitchen to make foods on their own, and do not need to understand the process of growing food (how to produce and process raw data)



![](https://files.mdnice.com/user/1474/ef3a403b-8c14-43d2-8823-1e16361f718b.png)


Farm owners also need to set up processes (API) so that they can successfully serve these restaurants. 
- Similarly, an API is a structured way that others can utilize your server-side code. 
- As the developer, you still have full control.


### 2. An Example: Open Weather API
Go to `https://openweathermap.org/current` to check the Weather API document


![](https://files.mdnice.com/user/1474/245c46ef-f8b1-4af2-a714-0dfa897f9802.png)

#### 2.1. API request by city name
We can call by city name, state code and country code. API responds with a list of results that match a searching word.
- parameters `q` and `appid` are required for `{city name}` and `{API Key}`
- optional parameter `mode` is for response data format. Possible values are `xml` and `html`. 
  - If you don't use the `mode` parameter format is `JSON` by default.
- optional parameter `units` is for units of temperature. Possible values are `standard` (default, in Kelvin), `metric`(in Celsius) and `imperial` (in Fahrenheit). 

![](https://files.mdnice.com/user/1474/9c9d4d23-6206-4f0d-bf21-b2f0a9f19adf.png)

#### 2.2. Use Postman to test API

![](https://files.mdnice.com/user/1474/3e053390-5b58-4f10-820f-4a193f901dfe.png)
### 3. Implement Weather Query Functionality using Node's HTTPS Module
#### 3.1. Build a Weather Query Form
Create `WeatherProject/index.html`, creates a `<form>` that allows users to **input data** and **submit it to a specified location**.
- The `action="/"` attribute **specifies the URL or path where the form data will be submitted**. 
  - In this case, the form data will be submitted to the `root URL ("/")` of the current web page.
- The `method="post"` attribute **specifies the HTTP method** to be used when submitting the form. 
  - In this case, it is set to `"post"` which means the `form data` will be sent as a **request body to the server**.

![](https://files.mdnice.com/user/1474/429df615-afe3-4c53-b471-b57aa2de4337.png)
#### 3.2. Display Weather API Query Results


![](https://files.mdnice.com/user/1474/4ee59348-b6d8-44e1-8b6f-6181218038f2.png)


#### Resources
- https://blog.codeanalogies.com/2018/02/27/web-apis-explained-by-selling-goods-from-your-farm/
- https://www.manutan.com/blog/en/glossary/api-definition-and-application-in-procurement
- https://www.prostdev.com/post/understanding-apis-part-1-what-is-an-api
- https://www.prostdev.com/post/understanding-apis-part-2-api-analogies-and-examples
- https://www.prostdev.com/post/understanding-apis-part-3-what-are-http-methods
- https://www.prostdev.com/post/understanding-apis-part-4-what-is-a-uri
- https://www.prostdev.com/post/understanding-apis-part-5-intro-to-postman-and-query-parameters
