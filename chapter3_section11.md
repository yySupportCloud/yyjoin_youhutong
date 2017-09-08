# 用户接口

对应SDK类：UserCenter  
*	根据用户ID获取用户信息  
基本信息

<table>
   <tr>
      <td>描述</td>
      <td>根据用户ID获取用户信息</td>
   </tr>
   <tr>
      <td>路径</td>
      <td>user/user?userId=id</td>
   </tr>
   <tr>
      <td>请求方法</td>
      <td>GET</td>
   </tr>
   <tr>
      <td>SDK方法</td>
      <td>public static String getUserById(String userId)</td>
   </tr>
</table>

请求参数

<table>
   <tr>
      <td>参数名称</td>
      <td>类型</td>
      <td>描述</td>
   </tr>
   <tr>
      <td>userId</td>
      <td>String</td>
      <td>用户ID</td>
   </tr>
</table>

返回值

<table>
   <tr>
      <td>字段</td>
      <td>类型</td>
      <td>描述</td>
   </tr>
   <tr>
      <td>status</td>
      <td>String</td>
      <td>请求的状态，如果为0，表示失败，如果为1，表示成功</td>
   </tr>
   <tr>
      <td>user</td>
      <td>UserVO</td>
      <td>用户基本信息</td>
   </tr>
 
</table>

<table>
   <tr>
      <td>字段</td>
      <td>类型</td>
      <td>描述</td>
      <td>示例</td>
   </tr>
   <tr>
      <td>registerDate</td>
      <td>String</td>
      <td>注册日期</td>
      <td>2016-03-09 16:06:23</td>
   </tr>
   <tr>
      <td>sysId</td>
      <td>String</td>
      <td>系统ID，由哪个应用添加的</td>
      <td> </td>
   </tr>
   <tr>
      <td> </td>
      <td> </td>
      <td> </td>
      <td> </td>
   </tr>
   <tr>
      <td>userCode</td>
      <td>String</td>
      <td>编码</td>
      <td>yht</td>
   </tr>
   <tr>
      <td>userEmail</td>
      <td>String</td>
      <td>邮箱</td>
      <td>yht@yonyou.com</td>
   </tr>
   <tr>
      <td></td>
   </tr>
   <tr>
      <td>userId</td>
      <td>String</td>
      <td>用户主键</td>
      <td>8eabf6af-c08c-49e7-8e26-8b04f9fb1917</td>
   </tr>
   <tr>
      <td>userMobile</td>
      <td>String</td>
      <td>手机</td>
      <td>15100000000</td>
   </tr>
   <tr>
      <td>userName</td>
      <td>String</td>
      <td>用户昵称</td>
      <td>友户通</td>
   </tr>
   <tr>
      <td> </td>
      <td> </td>
      <td> </td>
      <td> </td>
   </tr>
   <tr>
      <td>need_merge</td>
      <td>int</td>
      <td>0，不需要合并；1，需要合并</td>
      <td>0</td>
   </tr>
   <tr>
      <td>sex</td>
      <td> </td>
      <td> </td>
      <td>0</td>
   </tr>
   
</table>
  
UserVO对象字段说明   
*	根据用户ID数组获取用户信息  
基本信息

<table>
   <tr>
      <td>描述</td>
      <td>根据用户ID获取用户信息</td>
   </tr>
   <tr>
      <td>路径</td>
      <td>/user/getusersbypks</td>
   </tr>
   <tr>
      <td>请求方法</td>
      <td>POST</td>
   </tr>
   <tr>
      <td>SDK方法</td>
      <td>public static String getUserByPks(String[] pks)</td>
   </tr>
</table>

请求参数

<table>
   <tr>
      <td>参数名称</td>
      <td>类型</td>
      <td>描述</td>
   </tr>
   <tr>
      <td>pks</td>
      <td>String[]</td>
      <td>用户ID数组</td>
   </tr>
</table>

