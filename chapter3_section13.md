# 用户标签接口

对应SDK类：UserCenter  
*	根据用户ID获取用户标签  
基本信息

<table>
   <tr>
      <td>描述</td>
      <td>根据用户ID获取用户标签</td>
   </tr>
   <tr>
      <td>路径</td>
      <td>/tag/gettags</td>
   </tr>
   <tr>
      <td>请求方法</td>
      <td>GET</td>
   </tr>
   <tr>
      <td>SDK方法</td>
      <td>public static String getTags(String userId)</td>
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
      <td>tags</td>
      <td>List<String></td>
      <td>多个用户标签</td>
   </tr>
   <tr>
      <td>flag</td>
      <td>int</td>
      <td>标签设置是否成功的标志，当status为0时，无flag字段；当status=1时，flag为0表示标签获取失败，flag为1表示标签获取成功</td>
   </tr>
   <tr>
      <td>msg</td>
      <td>String</td>
      <td>失败信息的描述；当status为1且flag为1时，无meg字段</td>
   </tr>
</table>

UserTag对象字段说明

<table>
   <tr>
      <td>字段</td>
      <td>类型</td>
      <td>描述</td>
      <td>示例</td>
   </tr>
   <tr>
      <td>id</td>
      <td>String</td>
      <td>标签ID</td>
      <td>d9fafbc6-9b53-40b1-985f-15ee778621ad</td>
   </tr>
   <tr>
      <td>userId</td>
      <td>String</td>
      <td>用户ID</td>
      <td>778309f8-e50c-4222-84ee-02be687dcc2b</td>
   </tr>
   <tr>
      <td>tag</td>
      <td>String</td>
      <td>用户标签</td>
      <td>cool，beautiful</td>
   </tr>
</table>

*	根据标签获取用户ID  
基本信息

<table>
   <tr>
      <td>描述</td>
      <td>根据标签获取用户ID（分页查询，并提供重载）</td>
   </tr>
   <tr>
      <td>路径</td>
      <td>/tag/getuserids</td>
   </tr>
   <tr>
      <td>请求方法</td>
      <td>GET</td>
   </tr>
   <tr>
      <td>SDK方法</td>
      <td>public static String getUserIdsByTag(String tag)；</td>
   </tr>
   <tr>
      <td></td>
      <td>public static String getUserIdsByTag(String tag, String pageSize, String pageNumber)</td>
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
      <td>tag</td>
      <td>String</td>
      <td>标签</td>
   </tr>
   <tr>
      <td>参数名称</td>
      <td>类型</td>
      <td>描述</td>
   </tr>
   <tr>
      <td>tag</td>
      <td>String</td>
      <td>标签</td>
   </tr>
   <tr>
      <td>pageSize</td>
      <td>String</td>
      <td>页面大小</td>
   </tr>
   <tr>
      <td>pageNumber</td>
      <td>String</td>
      <td>第几页</td>
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
      <td>userIds</td>
      <td>JSONObject</td>
      <td>多用户ID页面信息（包括多个用户ID、分页信息、排序信息）</td>
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
      <td>List<String></td>
      <td>userId列表</td>
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

*	判断用户是否存在某个标签  
基本信息

<table>
   <tr>
      <td>描述</td>
      <td>判断用户是否存在某个标签</td>
   </tr>
   <tr>
      <td>路径</td>
      <td>/tag/ istagexist</td>
   </tr>
   <tr>
      <td>请求方法</td>
      <td>GET</td>
   </tr>
   <tr>
      <td>SDK方法</td>
      <td>public static String isTagExist(String userId，String tag)</td>
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
      <td>tag</td>
      <td>String</td>
      <td>标签</td>
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
      <td>flag</td>
      <td>int</td>
      <td>表示是否存在，存在返回1，如果不存在返回0</td>
   </tr>
   <tr>
      <td>msg</td>
      <td>String</td>
      <td>失败信息的描述；当status为1时，无meg字段</td>
   </tr>
</table>

*	为用户设置标签  
基本信息

<table>
   <tr>
      <td>描述</td>
      <td>为用户设置标签</td>
   </tr>
   <tr>
      <td>路径</td>
      <td>/tag/ settag</td>
   </tr>
   <tr>
      <td>请求方法</td>
      <td>POST</td>
   </tr>
   <tr>
      <td>SDK方法</td>
      <td>public static String setTag(String userId，String tag)</td>
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
      <td>tag</td>
      <td>String</td>
      <td>标签</td>
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
      <td>flag</td>
      <td>int</td>
      <td>标签设置是否成功的标志，当status为0时，无flag字段；当status=1时，flag为0表示标签设置失败，flag为1表示标签设置成功</td>
   </tr>
   <tr>
      <td>msg</td>
      <td>String</td>
      <td>失败信息的描述；当status为1且flag为1时，无meg字段</td>
   </tr>
</table>

*	移除用户标签  
基本信息

<table>
   <tr>
      <td>描述</td>
      <td>移除用户标签</td>
   </tr>
   <tr>
      <td>路径</td>
      <td>/tag/ deletetag</td>
   </tr>
   <tr>
      <td>请求方法</td>
      <td>POST</td>
   </tr>
   <tr>
      <td>SDK方法</td>
      <td>public static String removeTag(String userId，String tag)</td>
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
      <td>tag</td>
      <td>String</td>
      <td>标签</td>
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
      <td>flag</td>
      <td>int</td>
      <td>标签移除是否成功的标志，当status为0时，无flag字段；当status=1时，flag为0表示标签设置失败，flag为1表示标签设置成功</td>
   </tr>
   <tr>
      <td>msg</td>
      <td>String</td>
      <td>失败信息的描述；当status为1且flag为1时，无meg字段</td>
   </tr>
</table>

*	修改用户标签  
基本信息

<table>
   <tr>
      <td>描述</td>
      <td>修改用户标签</td>
   </tr>
   <tr>
      <td>路径</td>
      <td>/tag/ modifytag</td>
   </tr>
   <tr>
      <td>请求方法</td>
      <td>POST</td>
   </tr>
   <tr>
      <td>SDK方法</td>
      <td>public static String modifyTag(String userId, String oldTag, String newTag)</td>
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
      <td>oldTag</td>
      <td>String</td>
      <td>老标签</td>
   </tr>
   <tr>
      <td>newTag</td>
      <td>String</td>
      <td>新标签</td>
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
      <td>flag</td>
      <td>int</td>
      <td>标签修改是否成功的标志，当status为0时，无flag字段；当status=1时，flag为0表示标签设置失败，flag为1表示标签设置成功</td>
   </tr>
   <tr>
      <td>msg</td>
      <td>String</td>
      <td>失败信息的描述；当status为1且flag为1时，无meg字段</td>
   </tr>
</table>