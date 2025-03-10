### 介绍
java毕业设计，共享汽车管理系统
### 3000多套系统，需要联系
抠：3565014707 微：a13424421017

架构特征：
分层架构
Web层：controller 包处理 HTTP 请求（如 CommonController）。
业务层：service 包定义业务接口（CommonService）和实现（CommonServiceImpl）。
持久层：dao 包（CommonDao）与 resources/mapper 下的 XML 文件实现 SQL 映射。
实体层：entity 包定义数据库实体，vo（Value Object）和 view 包用于数据传输和视图模型。
权限控制
通过 AuthorizationInterceptor 拦截器和自定义注解 @APPLoginUser 实现登录验证。
前端路由（router-static.js）和后端接口配合实现访问权限管理。
前后端分离
前端代码位于 resources/admin，使用 Vue.js 构建 SPA（单页应用），通过 api.js 调用后端接口。
后端提供 RESTful API，静态资源通过 static/upload 存储上传文件。
二、功能模块解析
1. 核心业务模块（车辆管理系统）
车辆信息管理

qichexinxi（汽车信息）：管理车辆基础信息（型号、状态等）。
qicheruku（汽车入库）：记录车辆入库流程。
qichetoufang（汽车投放）：管理车辆投放区域和状态。
qicheguihai（汽车归还）：处理车辆归还登记。
订单管理

shiyongdingdan（使用订单）：跟踪车辆使用记录和订单状态。
区域管理

toufangdiqu（投放地区）：维护车辆可投放的地理区域。
2. 用户权限模块
用户管理

users 和 yonghu：管理后台用户账户（增删改查）。
密码修改功能（update-password.vue.bak）。
权限控制

通过 InterceptorConfig 配置拦截规则，AuthorizationInterceptor 校验用户登录状态。
3. 系统配置模块
参数配置
config 模块（ConfigEntity 和 add-or-update.vue）：管理系统参数（如文件上传路径、第三方 API 密钥）。
4. 工具与集成模块
文件上传

上传路径 static/upload，支持图片（如 1577351717989.jpg）存储。
第三方服务集成

BaiduUtil：集成百度 API（可能用于地图定位、OCR 识别等）。
三、技术栈推测
后端技术栈
框架：Spring Boot（SpringbootSchemaApplication 为启动类）
ORM：MyBatis（CommonDao.xml 为 SQL 映射文件）
依赖管理：Maven（pom-war.xml 用于 WAR 包构建）
部署：Tomcat（通过 WAR 包部署）
前端技术栈
框架：Vue.js（App.vue 和 main.js 为入口）
UI 库：ElementUI（element-variables.scss 为样式变量）
构建工具：Webpack（通过 babel.config.js 和 package-lock.json 推断）
图标：SVG 图标（svg 目录下的自定义图标）
