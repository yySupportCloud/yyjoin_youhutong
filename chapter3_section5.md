# SDK调用签名配置

友户通提供了用户服务的SDK接口，调用时需要配置好签名密钥

    #友户通接口服务器地址，如果不需要调用SDK的接口可不配置 
    yht.user.base.url=https://euc.yonyoucloud.com/rest 
    #客户端身份文件路径，支持classpath下的相对路径，调用SDK时需要 
    yht.client.credential.path=D:/authfile.txt 
    #连接池最大并发连接数
    httpclient.MaxTotal=100
    #单路由最大并发数
    httpclient.MaxPerRoute=100
    issimpleregister=0;
    #rest的配置文件
    #restful摘要算法
    rest.algorithm=HmacSHA1
    #RSA数字签名算法，目前JDK支持MD2withRSA,MD5withRSA,SHA1withRSA,都是1024bits
    UAP.DigitalSignatureAlgorithm=SHA1withRSA
    #RSA秘钥长度1024/2048
    UAP.DigitalSignatureKeyLength=1024
    #随机算法
    UAP.RandomAlgorithm=SHA1PRNG
    #HMAC摘要算法，目前jdk支持：HmacSHA1 (160 bits), HmacSHA256 (256 bits), HmacSHA384 (384 bits),HmacSHA512 (512 bits).
    UAP.KDF.PRF=HmacSHA1
    #签名或者摘要算法目前支持HMAC、RSA.
    UAP.AUTH.ALG=HMAC

客户端身份认证文件client.credential.path=D:/authfile.txt（此文件在开通应用时向友户通团队获取），配置样例如下：

    appId=testid
    key=testkey
    username=yhttest
    expiredTs=1471776321654
    expiredDate=2017-06-30 18:45:21
    
获取明文的用户联系方式，需要向友互通申请单独的密钥，并进行配置

    secretKey=testkey
