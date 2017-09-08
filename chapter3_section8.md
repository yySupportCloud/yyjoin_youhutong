# OAuth2.0登录授权

**授权申请**  
申请Oauth2.txt授权文件，向友户通团队申请。需要给出回调地址。默认accesstoken 有效期是1个月，如果要更长，需要说明。申请的授权文件是oauth2.txt，在sdk.properties中添加一行 

    oauth2file.path=pathTo\\oauth2.txt

**授权码模式获取Token**  
请求会跳转到用户登录界面，要求输入用户名，密码，成功验证后，会把code放到回调地址上，通过302 redirect到服务器上。服务器端收到code后，根据code获取token。  
请求授权码服务：  
https://idtest.yyuap.com/cas/login?sysid=market&service=urlEncode[https://idtest.yyuap.com/cas/oauth/authorize?client_id=22&response_type=code&redirect_uri=urlEncode&scope=7&tid=333&state=wer

| 参数| 必须 | 解释 |
| -- | -- | -- |
| https://euc.yonyoucloud.com/cas/login | 是 | 表示cas登录地址|
| https://euc.yonyoucloud.com/cas/oauth/authorize|是 | AuthorizationCode地址|
|redirect_uri | 是 |用来指定登录成功后应用要返回的地址，用来获取code。注意这里的redirectUrl要和申请的Oauth2.txt文件中的redirectUrl匹配 |
| sysid | 是 | 分系统Id |
| client_id|是 | 分配给应用的appid。Oauth2.txt文件中的client_id |
| response_type=code |是 | 固定值 |
| Tid | 是 | 设备ID，用来区分唯一设置|
| State | 是| client端的状态值。用于第三方应用防止CSRF攻击，自定义的值。 |
| Scope | 否| 请求用户授权时向用户显示的可进行授权的列表。例如：scope=7 |

请求授权码服务：  
服务器端收到code后，可以调用UserCenter.getAccessTokenByCode(code)，获取token

**密码模式获取Token**  
密码方式获取token，就是通过Sdk方法调用获取，比较简单，这里要求用户把密码给应用，由应用来获取accessToken。  
UserCenter.createAccessToken(String sysId,String userName,String password,String clientId)

**手机验证码模式获取Token**  
UserCenter.createAccessTokenByValidateCode( String sysId,String userName, String validateCode ,String clientId) 

**使用Token**  
a）放到请求头中
格式为key: Authorization, value:Bearer accessToken，其中Authorization 和Beare为固定值，Bearer和accessToken之间用空格分开  
b）放到请求参数中  
参数key:accesstoken  
Value:token值

**刷新Token**  
刷新accessToken，当accessToken要超期时，可以使用refreshToken延长accessToken的时间。刷新后refreshToken变化，但是accessToken不变。方法UserCenter. refreshAccessToken(accessToken)。刷新后accesstoken生命延长一倍
 
**销毁Token**  
前端退出：  
http://servername?SAMLAccessToken=true&access_token=token&service=redirectUrl
也可以调用sdk退出：UserCenter. destroyAccessToken(String accessToken)

