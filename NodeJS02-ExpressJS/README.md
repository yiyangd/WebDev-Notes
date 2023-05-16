# NodeJS 02｜Build a Server with express.js
> 此篇笔记是**「WebDev笔记」**系列**NodeJS专题**的第2篇，记录了如何安装Express.js并搭建一个服务器(Server)，并将整条构建的流水线比喻成：
> - [1]雇佣帮助老板管理新餐厅的经理(`express`)，
> - [2]选择餐厅的地址(服务器端口 `Port:3000`), 
> - [3]当用户访问餐厅时(`/`)与用户打招呼并询问信息 
> - [4] 当用户提交信息之后将用户带领到餐桌(`/table`)
### 1. Install Express.js
![](https://files.mdnice.com/user/1474/94f93d1f-01bd-4ccb-b1ff-a82697eb279f.png)

Go to `https://expressjs.com/en/starter/installing.html`, follow the installation steps:
```shell
$ npm init
$ npm install express
```

### 2. Build a simple Server app with express.js
Restaurant Analogy: 

![](https://files.mdnice.com/user/1474/eefaf325-5324-4c90-996d-986a560dee3a.png)

#### 2.1. The require statements (hiring the manager)
```js
const express = require('express')
const app = express()
```
- `express` is the **new manager we hired** by `require('express')`
- a `app` is an instance of `express`.
#### 2.2. Start the Server(Restaurant) by using app.listen()
We need to **determine the address for the location** of the restaurant.  

The **server** has `ports` that are kind of like **the `address` for the *restaurant***. 
- since server can handle **many types of restaurants** (or `server-side scripts`) at once, 
- we need to tell it **where each script should run**.
```js
port = 3000
app.listen(port, () => {
  console.log(`Restaurant(Server) started on port ${port}`)
})
```
![](https://files.mdnice.com/user/1474/fe3d9b95-d4fb-4e6c-946d-2ab5a16fbc43.png)

#### 2.3. Routing
> # Boring Definition: 
> **Routing** refers to determining **how an application `responds` to a client `request`** to a **particular endpoint**
> - which is a URI (or path) and a specific HTTP request method (`GET`, `POST`, ...)
#### 2.3.1. GET Request
When Customers (Clients) walk into main door(``"localhost:3000/"``) of restaurant (server) and **requesting for a service**, the manager should **response this request with "Welcome to the Restaurant" and an information form** (created in a `index.html`)
- to ask name and the number of people

```js
app.get("/", function (req, res) {
  //res.send("<h1>Welcome to the Restaurant！</h1>");
  res.sendFile(__dirname + "/index.html");
});
```
![](https://files.mdnice.com/user/1474/ca43267c-5f1b-437e-a2f1-5cb300d6c78c.png)
#### 2.3.2. POST Request
Customers need to `post` another `request` with their information and click `submit` button, then Manager will lead customers to the table.

```js
const bodyParser = require("body-parser");
app.use(bodyParser.urlencoded({ extended: true }));
app.post("/table", function (req, res) {
  var name = req.body.name;
  var num = req.body.num;
  res.send(`Good evening, ${name} ! I will lead you to your table of ${num}`);
});
```

![](https://files.mdnice.com/user/1474/21379b75-efcb-49db-a1be-a40676e343ca.png)


#### Resources:
- https://expressjs.com/en/starter/installing.html
- https://www.excellentwebworld.com/what-is-expressjs-in-node-js/
- http://www.codeanalogies.com/
- https://blog.codeanalogies.com/2017/11/03/understanding-the-basics-of-express-js/
