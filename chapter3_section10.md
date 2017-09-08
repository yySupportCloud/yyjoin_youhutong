# 页面服务

内嵌页面，业务系统可以采用采用<frame src=" " />标签嵌入友户通用户中心相关页面，必须单点登录登录成功。

<table>
   <tr>
      <td>页面</td>
      <td>地址（前缀：https://euc.yonyoucloud.com）</td>
   </tr>
   <tr>
      <td>用户信息</td>
      <td>/usercenter?iframe=iframe&iframePath=user</td>
   </tr>
   <tr>
      <td>账号安全</td>
      <td>/usercenter?iframe=iframe&iframePath=security</td>
   </tr>
   <tr>
      <td>修改密码</td>
      <td>/usercenter?iframe=iframe&iframePath=security&params=%7B%22state%22%3A%22pwd%22%7D</td>
   </tr>
   <tr>
      <td>修改邮箱</td>
      <td>/usercenter?iframe=iframe&iframePath=security&params=%7B%22state%22%3A%22email%22%7D</td>
   </tr>
   <tr>
      <td>修改手机</td>
      <td>/usercenter?iframe=iframe&iframePath=security&params=%7B%22state%22%3A%22mobile%22%7D</td>
   </tr>
   <tr>
      <td></td>
   </tr>
</table>

非内嵌页面，一般为跳转页面，需要添加参数embedMode=false，如修改邮箱页面地址为：
/usercenter?iframe=iframe&embedMode=false&iframePath=security&params=%7B%22state%22%3A%22email%22%7D
