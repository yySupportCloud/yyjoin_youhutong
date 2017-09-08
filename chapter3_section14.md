# 用户组接口

对应SDK类：UserGroupCenter  
*	添加用户组  
基本信息

<table>
   <tr>
      <td>描述</td>
      <td>添加用户组</td>
   </tr>
   <tr>
      <td>路径</td>
      <td>usergroup/add</td>
   </tr>
   <tr>
      <td>请求方法</td>
      <td>POST</td>
   </tr>
   <tr>
      <td>SDK方法</td>
      <td>public static String add(UserGroup userGroup)</td>
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
      <td>userGroup</td>
      <td>UserGroup</td>
      <td>用户组</td>
   </tr>
</table>

返回值

| 字段 | 类型 | 描述 |
| -- | -- | -- |
| status | string | 请求的状态，如果为0，表示失败，如果为1，表示成功 |
| msg | string | 当status为0时，返回失败信息的描述；当status为1时，返回userGroup       例如：   "usergroup": {  "sysId": "ipu",  "enterpriseId": "00107ad0-d331-4e88-aaa6-d7c106c76f35",  "groupId": "8eabf6af-c08c-49e7-8e26-8b04f9fb1917",  "groupName": "店小二组",  "para1": "组内的用户有店小二权限",  "para6": "20",  "registerDate": "2017-02-28 16:06:23"  }
 


*	更新用户组信息  
基本信息

<table>
   <tr>
      <td>描述</td>
      <td>更新用户组</td>
   </tr>
   <tr>
      <td>路径</td>
      <td>usergroup/update</td>
   </tr>
   <tr>
      <td>请求方法</td>
      <td>POST</td>
   </tr>
   <tr>
      <td>SDK方法</td>
      <td>public static String update( UserGroup userGroup)</td>
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
      <td>userGroup</td>
      <td>UserGroup</td>
      <td>用户分组实体</td>
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
      <td>更新成功或失败等提示消息</td>
   </tr>
</table>

 UserGroup对象字段说明
 
 <table>
   <tr>
      <td>字段</td>
      <td>类型</td>
      <td>描述</td>
      <td>示例</td>
   </tr>
   <tr>
      <td>sysId</td>
      <td>String</td>
      <td>所属分系统Id</td>
      <td> </td>
   </tr>
   <tr>
      <td>enterpriseId</td>
      <td>String</td>
      <td>所属企业Id</td>
      <td> </td>
   </tr>
   <tr>
      <td>groupId</td>
      <td>String</td>
      <td>用户组Id</td>
      <td> </td>
   </tr>
   <tr>
      <td>groupName</td>
      <td>String</td>
      <td>用户组名称</td>
      <td> </td>
   </tr>
   <tr>
      <td>para1</td>
      <td>String</td>
      <td>参数1，长度1000（预留字段）</td>
      <td> </td>
   </tr>
   <tr>
      <td>para2</td>
      <td>String</td>
      <td>参数2，长度1000（预留字段）</td>
      <td> </td>
   </tr>
   <tr>
      <td>Para3</td>
      <td>String</td>
      <td>参数3，长度100（预留字段）</td>
      <td> </td>
   </tr>
   <tr>
      <td>Para4</td>
      <td>String</td>
      <td>参数4，长度100（预留字段）</td>
      <td> </td>
   </tr>
   <tr>
      <td>Para5</td>
      <td>String</td>
      <td>参数5，长度100（预留字段）</td>
      <td> </td>
   </tr>
   <tr>
      <td>Para6</td>
      <td>Integer</td>
      <td>参数6（预留字段）</td>
      <td> </td>
   </tr>
   <tr>
      <td>Para7</td>
      <td>Integer</td>
      <td>参数7（预留字段）</td>
      <td> </td>
   </tr>
   <tr>
      <td>Para8</td>
      <td>Long</td>
      <td>参数8（预留字段）</td>
      <td> </td>
   </tr>
   <tr>
      <td>Para9</td>
      <td>Long</td>
      <td>参数9（预留字段）</td>
      <td> </td>
   </tr>
   <tr>
      <td>registerDate</td>
      <td>String</td>
      <td>注册时间</td>
      <td>2017-03-09 16:06:23</td>
   </tr>
