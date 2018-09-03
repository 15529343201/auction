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
