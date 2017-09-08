# 注销

应用注销时，可在浏览器端直接发送logout请求，URL为 servername/logout?SAMLRequest=true&service=servername，友户通的Filter会处理这个请求，直接注销。  

要注意对应用自身的会话的处理。在注销时需要同步注销应用自身的会话和友户通的会话，否则会出现会话状态不一致的情况。友户通会话的注销方式为CasClientUtils.destroyToken，此方法将会删除Filter设置的会话存储内容，并返回一个url（向CAS发起全局注销的URL），应用需要重定向此url（处理完应用自己的注销逻辑后重定向）。应用可以通过增加Filter的方法来实现此过程，当其他应用退出时，也会发出注销请求，以达到能够单点注销的功能；这个Filter需要拦截处理如下的URL请求： 

| 请求方式 | post |
| -- | -- |
| url |https://www.myappdemo.com |
| body | logoutRequest=<samlp:LogoutRequest xmlns:samlp="urn:oasis:names:tc:SAML:2.0:protocol" ID="LR-3-afX79HEaAiPfrTCc0C2weJMJQQtbrUJH7cw" Version="2.0" IssueInstant="2017-03-23T15:01:47Z"><saml:NameID xmlns:saml="urn:oasis:names:tc:SAML:2.0:assertion">@NOT_USED@</saml:NameID><samlp:SessionIndex>ST-3-WGhgPbSQVVs9JGK53yao-cas01.example.org</samlp:SessionIndex><samlp:UserId>e765d88c-a01b-4eeb-b5c6-8247876cbd86</samlp:UserId></samlp:LogoutRequest> |

更为简单的方法是，直接通过继承ProxyReceivingTicketValidationFilter，实现钩子方法完成。

| protected void saveLoginInfo(String ticket, Assertion assertion,HttpServletRequest request, HttpServletResponse response) | 登录时记录ticket和session的关系 |
| -- | -- |
| protected void frontLogout(HttpServletRequest request,HttpServletResponse response) | 前端退出（用来应用在前端调用退出时使用） |
|protected void backLogout(String ticket)| 后端退出，其中ticket对应一次登录，在saveLoginInfo中记录，这里用来拿存放的信息退出|