{"pks":["2c1afdf0-4a47-4b03-8d40-defaa65b9943","604821"],"sysid":"","secretKey":""}  
注：明文手机号需要secretKey  
返回值

<table>
   <tr>
      <td>字段</td>
      <td>类型</td>
      <td>描述</td>
   </tr>
   <tr>
      <td>status</td>
      <td>String</td>
      <td>请求的状态，如果为0，表示失败，如果为1，表示成功</td>
   </tr>
   <tr>
      <td>user</td>
      <td>UserVO</td>
      <td>用户基本信息</td>
   </tr>
</table>

    {
    "status" : 1,
    "users" : [ {
    "account" : "",
    "lang" : "",
    "loginType" : "YHTSYSID",
    "mailValidatect" : 3,
    "outDate" : "2017-05-15 15:30:33.56",
    "registerDate" : "2017-04-14 11:31:11",
    "secretKey" : "964f5b80-a764-42c0-999a-5d17abbc8d1b",
    "status" : 0,
    "timeZone" : "",
    "userAvator" : "",
    "userCode" : "13811394465",
    "userEmail" : "tan*****.com",
    "userId" : "f2a2314a-1fdd-41e3-9119-4b2e8bb63ca5",
    "userMobile" : "138****4465",
    "userName" : "13811394465"
    } ]
    }

*	根据用户id数组和用户名称查找用户  
基本信息

<table>
   <tr>
      <td>描述</td>
      <td>根据用户id数组和用户名称查找用户，可模糊查询，默认分页，每页20条</td>
   </tr>
   <tr>
      <td>路径</td>
      <td>user/userspage</td>
   </tr>
   <tr>
      <td>请求方法</td>
      <td>GET</td>
   </tr>
   <tr>
      <td>SDK方法</td>
      <td>public static String searchUser(String[] pks, String userName)</td>
   </tr>
</table>

请求参数

<table>
   <tr>
      <td>参数名称</td>
      <td>类型</td>
      <td>描述</td>
   </tr>
   <tr>
      <td>pks</td>
      <td>String[]</td>
      <td>用户id数组</td>
   </tr>
   <tr>
      <td>userName</td>
      <td>String</td>
      <td>用户名称</td>
   </tr>
</table>

返回值

<table>
   <tr>
      <td>字段</td>
      <td>类型</td>
      <td>描述</td>
   </tr>
   <tr>
      <td>status</td>
      <td>String</td>
      <td>请求的状态，如果为0，表示失败，如果为1，表示成功</td>
   </tr>
   <tr>
      <td>user</td>
      <td>UserVO</td>
      <td>用户基本信息</td>
   </tr>
</table>

user字段（JSONObject）key值说明

<table>
   <tr>
      <td>Key</td>
      <td>类型</td>
      <td>描述</td>
   </tr>
   <tr>
      <td>number</td>
      <td>int</td>
      <td>当前页码</td>
   </tr>
   <tr>
      <td>totalpages</td>
      <td>int</td>
      <td>总页数</td>
   </tr>
   <tr>
      <td>content</td>
      <td>List<TenantUser></td>
      <td>user列表</td>
   </tr>
   <tr>
      <td>totalElements</td>
      <td>int</td>
      <td>元素总个数</td>
   </tr>
   <tr>
      <td>sort</td>
      <td>JSONObject</td>
      <td>分页排序方式</td>
   </tr>
   <tr>
      <td>first</td>
      <td>boolean</td>
      <td>第一个元素是否在当前页</td>
   </tr>
   <tr>
      <td>firstpage</td>
      <td>boolean</td>
      <td>是否是第一页</td>
   </tr>
   <tr>
      <td>last</td>
      <td>boolean</td>
      <td>最后一个元素是否在当前页</td>
   </tr>
   <tr>
      <td>lastpage</td>
      <td>boolean</td>
      <td>是否是最后一页</td>
   </tr>
   <tr>
      <td>numberOfElements</td>
      <td>int</td>
      <td>当前页的元素个数</td>
   </tr>
   <tr>
      <td>size</td>
      <td>int</td>
      <td>页面的大小</td>
   </tr>
