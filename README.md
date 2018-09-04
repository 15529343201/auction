# Angular 4.0打造在线竞拍网站
## chapter2 开始Angular开发
### Angular程序结构
![image](https://github.com/15529343201/auction/blob/chapter2/image/1.PNG)<br>
- 组件:是Angular应用的基本构建块,你可以把一个组件理解为一段带有业务逻辑和数据的HTML
- 服务:用来封装可重用的业务逻辑
- 指令:允许你向HTML元素添加自定义行为
- 模块:用来将应用中不同的部分组织成一个Angular框架可以理解的单元

### 搭建Angular开发环境
- 安装Nodejs、Angular CLI、WebStorm
- 使用Angular CLI创建并运行Angular项目
- 分析Angular项目的目录结构及Angular CLI生成的基础代码

```
npm install -g @angular/cli
npm install -g @angular/cli@1.0.0
ng -v
ng new auction
```
![image](https://github.com/15529343201/auction/blob/chapter2/image/2.PNG)<br>
Angular cli 工具生成的目录文件名不要随意修改，要不然会影响工具的使用。<br>
- e2e：端到端的测试目录，用来做自动测试的。
- node_modules：Angular第三方包。
- src：应用源代码目录，我们写的代码在这里面。
- .editorconfig：webstrom IDE配置文件。
- .gitignore：git配置文件。
- .angular-cli.json：Angular命令行配置文件，实际项目中会修改该文件，引入第三方包等。
- karma.conf.js：karma是单元测试的执行器，是karma的配置文件。
- package.json：npm的Angular第三方包目录，在命令行创建项目的时候，会根据这个配置文件去下载第三方包，保存在node_modules中。
- protractor.conf.js：自动化测试的配置文件。
- README.md：命令行的使用说明。
- tsconfig.json：Typescript编译成JavaScript的配置文件。
- tslint.json：Angular代码检测配置文件。

![image](https://github.com/15529343201/auction/blob/chapter2/image/3.PNG)<br>
组件:<br>
```
import { Component } from '@angular/core';

@Component({
  selector: 'app-root',
  templateUrl: './app.component.html',
  styleUrls: ['./app.component.css']
})
export class AppComponent {
  title = 'app works!';
}
```
模块:<br>
```
import { BrowserModule } from '@angular/platform-browser';
import { NgModule } from '@angular/core';
import { FormsModule } from '@angular/forms';
import { HttpModule } from '@angular/http';

import { AppComponent } from './app.component';

@NgModule({
  declarations: [
    AppComponent
  ],
  imports: [
    BrowserModule,
    FormsModule,
    HttpModule
  ],
  providers: [],
  bootstrap: [AppComponent]
})
export class AppModule { }
```
angular 如何启动项目:<br>
1.当你在命令行中输入 ng serve 后<br>
2.ng 会根据 angular-cli.json 中的 main元素 找到 应用入口文件main.ts<br>
3.main.ts 再加载 根模块AppModule<br>
4.AppModule 启动Angular模块(@ngModule)<br>
5.@ngModule 为 AppModule 添加元数据,并指定了顶层组件AppComponent<br>
6.AppComponent 中我们就可以为所欲为了<br>
![image](https://github.com/15529343201/auction/blob/chapter2/image/4.PNG)<br>
Angular4启动过程:https://blog.csdn.net/It_rod/article/details/78837101<br>   
### 开发准备
```
npm install jquery --save
npm install bootstrap --save
"styles": [
        "styles.css",
        "../node_modules/bootstrap/dist/css/bootstrap.css"
      ],
      "scripts": [
        "../node_modules/jquery/dist/jquery.js",
        "../node_modules/bootstrap/dist/js/bootstrap.js"
      ],
npm install @types/jquery --save-dev
npm install @types/bootstrap --save-dev
ng g component navbar
ng g component footer
ng g component search
ng g component carousel
ng g component product
ng g component stars
```
### 开发app组件
```
<app-navbar></app-navbar>
<div class="container">
  <div class="row">
    <div class="col-md-3">
      <app-search></app-search>
    </div>
    <div class="col-md-9">
      <div class="row">
        <app-carousel></app-carousel>
      </div>
      <div class="row">
        <app-product></app-product>
      </div>
    </div>
  </div>
</div>
<app-footer></app-footer>
```
![image](https://github.com/15529343201/auction/blob/chapter2/image/5.PNG)<br>
### 开发navbar和footer组件
```
<nav class="navbar navbar-inverse navbar-fixed-top">
  <div class="container">
    <div class="navbar-header">
      <button type="button" class="navbar-toggle" data-toggle="collapse" data-target=".navbar-ex1-collapse">
        <span class="icon-bar"></span>
        <span class="icon-bar"></span>
        <span class="icon-bar"></span>
      </button>
      <a class="navbar-brand" href="#">在线竞拍</a>
    </div>
    <div>
      <ul class="nav navbar-nav navbar-ex1-collapse">
        <li><a href="#">关于我们</a></li>
        <li><a href="#">联系我们</a></li>
        <li><a href="#">网站地图</a></li>
      </ul>
    </div>
  </div>
</nav>
```
```
<div class="container">
  <hr>
  <footer>
    <div class="row">
      <div class="col-lg-12">
        <p>Angular入门实践</p>
      </div>
    </div>
  </footer>
</div>
```
![image](https://github.com/15529343201/auction/blob/chapter2/image/6.PNG)<br>
