# OAuth2接口

对应SDK类：UserCenter  
*	根据密码获取accesstoken  
基本信息

<table>
   <tr>
      <td>描述</td>
      <td>获取accesstoken</td>
   </tr>
   <tr>
      <td>路径</td>
      <td>/oauth/token</td>
   </tr>
   <tr>
      <td>请求方法</td>
      <td>POST</td>
   </tr>
</table>

请求参数 

<table>
   <tr>
      <td>sys</td>
      <td>String</td>
      <td>sysid</td>
   </tr>
   <tr>
      <td>clientId</td>
      <td>String</td>
      <td>客户端id</td>
   </tr>
   <tr>
      <td>username</td>
      <td>String</td>
      <td>用户名</td>
   </tr>
   <tr>
      <td>md5password</td>
      <td>String</td>
      <td>md5密码</td>
   </tr>
   <tr>
      <td>shapassword</td>
      <td>String</td>
      <td>sha密码</td>
   </tr>
</table>

SDK方法：  
 public static String createAccessToken( String sysId,String userName, String md5Password,String shaPassword ,String clientId)
 
body  	
{"sysid": "aaaa","username": "test","client_id": "23","md5password": "test","shapassword": "test"}  
 返回值
 
 <table>
   <tr>
      <td>字段</td>
      <td>类型</td>
      <td>描述</td>
   </tr>
   <tr>
      <td>status</td>
      <td>int</td>
      <td>请求的状态，如果为0，表示失败，如果为1，表示成功</td>
   </tr>
   <tr>
      <td>result</td>
      <td>String</td>
      <td>{"accessToken":"f2a2314a-1fdd-41e3-9119-4b2e8bb63ca5","refreshToken":"f2a2314a-1fdd-41e3-9119-4b2e8bb63ca5","expires_in":"86400"}</td>
   </tr>
</table>

*	根据验证码获取accesstoken  
基本信息

<table>
   <tr>
      <td>描述</td>
      <td>根据sysId，用户名，验证码accesstoken</td>
   </tr>
   <tr>
      <td>路径</td>
      <td>/oauth/token</td>
   </tr>
   <tr>
      <td>请求方法</td>
      <td>POST</td>
   </tr>
</table>

请求参数

<table>
   <tr>
      <td> sysid</td>
      <td>String</td>
      <td>sysid</td>
   </tr>
   <tr>
      <td>clientId</td>
      <td>String</td>
      <td>客户端id</td>
   </tr>
   <tr>
      <td>username</td>
      <td>String</td>
      <td>用户名</td>
   </tr>
   <tr>
      <td>validateCode</td>
      <td>String</td>
      <td>验证码</td>
   </tr>
</table>

SDK方法：   
  public static String createAccessTokenByValidateCode( String sysId,String userName, String validateCode ,String clientId)
  
body  
{"sysid": "aaaa","username": "test","client_id": "23","validateCode ": "2233"}

 返回值

<table>
   <tr>
      <td>字段</td>
      <td>类型</td>
      <td>描述</td>
   </tr>
   <tr>
      <td>status</td>
      <td>int</td>
      <td>请求的状态，如果为0，表示失败，如果为1，表示成功</td>
   </tr>
   <tr>
      <td>result</td>
      <td>String</td>
      <td>{"accessToken":"f2a2314a-1fdd-41e3-9119-4b2e8bb63ca5","refreshToken":"f2a2314a-1fdd-41e3-9119-4b2e8bb63ca5","expires_in":"86400"}</td>
   </tr>
</table>

*	验证accesstoken  
基本信息

<table>
   <tr>
      <td>描述</td>
      <td>验证accesstoken</td>
   </tr>
   <tr>
      <td>路径</td>
      <td>/user/checkOauthToken</td>
   </tr>
   <tr>
      <td>请求方法</td>
      <td>POST</td>
   </tr>
</table>

请求参数

<table>
   <tr>
      <td>access_token</td>
      <td>String</td>
      <td>accesstoken</td>
   </tr>
</table>

SDK方法：   
public static String checkOauthToken(String accessToken)  

body  
{"accessToken":"f2a2314a-1fdd-41e3-9119-4b2e8bb63ca5"}   

返回值

<table>
   <tr>
      <td>字段</td>
      <td>类型</td>
      <td>描述</td>
   </tr>
   <tr>
      <td>status</td>
      <td>int</td>
      <td>请求的状态，如果为0，表示失败，如果为1，表示成功</td>
   </tr>
   <tr>
      <td>result</td>
      <td>String</td>
      <td>accessToken校验结果</td>
   </tr>
</table>

