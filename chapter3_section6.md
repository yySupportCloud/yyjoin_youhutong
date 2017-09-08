# 忽略登录拦截

匹配模式名称支持CONTAINS（包含）、MUTICONTAINS（多个，逗号分隔的包含）、REGEX（正则表达式）、EXACT（相等）、MUTIREGEX（多个正则表达式，逗号分割）

    ignoreUrlPatternType=MUTIREGEX
    ignorePattern=.*\\.js,.*\\.css,.*\\.jsx,/rest/.*,/style/.*,/index\\.html,/controller/register/.*

定制的过滤条件类，在sdk.properties中配置

    ignoreUrlClassPath=
    com.yonyou.yht.web.cas.MutiContainsPatternUrlPatternMatcherStrategy