</table>

key值中sort（JSONObject）key值说明

<table>
   <tr>
      <td>Key</td>
      <td>类型</td>
      <td>描述</td>
   </tr>
   <tr>
      <td>nullHandling</td>
      <td>NullHandling</td>
      <td>处理nulls的方式</td>
   </tr>
   <tr>
      <td>ignoreCase</td>
      <td>boolean</td>
      <td>排序是否区分大小写</td>
   </tr>
   <tr>
      <td>property</td>
      <td>String</td>
      <td>用于排序的属性</td>
   </tr>
   <tr>
      <td>ascending</td>
      <td>boolean</td>
      <td>是否为升序排序方式</td>
   </tr>
   <tr>
      <td>direction</td>
      <td>Direction</td>
      <td>排序方式</td>
   </tr>
</table>

*	增加用户  
基本信息

<table>
   <tr>
      <td>描述</td>
      <td>增加用户，如果手机号和邮箱已存在于友户通中，将会返回相应的用户信息</td>
   </tr>
   <tr>
      <td>路径</td>
      <td>user/user</td>
   </tr>
   <tr>
      <td>请求方法</td>
      <td>POST</td>
   </tr>
   <tr>
      <td>SDK方法</td>
      <td>public staticString addUser(Map<String, String> params)</td>
   </tr>
</table>

请求参数

<table>
   <tr>
      <td>参数名称</td>
      <td>类型</td>
      <td>描述</td>
   </tr>
   <tr>
      <td> </td>
      <td>UserVO</td>
      <td>用户信息，必有的值userCode,userName,userMile或者userEmail；可选userPassword，密码可不传，不传的话会被设置为默认密码；需要传systId,应用标识。</td>
   </tr>
</table>

body:  
userCode=
tanyh1&userMobile=13811394460&userPassword=tanyh*123&userName=tanyh  
 返回值

<table>
   <tr>
      <td>字段</td>
      <td>类型</td>
      <td>描述</td>
   </tr>
   <tr>
      <td>status</td>
      <td>String</td>
      <td>请求的状态，如果为0，表示失败，如果为1，表示成功</td>
   </tr>
   <tr>
      <td>user</td>
      <td>UserVO</td>
      <td>用户基本信息</td>
   </tr>
</table>


手机已存在返回示例：   

{   
"status" : 0,  
"msg" : "18909090909 手机号已存在",  
"code" : "900010000200008",  
"user" : {  
"account" : "",  
"lang" : "",  
"loginType" : "YHTSYSID",  
"mailValidatect" : 0,  
"needMerge" : false,  
"outDate" : "",  
"registerDate" : "2017-06-23 13:45:14",  
"registerSource" : "",  
"status" : 0,  
"timeZone" : "",  
"userActivate" : true,  
"userAvator" : "",  
"userAvatorNew" : "",  
"userCode" : "s2323@zblzbl",  
"userEmail" : "s23XXXX@qq.com",  
"userId" : "10b460e6-c924-4aa9-8ec1-8ff654a98048",  
"userMobile" : "189XXXX0909",  
"userName" : "s2323@zblzbl",  
"validateEmail" : false,  
"validateMobile" : false,  
"verified" : false  
}  
}  

邮箱已存在示例：  