</table>

*	删除用户组  
基本信息

<table>
   <tr>
      <td>描述</td>
      <td>删除用户组</td>
   </tr>
   <tr>
      <td>路径</td>
      <td>usergroup/ delete</td>
   </tr>
   <tr>
      <td>请求方法</td>
      <td>POST</td>
   </tr>
   <tr>
      <td>SDK方法</td>
      <td>public static String delete(String groupId)</td>
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
      <td>groupId</td>
      <td>String</td>
      <td>用户组ID</td>
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
      <td>失败信息的描述；当status为1时，无该字段</td>
   </tr>
</table>

*	根据用户组ID获取用户组信息  
基本信息

<table>
   <tr>
      <td>描述</td>
      <td>根据用户组ID获取用户组信息</td>
   </tr>
   <tr>
      <td>路径</td>
      <td>usergroup/get</td>
   </tr>
   <tr>
      <td>请求方法</td>
      <td>GET</td>
   </tr>
   <tr>
      <td>SDK方法</td>
      <td>public static String get(String groupId)</td>
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
      <td>groupId</td>
      <td>String</td>
      <td>用户组ID</td>
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
      <td>userGroup</td>
      <td>UserGroup</td>
      <td>用户组信息；当status为0时，无该字段</td>
   </tr>
   <tr>
      <td>msg</td>
      <td>String</td>
      <td>失败信息的描述；当status为1时，无该字段</td>
   </tr>
</table>

*	批量添加用户组  
基本信息

<table>
   <tr>
      <td>描述</td>
      <td>批量添加用户组</td>
   </tr>
   <tr>
      <td>路径</td>
      <td>usergroup/addusergroups</td>
   </tr>
   <tr>
      <td>请求方法</td>
      <td>POST</td>
   </tr>
   <tr>
      <td>SDK方法</td>
      <td>public static String addUserGroups(String jsonStr)</td>
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
      <td>jsonStr</td>
      <td>String</td>
      <td>由多个usergroup组成的json字符串(数量不超过50个)usergroup必有的值groupName</td>
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
      <td>当jsonStr中的usergroup为空时返回"没有用户组信息，无法批量添加用户组"，当jsonStr中usergroup数量超过50时，返回“用户组数量超过50”</td>
   </tr>
   <tr>
      <td>usergroups</td>
      <td>List<UserGroup></td>
      <td>添加成功的用户组</td>
   </tr>
   <tr>
      <td>errors</td>
      <td>List<String></td>
      <td>当有usergroup添加失败时，添加失败的usergroup分组的groupName到errors</td>
   </tr>
</table>

*	根据用户组ID和用户姓名获取用户信息  
基本信息

<table>
   <tr>
      <td>描述</td>
      <td>根据GroupId和UserName获取用户信息</td>
   </tr>
   <tr>
      <td>路径</td>
      <td>usergroup/searchuser</td>
   </tr>
   <tr>
      <td>请求方法</td>
      <td>GET</td>
   </tr>
   <tr>
      <td>SDK方法</td>
      <td>public static String searchUser(String groupId, String username)</td>
   </tr>
   <tr>
      <td></td>
      <td>public static String searchUser(String groupId, String userName, String pageNumber, String pageSize)</td>
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
      <td>groupId</td>
      <td>String</td>
      <td>用户分组的Id</td>
   </tr>
   <tr>
      <td>userName</td>
      <td>String</td>
      <td>用户的名字</td>
   </tr>
   <tr>
      <td>pageNumber</td>
      <td>String</td>
      <td>分页页码</td>
   </tr>
   <tr>
      <td>pageSize</td>
      <td>pageSize</td>
      <td>分页大小</td>
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
      <td>users</td>
      <td>JSONObject</td>
      <td>符合查找条件的user以及关于的分页的信息</td>
   </tr>
