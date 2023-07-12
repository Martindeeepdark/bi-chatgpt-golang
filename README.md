Hello GoLang!


2023年7月9日00:30



BI-Golang-ChatGPT

本项目由Java+Spring Boot重构为Go+Gin，旨在提升自己Go语言开发技能

作为一名Go语言的初学者，重构期间学会了很多关于Go的开发规范问题，GoLang的生态，GoLang 的语言特点等等...所以项目还是编程学习的重要推进点

（原本学Java，之前想要在实习期间有一个学习Go的机会，所以目前实习部门是写Go+Python的）



首先介绍项目：

# 智能BI数据分析平台

项目简介：

​	BI工具大家知道很多，此项目与普通BI平台不同的是，在数据存储，数据清洗等环节之后，数据分析层面的统计分析、分析预测、数据可视化这三个层面来突破，系统亮眼的地方是将此处的工作交由ChatGPT来实施，通过用户上传的XLSX文件，对表格数据进行抽取整理交给ChatGPT来进行数据分析预测与可视化实现。

目前系统仅支持图表形式，用户可选择想要的呈现方式，比如：折线图、柱形图、饼图....更直观地展示数据分析结果，帮助用户理解和解读数据。



# 功能拓展

【时间紧张，并且处于项目网站目前功能单一以及初始目的是提高Go语言开发能力，并未涉及消息队列的部分内容】

1. **gin-jwt** Gin框架十分轻量，不像SpringBoot那样的保姆式框架，所以Session->Cookie等等操作都需要自己封装，所以我在项目中采用了JWT鉴权方式，引入了`github.com/appleboy/gin-jwt`库来统一处理token与http请求。
2. **封装对接chat请求** 在原先Java项目中，与ChatGPT的对接借用了开源sdk，只需要传ak,sk即可，所以我只能在这个项目中自己来封装对接Chat的请求，api-key也是购买的代理的。这里有个需要注意的，我试了很多次去直接请求官方的api地址【开了魔法也还是超时】，最后只能通过别人的代理地址去请求。
3. **新增管理用户消耗Token数界面** 此项目其实我想了想有哪些优化的地方，我反而觉得功能单一的界面其实并非应该优先考虑用户体验（此处指消息队列）我选择了一个简单省事的出于系统安全的优化点——计算用户Token数并且由管理员在后台查看管理。我引入了`github.com/pandodao/tokenizer-go`来方便计算每一次数据分析消耗的token值，这样就能直观的看到是谁最能白嫖(不是



## 印象里用到的库

`github.com/xuri/excelize/v2` —— 处理excel文件

`github.com/joho/godotenv`——Load .env文件

`github.com/swaggo/gin-swagger`——gin框架的swagger文档库

`github.com/duke-git/lancet/v2`——go语言的工具包,用得最多的是strutil

....

### 还学到了

在这个项目中，其实是熟悉了GORM的使用操作，在Token计算并且设计管理界面的时候，还用到了gorm的hooks去处理用户每次请求结束后数据库里Token字段对应值的同步问题。这里最深刻的印象就是全程跟着gorm文档走（gorm是国人开发的，文档其实很清晰，复杂一点的操作直接交给Chat，棒）

## 转Go心得

1. 还了解了很多GoLang的生态，其实我感觉转码的学习一定程度上是一种映射的理念，我之前学Java，现在部门里搞Go+Python时，不懵逼的前提就是把当前的业务场景去和Java对比，Java是怎么实现的，一步一步的映射回Go/Python的实现，自然思路就会清晰。转码过程中的懵逼我认为仅仅是生态的不熟悉，不知道引什么包或者不知道这里语法怎么会报警告...

2. Go语言的注解很清晰简洁！不像之前学习Java时点进原码其实我是看不懂注解意思的（我水平不行）只能硬着头皮看代码实现逻辑，但是Go社区内的注释规范很注重简洁直接，大部分都是几个词表述清楚这个func的含义。
3. 还有就是学习上的改变，学习Java时网上资源很全面，我往往直接带着问题去google。还有用了Gin才觉得SpringBoot是真的保姆框架。学Go期间多是带着问题去官方文档或者直接debug，这是我这段时间实习提升最快的能力之一。

...



界面展示：

![image-20230712205336132.png](/Users/wangmingyao/Downloads/afVHWOI8FpQqs4E.png)





![image-20230712205555067.png](/Users/wangmingyao/Downloads/9CvTGewIarod36F.png)



![image-20230712205854897.png](/Users/wangmingyao/Downloads/o5GxuNIs7HzWTkA.png)



![image-20230712205914683.png](/Users/wangmingyao/Downloads/KO2WiXUDQvzfHk5.png)



# 项目还未完成，仍会每天push代码

截图就可以看到还有很多粗糙的地方，我的前端水平是半吊子，还需要完善，我也会借助此项目来促进我的转Go之旅，项目在github上，如果可以，希望朋友们点个**star**=-=尊的谢谢



