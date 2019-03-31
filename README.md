**项目步骤**

+ 登录模块
  + 发送ajax请求，后台验证账号密码是否正确
  + 将账号密码存在session实现状态保持，session存在redis中
  + 使用wtf生成token，进行csrf跨站请求保护
+ 信息模块
  + 后端返回HTML模板
  + 经过浏览器渲染，展示界面
+ 新增模块
  + 填写好要新增的信息，发送ajax请求
  + 后端查询mysql数据库，判断新增的id是否已经存在
  + 如果已经存在，新增失败，反之成功
  + 刷新页面，进行展示
+ 编辑模块
  + 对已经存在的信息进行修改和删除，发送ajax请求以后，会对要修改的账号id进行判断，是否是要编辑的id
  + 如果不是进行返回，反之刷新页面，进行展示
+ 删除模块
  + 要求输入要删除的id
  + 后端进行判断
  + 如果一致，进行删除，刷新界面，进行展示，反之，删除失败
+ 密码修改
  + 获取旧密码和新密码，发送ajax请求
  + 将旧密码进行判断，看是否正确
  + 如果正确进行更新，反之报错
+ 退出模块
  + 清除session中的账号密码，重定向到登录界面，刷新界面
  + 如果不退出下次登录将会重定向直接进入到管理界面
+ 部署
  + 使用Nginx作为代理服务器，处理前端发过来的请求
  + Gnuicorn处理Nginx发过来的动态请求