</table>

users字段key值说明：

<table>
   <tr>
      <td>字段</td>
      <td>类型</td>
      <td>描述</td>
   </tr>
   <tr>
      <td>number</td>
      <td>int</td>
      <td>当前所在的页数</td>
   </tr>
   <tr>
      <td>totalpages</td>
      <td>int</td>
      <td>总页数</td>
   </tr>
   <tr>
      <td>content</td>
      <td>List<TenantUser></td>
      <td>User列表</td>
   </tr>
   <tr>
      <td>totalElements</td>
      <td>int</td>
      <td>元素总个数</td>
   </tr>
   <tr>
      <td>sort</td>
      <td>JSONArray</td>
      <td>关于分页排序方式的json数组，nullHandling，property，ascending，direction等</td>
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
      <td>分页的大小</td>
   </tr>
</table>

*	根据用户组ID获取多用户信息  
基本信息

<table>
   <tr>
      <td>描述</td>
      <td>根据用户组ID获取多用户信息（分页查询，并提供重载）</td>
   </tr>
   <tr>
      <td>路径</td>
      <td>usergroup/listuser</td>
   </tr>
   <tr>
      <td>请求方法</td>
      <td>GET</td>
   </tr>
   <tr>
      <td>SDK方法</td>
      <td>public static String listUser(String groupId)</td>
   </tr>
   <tr>
      <td></td>
      <td>public static String listUser(String groupId, String pageNumber, String pageSize)</td>
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
      <td>groupId</td>
      <td>String</td>
      <td>用户组ID</td>
   </tr>
   <tr>
      <td>参数名称</td>
      <td>类型</td>
      <td>描述</td>
   </tr>
   <tr>
      <td>groupId</td>
      <td>String</td>
      <td>用户组ID</td>
   </tr>
   <tr>
      <td>pageNumber</td>
      <td>String</td>
      <td>页码</td>
   </tr>
   <tr>
      <td>pageSize</td>
      <td>String</td>
      <td>页面大小</td>
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
      <td>users</td>
      <td>JSONObject</td>
      <td>多用户页面信息（包括用户信息、分页信息、排序信息）</td>
   </tr>
</table>

 users字段（JSONObject）key值说明
 
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
      <td>User列表</td>
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

*	添加用户到用户组  
基本信息

<table>
   <tr>
      <td>描述</td>
      <td>添加用户到用户组</td>
   </tr>
   <tr>
      <td>路径</td>
      <td>usergroup/adduser2group</td>
   </tr>
   <tr>
      <td>请求方法</td>
      <td>POST</td>
   </tr>
   <tr>
      <td>SDK方法</td>
      <td>public static String addUser2Group(String groupId, String userId)</td>
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
      <td>groupId</td>
      <td>String</td>
      <td>用户组ID</td>
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
      <td>msg</td>
      <td>String</td>
      <td>失败信息的描述；当status为1时，无该字段</td>
   </tr>
</table>

*	从用户组中移除用户   
基本信息

<table>
   <tr>
      <td>描述</td>
      <td>从用户组中移除用户</td>
   </tr>
   <tr>
      <td>路径</td>
      <td>usergroup/removeuser</td>
   </tr>
   <tr>
      <td>请求方法</td>
      <td>POST</td>
   </tr>
   <tr>
      <td>SDK方法</td>
      <td>public static String removeUserFromGroup(String groupId, String userId)</td>
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
      <td>groupId</td>
      <td>String</td>
      <td>用户组ID</td>
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
      <td>msg</td>
      <td>String</td>
      <td>失败信息的描述；当status为1时，无该字段</td>
   </tr>
</table>