{  
"status" : 0,  
"msg" : "s2323@qq.com 邮箱已存在",  
"code" : "900010000200009",  
"user" : {  
"userAvatorNew" : "",  
"loginType" : "YHTSYSID",  
"userCode" : "s2323@zblzbl",  
"registerSource" : "",  
"validateMobile" : false,  
"userMobile" : "189XXXX0909",  
"userActivate" : true,  
"userEmail" : "s23XXXX@qq.com",  
"lang" : "",  
"registerDate" : "2017-06-23 13:45:14",  
"outDate" : "",  
"needMerge" : false,  
"verified" : false,  
"timeZone" : "",  
"userName" : "s2323@zblzbl",  
"userId" : "10b460e6-c924-4aa9-8ec1-8ff654a98048",  
"validateEmail" : false,  
"userAvator" : "",  
"mailValidatect" : 0,  
"account" : "",  
"status" : 0  
}  
}  

userCode已存在  

{
"status" : 0,  
"msg" : "yy_6285382275127313409am1ym1 用户帐号已经存在",  
"code" : "900010000200007",  
"user" : {  
"account" : "",   
"lang" : "",  
"loginType" : "YHTSYSID",  
"mailValidatect" : 0,  
"needMerge" : false,  
"outDate" : "",  
"registerDate" : "2017-06-27 20:13:45",  
"registerSource" : "",  
"status" : 0,  
"timeZone" : "",  
"userActivate" : true,  
"userAvator" : "",  
"userAvatorNew" : "",  
"userCode" : "yy_6285382275127313409am1ym1",  
"userEmail" : "wkpw******@upesn.com",  
"userId" : "7d17b12f-7e36-4c62-998d-e30bdc383064",  
"userMobile" : "175****7581",  
"userName" : "吴正军",  
"validateEmail" : false,  
"validateMobile" : false,  
"verified" : false  
}
}

*	批量增加用户  
基本信息  

<table>
   <tr>
      <td>描述</td>
      <td>批量增加用户（最多50个）</td>
   </tr>
   <tr>
      <td>路径</td>
      <td>user/users</td>
   </tr>
   <tr>
      <td>请求方法</td>
      <td>POST</td>
   </tr>
   <tr>
      <td>SDK方法</td>
      <td>public staticString addUsers(String systemCode, String jsonStr)</td>
   </tr>
</table>

请求参数

<table>
   <tr>
      <td>参数名称</td>
      <td>类型</td>
      <td>描述</td>
   </tr>
   <tr>
      <td>sysId</td>
      <td>String</td>
      <td>系统编码，表示是属于那个应用的用户（例如：ipu，hr_cloud）</td>
   </tr>
   <tr>
      <td>jsonStr</td>
      <td>UserVO</td>
      <td>用户信息，必有的值userCode,userName,userMile或者userEmail；可选userPassword，密码可不传，不传的话会被设置为默认密码；需要传systId,应用标识。</td>
   </tr>
</table>

body:  

{"users":[{"userCode":"ptest1","userPassword":"tanyh*123","userMobile":"13412343431","userName":"[0xe6][0xb5][0x8b][0xe8][0xaf][0x95][0xe7][0x94][0xa8][0xe6][0x88][0xb7]p1","userEmail":"ptest1@yonyou.com"},{"userCode":"ptest2","userMobile":"13412343432","userName":"[0xe6][0xb5][0x8b][0xe8][0xaf][0x95][0xe7][0x94][0xa8][0xe6][0x88][0xb7]p2","userEmail":"ptest2@yonyou.com"}],"sysId":"ipu"}

*	获取图形验证码  
基本信息 

<table>
   <tr>
      <td>描述</td>
      <td>获取图形验证码</td>
   </tr>
   <tr>
      <td>路径</td>
      <td>images/getValiImage?ts=1495615240000</td>
   </tr>
   <tr>
      <td>请求方法</td>
      <td>Get</td>
   </tr>
</table>

ts是图形验证码的key，一般使用时间，校验时ts的值要作为key的值传递到校验图形验证码的接口中。   
 返回值  
图片，可放到img的src里  
*	非用户发送手机或邮箱验证码  
基本信息

