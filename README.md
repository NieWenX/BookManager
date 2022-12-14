# 基于SSM的BookManager后台管理系统


## 主要技术
前端：采用JSP+bootstrap+JQuery,包含用户登录页面，系统首页，书籍查询结果页面，以及书籍增删改查询页面等；
后端：SSM框架+Redis,实现用户登录验证，用户注册、注销，以及管理书籍的增删改查。


## 主要模块和主要功能
 **用户管理模块** 
 1. 实现用户登录验证，用户注册，用户注销；用于登录验证中，也需要进行验证码验证，验证码通过Redis暂存，过期时间2分钟。
 2. 通过过滤器拦截未登录用户，避免用户非法访问。
 3. 客户端 Cookie 存储登陆成功的账户信息，实现记住密码功能；
 4. 用户登陆成功后，用户信息存储在Redis中，下次登录直接和Redis中数据验证即可。

 **书籍管理模块**
 1. 实现登录用户对书籍的基本增删改查功能。
 2. 进一步采用动态SQL实现书籍的按条件查询功能，并通过分页插件分页显示。
 3. 采用Redis缓存各查询结果，目录层级结构构建Redis键值。
 4. 实现书籍封面上传，上传成功后数据库存储图片相对路径，以便前端获取图片。


## 效果预览
![登录页面](https://github.com/NieWenX/BookManager/tree/master/BookManagerImg/login.png)


![首页](https://github.com/NieWenX/BookManager/tree/master/BookManagerImg/home.png)



![按条件查询书籍并分页显示](https://github.com/NieWenX/BookManager/tree/master/BookManagerImg/queryByCondition.png)


![上传图片](https://github.com/NieWenX/BookManager/tree/master/BookManagerImg/editAndUploadImg.png)


![修改账户密码或注销用户](https://github.com/NieWenX/BookManager/tree/master/BookManagerImg/editPassWord.png)






