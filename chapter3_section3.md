# 配置会话存储

通过sdk.properties的sessionStoreClass属性设置。会话存储支持Redis、Memory、扩展会话存储三种方式：  
Redis:通过redis分布式缓存存储会话；  
Memory：使用JVM内存MAP来存储，默认的存储方式，对集群环境，不能使用该方式；  
扩展会话存储：通过实现com.yonyou.yht.sdk.ISessionStore或继承com.yonyou.yht.sdk.AbstractSessionStore来进行扩展。  
Redis的配置方法

    sessionStoreClass=com.yonyou.yht.cache.RedisSessionStore
    
在Spring的配置文件中进行配置：

    <bean id="redisPool" 
    class="com.yonyou.yht.cache.redis.RedisPoolFactory" 
    scope="prototype" factory-method="createJedisPool">
      <constructor-arg value="direct://192.168.1.100:6380?poolName=mypool&amp;poolSize=100" />
    </bean>
    <bean id="jedisTemplate" class="org.springside.modules.nosql.redis.JedisTemplate">
      <constructor-arg ref="redisPool"></constructor-arg>
    </bean>
    <bean id="cacheManager" class="com.yonyou.yht.cache.CacheManager">
     <property name="jedisTemplate" ref="jedisTemplate" />
     <property name="sessionTimeout" value="3600" />
    </bean>

如果使用Redis来存储Session，需要在pom.xml里引入yht-sso-cache.jar，配置方式如下

    <dependency>
      <groupId>com.yonyou.yht</groupId> 
      <artifactId>yht-sso-cache</artifactId> 
      <version>0.1-SNAPSHOT</version>
    </dependency>