<table>
   <tr>
      <td>描述</td>
      <td>非用户发送手机或邮箱验证码，供注册用户使用</td>
   </tr>
   <tr>
      <td>路径</td>
      <td>/user/sendcode2（url里不能带rest）</td>
   </tr>
   <tr>
      <td>请求方法</td>
      <td>POST</td>
   </tr>
   <tr>
      <td>SDK方法</td>
      <td>sendcode(String contact, String type, String key, String code)</td>
   </tr>
</table>

请求参数

<table>
   <tr>
      <td>userId</td>
      <td>String</td>
      <td>用户id(可不传递)</td>
   </tr>
   <tr>
      <td>type</td>
      <td>String</td>
      <td>mobile 或者email</td>
   </tr>
   <tr>
      <td>key</td>
      <td>Striing</td>
      <td>图形验证码的key</td>
   </tr>
   <tr>
      <td>code</td>
      <td>String</td>
      <td>图形验证码的值</td>
   </tr>
   <tr>
      <td>mobile</td>
      <td>boolean</td>
      <td>手机号，type为mobile时有效</td>
   </tr>
   <tr>
      <td>email</td>
      <td>boolean</td>
      <td>邮箱，type为email时有效</td>
   </tr>
</table>

SDK方法：  
sendcode(String contact, String type, String key, String code) 
{"contact":"13856545851","type":"mobile","code":"123389","key":"1495615240000"}  
或者  
{"contact":"mymail@yonyou.com","type":"email","code":"123389","key":"1495615240000"}  
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
      <td>msg</td>
      <td>String</td>
      <td>更新结果</td>
   </tr>
</table>

{"status" : 1,"msg" : "短信发送成功"}  
*	给已有用户发送手机或邮箱验证码  
基本信息

<table>
   <tr>
      <td>描述</td>
      <td>给已有用户发送手机或邮箱验证码</td>
   </tr>
   <tr>
      <td>供修改密码、重置密码等获取sid时验证用户使用</td>
   </tr>
   <tr>
      <td>路径</td>
      <td>/user/sendcode</td>
   </tr>
   <tr>
      <td>请求方法</td>
      <td>POST</td>
   </tr>
</table>

请求参数

<table>
   <tr>
      <td>参数名称</td>
      <td>类型</td>
      <td>描述</td>
   </tr>
   <tr>
      <td>type</td>
      <td>String</td>
      <td>mobile 或者email</td>
   </tr>
   <tr>
      <td>userId</td>
      <td>String</td>
      <td>用户ID</td>
   </tr>
   <tr>
      <td>sysid</td>
      <td>String</td>
      <td>应用ID</td>
   </tr>
</table>

SDK方法：  
public static String sendPhoneMessage(String userId)  
public static String sendEmailMessage(String userId)  
public static String sendValidateCode(String userId, String type)   
Body  
{"userId":"f2a2314a-1fdd-41e3-9119-4b2e8bb63ca5","type":"email","sysid":"yht"}  
或者  
{"userId":"f2a2314a-1fdd-41e3-9119-4b2e8bb63ca5","type":"mobile","sysid":"yht"}  
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
      <td>msg</td>
      <td>String</td>
      <td>更新结果</td>
   </tr>
</table>

{"status" : 1,"msg" : "短信发送成功"}

*	验证手机验证码  
基本信息

<table>
   <tr>
      <td>描述</td>
      <td>增加用户</td>
   </tr>
   <tr>
      <td>路径</td>
      <td>user/validatecode</td>
   </tr>
   <tr>
      <td>请求方法</td>
      <td>POST</td>
   </tr>
   <tr>
      <td>SDK方法</td>
      <td>validateCode(String type, String userId, String code, String contact)</td>
   </tr>
</table>

请求参数

<table>
   <tr>
      <td>参数名称</td>
      <td>类型</td>
      <td>描述</td>
   </tr>
   <tr>
      <td>type</td>
      <td>String</td>
      <td>mobile或者email</td>
   </tr>
   <tr>
      <td>userId</td>
      <td>String</td>
      <td>用户ID</td>
   </tr>
   <tr>
      <td>code</td>
      <td>String</td>
      <td>验证码</td>
   </tr>
   <tr>
      <td>contact</td>
      <td>String</td>
      <td>手机号或邮箱，userId为空时生效</td>
   </tr>