*	根据accesstoken获取用户信息  
基本信息

<table>
   <tr>
      <td>描述</td>
      <td>根据accesstoken获取用户信息</td>
   </tr>
   <tr>
      <td>路径</td>
      <td>/user/getUserByToken</td>
   </tr>
   <tr>
      <td>请求方法</td>
      <td>POST</td>
   </tr>
</table>

请求参数

<table>
   <tr>
      <td>access_token</td>
      <td>String</td>
      <td>accesstoken</td>
   </tr>
</table>

SDK方法：   
public static String getUserByToken(String accessToken)

body  
{"accessToken":"f2a2314a-1fdd-41e3-9119-4b2e8bb63ca5"} 

返回值

<table>
   <tr>
      <td>字段</td>
      <td>类型</td>
      <td>描述</td>
   </tr>
   <tr>
      <td>status</td>
      <td>int</td>
      <td>请求的状态，如果为0，表示失败，如果为1，表示成功</td>
   </tr>
   <tr>
      <td>user</td>
      <td>String</td>
      <td>用户信息</td>
   </tr>
</table>

*	销毁accesstoken  
基本信息

<table>
   <tr>
      <td>描述</td>
      <td>验证accesstoken</td>
   </tr>
   <tr>
      <td>路径</td>
      <td>/oauth/destoryToken</td>
   </tr>
   <tr>
      <td>请求方法</td>
      <td>POST</td>
   </tr>
</table>

请求参数

<table>
   <tr>
      <td>access_token</td>
      <td>String</td>
      <td>accesstoken</td>
   </tr>
</table>

SDK方法：  
 public static String destroyAccessToken(String accessToken)
 
body  
{"access_token":"f2a2314a-1fdd-41e3-9119-4b2e8bb63ca5"}

 返回值
 
 <table>
   <tr>
      <td>字段</td>
      <td>类型</td>
      <td>描述</td>
   </tr>
   <tr>
      <td>status</td>
      <td>int</td>
      <td>请求的状态，如果为0，表示失败，如果为1，表示成功</td>
   </tr>
   <tr>
      <td>result</td>
      <td>String</td>
      <td>accessToken销毁提示</td>
   </tr>
</table>

*	刷新accesstoken  
基本信息

<table>
   <tr>
      <td>描述</td>
      <td>刷新accesstoken</td>
   </tr>
   <tr>
      <td>路径</td>
      <td>/oauth/refreshAccessToken</td>
   </tr>
   <tr>
      <td>请求方法</td>
      <td>POST</td>
   </tr>
</table>

请求参数

<table>
   <tr>
      <td>refresh_token</td>
      <td>String</td>
      <td>accesstoken</td>
   </tr>
</table>

SDK方法：   
public static String refreshAccessToken(String refresh_token)

body  
{"refresh_token":"f2a2314a-1fdd-41e3-9119-4b2e8bb63ca5"} 

返回值

<table>
   <tr>
      <td>字段</td>
      <td>类型</td>
      <td>描述</td>
   </tr>
   <tr>
      <td>status</td>
      <td>int</td>
      <td>请求的状态，如果为0，表示失败，如果为1，表示成功</td>
   </tr>
   <tr>
      <td>result</td>
      <td>String</td>
      <td>{"accessToken":"f2a2314a-1fdd-41e3-9119-4b2e8bb63ca5","refreshToken":"f2a2314a-1fdd-41e3-9119-4b2e8bb63ca5","expires_in":"86400"}</td>
   </tr>
</table>

*	根据accesstoken获取临时token  
基本信息

<table>
   <tr>
      <td>描述</td>
      <td>根据accesstoken获取临时token</td>
   </tr>
   <tr>
      <td>路径</td>
      <td>/oauth/getTempToken</td>
   </tr>
   <tr>
      <td>请求方法</td>
      <td>POST</td>
   </tr>
</table>

请求参数

<table>
   <tr>
      <td>access_token</td>
      <td>String</td>
      <td>accesstoken</td>
   </tr>
</table>

SDK方法：  
 public static String genTokenByAccessToken(String accessToken)
 
body  
{"accessToken":"f2a2314a-1fdd-41e3-9119-4b2e8bb63ca5"}

 返回值

<table>
   <tr>
      <td>字段</td>
      <td>类型</td>
      <td>描述</td>
   </tr>
   <tr>
      <td>status</td>
      <td>int</td>
      <td>请求的状态，如果为0，表示失败，如果为1，表示成功</td>
   </tr>
   <tr>
      <td>result</td>
      <td>String</td>
      <td>token值</td>
   </tr>
</table>







