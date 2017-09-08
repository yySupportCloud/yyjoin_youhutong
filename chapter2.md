# 快速入门

本章为需要快速了解友户通的用户提供一个概览,下面通过一个简单的示例来演示友户通的单点登录集成。  
**第一步：配置maven库和依赖包**  
    
    <repository>   
          <id>yhtSnapshots</id>  
          <name>yhtSnapshots</name>
          <url>http://maven.yonyou.com/nexus/content/repositories/YHTCloud-Snapshot/</url>
          <layout>default</layout>
          <releases>
             <enabled>true</enabled>
          </releases>
          <snapshots>
             <enabled>true</enabled>
          </snapshots>
    </repository>
在您项目的pom.xml中添加  

    <dependency>
    <groupId>org.jasig.cas.client</groupId> 
    <artifactId>cas-client-core</artifactId> 
    <version>3.3.2</version> 
    <exclusions>
     <exclusion>
      <groupId>org.bouncycastle</groupId> 
      <artifactId>bcprov-jdk15</artifactId>
    </exclusion> 
    <exclusion>
      <groupId>xalan</groupId> 
      <artifactId>xalan</artifactId>
    </exclusion> 
    <exclusion>
      <groupId>commons-collections</groupId> 
      <artifactId>commons-collections</artifactId>
    </exclusion>
     </exclusions>
    </dependency> 
    <dependency>
      <groupId>com.yonyou.yht</groupId> 
      <artifactId>yht-sso-client</artifactId> 
      <version>0.1-RELEASE</version>
    </dependency>
    
**第二步：添加监听和拦截**  
在web.xml中添加如下内容，注意，Filter部分要放在配置文件的所有filter之前

    <filter>
     <filter-name>CAS Single Sign Out Filter</filter-name>
     <filter-class>com.yonyou.yht.web.cas.sso.SingleSignOutFilter</filter-class>
    </filter>
    <filter-mapping>
     <filter-name>CAS Single Sign Out Filter</filter-name>
     <url-pattern>/*</url-pattern>
    </filter-mapping>
    <filter>
     <filter-name>CAS Authentication Filter</filter-name>
     <filter-class>com.yonyou.yht.web.cas.AuthenticationFilter2</filter-class>
    </filter>
    <filter>
     <filter-name>CAS Validation Filter</filter-name>
     <filter-class>com.yonyou.yht.web.cas.ProxyReceivingTicketValidationFilter</filter-class>   
     <init-param>
       <param-name>encoding</param-name>
       <param-value>UTF-8</param-value>
     </init-param>
    </filter>
    <filter>
     <filter-name>CAS HttpServletRequest Wrapper Filter</filter-name>
     <filter-class>org.jasig.cas.client.util.HttpServletRequestWrapperFilter</filter-class>
    </filter>
    <filter>
     <filter-name>CAS Assertion Thread Local Filter</filter-name>
     <filter-class>org.jasig.cas.client.util.AssertionThreadLocalFilter</filter-class>
    </filter>
    <filter-mapping>
     <filter-name>CAS Authentication Filter</filter-name>
     <url-pattern>/*</url-pattern>
    </filter-mapping>
    <filter-mapping>
     <filter-name>CAS Validation Filter</filter-name>
     <url-pattern>/*</url-pattern>
    </filter-mapping>
    <filter-mapping>
     <filter-name>CAS HttpServletRequest Wrapper Filter</filter-name>
     <url-pattern>/*</url-pattern>
    </filter-mapping>
    <filter-mapping>
     <filter-name>CAS Assertion Thread Local Filter</filter-name>
     <url-pattern>/*</url-pattern>
    </filter-mapping>

**第三步：相关属性配置**  
在classes路径下新建sdk.properties，配置内容如下(红色的配置属性需要修改)。

    ##cas地址，表示cas认证服务器地址URL，可按情况修改为实际使用的cas服务器地址。
    cas.url=https://euc.yonyoucloud.com/cas
    ##当前域名应用的访问地址 
    servername=https://www.myappdemo.com

**第四步：获取用户信息**  
在业务程序中，可以通过以下方式获取用户信息

    Assertion assertion = AssertionHolder.getAssertion();
    AttributePrincipal principal = assertion.getPrincipal();
    Map<String, Object> info = principal.getAttributes();
    String userCode = (String)info.get(“userCode”);
    String userId = (String)info.get(“userId”);
    String userName = (String)info.get(“userName”);

通过以上步骤，即完成了与友户通的单点登录集成，访问应用是，如果没有登录，将自动跳转到登录页面，登录成功后，自动跳转到业务系统中，业务系统获取用户信息，建立用户会话。