</table>

SDK方法：  
public static String validatePhoneMessage(String userId,String message);  
public static String validateEmailMessage(String userId,String message);  
public static String validateCode(String type, String userId, String code, String contact);  
 body  
{"userId":"f2a2314a-1fdd-41e3-9119-4b2e8bb63ca5","type":"mobile","code":"849818"}  
或者  
{"contact":"13811452269","type":"mobile","code":"849818"}  
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
      <td>sid</td>
      <td>String</td>
      <td>后续做安全有关的sessionid，只能使用一次，只能针对相应的user进行安全接口调用，无userId</td>
   </tr>
</table>

{"status" : 1,"sid" : "5aa925958acd671d0323f97ff740a832"}

*	修改密码  
基本信息

<table>
   <tr>
      <td>描述</td>
      <td>增加用户</td>
   </tr>
   <tr>
      <td>路径</td>
      <td>user/modifypassword</td>
   </tr>
   <tr>
      <td>请求方法</td>
      <td>POST</td>
   </tr>
</table>

 请求参数
 
 <table>
   <tr>
      <td>userId</td>
      <td>String</td>
      <td>用户id</td>
   </tr>
   <tr>
      <td>shaPassword</td>
      <td>String</td>
      <td>旧密码的sha-1值</td>
   </tr>
   <tr>
      <td>md5Password</td>
      <td>Striing</td>
      <td>旧密码的md5值</td>
   </tr>
   <tr>
      <td>shaNewPassword</td>
      <td>String</td>
      <td>新密码的sha-1值</td>
   </tr>
   <tr>
      <td>md5NewPassword</td>
      <td>String</td>
      <td>新密码的md5值</td>
   </tr>
   <tr>
      <td>reset</td>
      <td>boolean</td>
      <td>是否是重置密码</td>
   </tr>
   <tr>
      <td>sid</td>
      <td>String</td>
      <td>验证码校验接口返回的sid（友户通接口-验证手机验证码）</td>
   </tr>
</table>

SDK方法：  
 修改密码  
 public static String modifyPassword(String userId, String shaPassword, String md5Password, String shaNewPassword, String md5NewPassword, String sid);
 
 重置密码  
 public static String resetPassword(String userId, String shaNewPassword, String md5NewPassword, String sid);
 
body  
{"userId":"f2a2314a-1fdd-41e3-9119-4b2e8bb63ca5","shaPassword":"66c9549482d98808b306dcf47f0b419c06271bb6","md5Password":"ddb5dae482528387954e1a3bc7af2ca3","shaNewPassword":"2cb67291738027c35b3e64eaf5ea8855c4da8cc5","md5NewPassword":"811e172171edeb860e09a87576b66297","reset":false,"sid":"fc1f6dc08e56ed8de3bd619beff560aa"}

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
      <td>msg</td>
      <td>String</td>
      <td>更新结果</td>
   </tr>
</table>

*	修改手机号或邮箱  
基本信息

<table>
   <tr>
      <td>描述</td>
      <td>修改手机号邮箱</td>
   </tr>
   <tr>
      <td>路径</td>
      <td>user/modifyContact</td>
   </tr>
   <tr>
      <td>请求方法</td>
      <td>POST</td>
   </tr>
</table>

请求参数

<table>
   <tr>
      <td>userId</td>
      <td>String</td>
      <td>用户id</td>
   </tr>
   <tr>
      <td>contact</td>
      <td>String</td>
      <td>手机号或邮箱</td>
   </tr>
   <tr>
      <td>sid</td>
      <td>String</td>
      <td>验证码校验接口返回的sid（友户通接口-验证手机验证码）</td>
   </tr>
