#ssm后台环境搭建
###SpringMVC
######DispathcherServlet类
核心本质: 是一个Servlet

作用:就是初始化组件

基于Model2实现的技术框架:jsp+servlet+javaBean

底层的机制:MVC

环境搭建好以后

登录的小案例:
1. new --> Maven Project --> next --> maven-archetype-webapp --> 配置id

2. 引入Tomcat: 项目名 --> biuld path --> add library --> server  runtime --> tomcat

3. 引入spring相关的maven依赖

4. 导入spring配置文件pom.xml

5. web-inf 中的web.xml文件中配置spring相关信息

6. 新建jsp文件

7. 如果缺少source文件夹,就选中项目右键,biuld path --> new source floder




