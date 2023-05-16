# NodeJS 01｜Node & NPM & package.json
> 此篇笔记是**「WebDev笔记」**系列**NodeJS专题**的第1篇，记录了如何安装Node.js、导入Node.js的内部模块以及利用`npm`初始化(`npm init`)、安装(`npm install`)外部的依赖包(packages/dependencies)并生成`package.json`
### 0. Front-End vs Back-End Web Dev
![](https://files.mdnice.com/user/1474/c7d4b72f-9c14-4fa8-b24c-a62dbd0e9c4f.jpg)

`HTML` and `CSS` enable us to design website and allow for user interaction on the client side in the browser (web app)
- `Node.js` and Python (server-side languages) enable us to **interact with databases** and build complex data structures and algorithms to provide buisness logic and value to userson a server side
- Database “languages” like SQL allow us to **store and access persistent data**

![](https://files.mdnice.com/user/1474/9dc588b9-c440-4f77-aaff-53f80e26ce31.jpg)


### 1. Install Node.js
#### 1.1. Download LTS Installer
Go to `https://nodejs.org/en/`

![The LTS version is 18.14.2 in 2023.02.21](https://files.mdnice.com/user/1474/5f152ad6-22ed-4eea-afc1-aeb7c64e7a6f.png)
#### 1.2. Run the Installer
![](https://files.mdnice.com/user/1474/caef09af-4f01-4cc4-b6be-e87d274257e5.png)
#### 1.3. Check the node version in terminal
```shell
$ node --version # 18.14.2
```

### 2. Built-in Node Module
A **Module** in Node.js is **a set of functions**
- Node.js has a set of built-in modules which we can use without any further installation.
- `https://nodejs.org/api/` provides Built-in Modules such as `fs` that enables **interacting with the file system**

#### 2.1. Import and use Built-in module `fs`:
- `fs.copyFileSync(src, dest)` **synchronously copies** `src` to `dest`. 
  - `dest` is overwritten if it already exists, otherwise, `dest` will be created
```javascript
// index.js
const fs = require("fs");

src = "source.txt";
dest = "destination.txt";
fs.copyFileSync(src, dest);
console.log("source.txt was copied to destination.txt");
```
#### 2.2. Execute js with node in terminal
```shell
$ node index.js
```
![](https://files.mdnice.com/user/1474/b567826c-c81e-4ff7-b7ec-1c39ead7c949.png)

### 3. NPM Package Manager for External Node Modules
NPM is a **package manager** for Node.js packages
- `www.npmjs.com` hosts thousands of free packagesto download and use.
- **A package is one or more modules** grouped (or packaged) together. 
#### Initiate a Package
```shell
$ npm init
```
Use `npm init` to create a `package.json` file is typically the first step in a Node project, 

![](https://files.mdnice.com/user/1474/05874235-4c7f-431e-96ba-618791dab7b9.png)
- we need one to hold important metadata about your project and install dependencies in npm.

#### Install Packages (Dependencies)
```shell
$ npm install superheroes
$ npm install supervillains
```
![](https://files.mdnice.com/user/1474/f0a0b750-a3f5-4046-afd6-cb2732f416fc.png)

#### Resources:
- https://blog.codeanalogies.com/2018/04/07/front-end-v-back-end-explained-by-waiting-tables-at-a-restaurant/
- https://blog.codeanalogies.com/2020/01/21/web-development-explained-by-trying-to-run-a-restaurant/
- https://nodejs.org/en/
- https://nodejs.org/api/
- https://nodejs.org/api/fs.html
- https://www.npmjs.com/
- https://www.npmjs.com/package/superheroes
- https://www.npmjs.com/package/supervillains