</table>

SDK方法：  
 修改密码  
public static String modifyContact(String userId, String contact, String sid);

body  
{"userId":"f2a2314a-1fdd-41e3-9119-4b2e8bb63ca5","contact":"teest@yonyou.com","sid":"fc1f6dc08e56ed8de3bd619beff560aa"}

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
      <td>msg</td>
      <td>String</td>
      <td>更新结果</td>
   </tr>
</table>

*	绑定邮箱  
基本信息

<table>
   <tr>
      <td>描述</td>
      <td>增加用户</td>
   </tr>
   <tr>
      <td>路径</td>
      <td>user/bindMail</td>
   </tr>
   <tr>
      <td>请求方法</td>
      <td>POST</td>
   </tr>
</table>

请求参数

<table>
   <tr>
      <td>参数名称</td>
      <td>类型</td>
      <td>描述</td>
   </tr>
   <tr>
      <td>email</td>
      <td>String</td>
      <td>邮箱</td>
   </tr>
   <tr>
      <td>userId</td>
      <td>String</td>
      <td>用户ID</td>
   </tr>
</table>

Body:  
{"userId":"f2a2314a-1fdd-41e3-9119-4b2e8bb63ca5","email":"120437047@qq.com"}

返回值

<table>
   <tr>
      <td>字段</td>
      <td>类型</td>
      <td>描述</td>
   </tr>
   <tr>
      <td>status</td>
      <td>String</td>
      <td>请求的状态，如果为0，表示失败，如果为1，表示成功</td>
   </tr>
</table>

*	绑定手机  
 基本信息 

<table>
   <tr>
      <td>描述</td>
      <td>增加用户</td>
   </tr>
   <tr>
      <td>路径</td>
      <td>user/bindMobile</td>
   </tr>
   <tr>
      <td>请求方法</td>
      <td>POST</td>
   </tr>
</table>

请求参数

<table>
   <tr>
      <td>参数名称</td>
      <td>类型</td>
      <td>描述</td>
   </tr>
   <tr>
      <td>mobile</td>
      <td>String</td>
      <td>手机号</td>
   </tr>
   <tr>
      <td>userId</td>
      <td>String</td>
      <td>用户ID</td>
   </tr>
</table>

body:  
 {"userId":"f2a2314a-1fdd-41e3-9119-4b2e8bb63ca5","mobile":"13866544465"}
 
  返回值 

<table>
   <tr>
      <td>字段</td>
      <td>类型</td>
      <td>描述</td>
   </tr>
   <tr>
      <td>status</td>
      <td>String</td>
      <td>请求的状态，如果为0，表示失败，如果为1，表示成功</td>
   </tr>
</table>

*	登录校验  
基本信息

<table>
   <tr>
      <td>描述</td>
      <td>登录校验</td>
   </tr>
   <tr>
      <td>路径</td>
      <td>/cas/v1/validate</td>
   </tr>
   <tr>
      <td>请求方法</td>
      <td>POST</td>
   </tr>
   <tr>
      <td>SDK方法</td>
      <td>public static String verifyUser(String userName, String userPassword, String systemId)</td>
   </tr>
</table>

请求参数

<table>
   <tr>
      <td>参数名称</td>
      <td>类型</td>
      <td>描述</td>
   </tr>
   <tr>
      <td>userName</td>
      <td>String</td>
      <td>登录名</td>
   </tr>
   <tr>
      <td>md5Password</td>
      <td>String</td>
      <td>md5加密后的密码，并且用cas RSA公钥加密(如果传入norsa参数，则不用rsa加密）</td>
   </tr>
   <tr>
      <td>shaPassword</td>
      <td>String</td>
      <td>sha-1加密后的密码，并且用cas RSA公钥加密(如果传入norsa参数，则不用rsa加密）</td>
   </tr>
   <tr>
      <td>sysId</td>
      <td>String</td>
      <td>应用编码，标识应用的</td>
   </tr>
</table>

{"userName":"yhttest345","md5Password":"f5740c21c8472ae57c40884093c40739","shaPassword":"10f0064b104ead147c0d946aa03f2fa1945a2001","norsa":"norsa","sysId":"yht"}

  返回值
  
认证成功

<table>
   <tr>
      <td>字段</td>
      <td>类型</td>
      <td>描述</td>
   </tr>
   <tr>
      <td>status</td>
      <td>String</td>
      <td>请求的状态，为1，表示成功</td>
   </tr>
   <tr>
      <td>msg</td>
      <td>String</td>
      <td>认证信息，“认证成功”</td>
   </tr>
   <tr>
      <td>user</td>
      <td>UserVO</td>
      <td>用户信息</td>
   </tr>
</table>

认证失败

<table>
   <tr>
      <td>字段</td>
      <td>类型</td>
      <td>描述</td>
   </tr>
   <tr>
      <td>status</td>
      <td>String</td>
      <td>请求的状态，为0，表示失败</td>
   </tr>
   <tr>
      <td>msg</td>
      <td>String</td>
      <td>认证失败信息，如“用户名或密码错误”</td>
   </tr>
</table>

*	向用户手机发送消息  
基本信息

<table>
   <tr>
      <td>描述</td>
      <td>根据用户ID向该用户手机发送消息</td>
   </tr>
   <tr>
      <td>路径</td>
      <td>/user/ sendmsgbymobile</td>
   </tr>
   <tr>
      <td>请求方法</td>
      <td>POST</td>
   </tr>
   <tr>
      <td>SDK方法</td>
      <td>public static String sendMsgByMobile(String userId，String massage)</td>
   </tr>
</table>

请求参数

<table>
   <tr>
      <td>参数名称</td>
      <td>类型</td>
      <td>描述</td>
   </tr>
   <tr>
      <td>userId</td>
      <td>String</td>
      <td>用户ID</td>
   </tr>
   <tr>
      <td>massage</td>
      <td>String</td>
      <td>消息内容</td>
   </tr>
</table>

返回值

<table>
   <tr>
      <td>字段</td>
      <td>类型</td>
      <td>描述</td>
   </tr>
   <tr>
      <td>status</td>
      <td>String</td>
      <td>请求的状态，如果为0，表示失败，如果为1，表示成功</td>
   </tr>
   <tr>
      <td>msg</td>
      <td>String</td>
      <td>失败信息的描述；当status为1时，无meg字段</td>
   </tr>
</table>

*	向用户邮箱发送消息  
基本信息

<table>
   <tr>
      <td>描述</td>
      <td>根据用户ID向该用户邮箱发送消息</td>
   </tr>
   <tr>
      <td>路径</td>
      <td>/user/ sendmsgbyemail</td>
   </tr>
   <tr>
      <td>请求方法</td>
      <td>POST</td>
   </tr>
   <tr>
      <td>SDK方法</td>
      <td>public static String sendMsgByEmail(String userId，String massage)</td>
   </tr>
</table>

请求参数

<table>
   <tr>
      <td>参数名称</td>
      <td>类型</td>
      <td>描述</td>
   </tr>
   <tr>
      <td>userId</td>
      <td>String</td>
      <td>用户ID</td>
   </tr>
   <tr>
      <td>massage</td>
      <td>String</td>
      <td>消息内容</td>
   </tr>
</table>

返回值

<table>
   <tr>
      <td>字段</td>
      <td>类型</td>
      <td>描述</td>
   </tr>
   <tr>
      <td>status</td>
      <td>String</td>
      <td>请求的状态，如果为0，表示失败，如果为1，表示成功</td>
   </tr>
   <tr>
      <td>msg</td>
      <td>String</td>
      <td>失败信息的描述；当status为1时，无meg字段</td>
   </tr>
</table>


