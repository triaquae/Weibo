# Weibo
模拟新浪微博

#1. 项目介绍
新浪weibo是一个用来练习开发能力的非常好的项目，本节我们一起来开发一个简单版的weibo

1.1功能需求

一个人可以follow很多人
一个用户如果发了新weibo会自动推送所有关注他的人
可以搜索、关注其它用户
可以分类关注
用户可以发weibo, 转发、收藏、@其它人
发微博时可选择公开、隐私、只能好友看等
可私信聊天
热门微博无需关注 
我的微博列表
可以评论、点赞微博
发微博时可以上传图片、视频、可以发表情
 


#2. 架构设计
2.1 设计架构前需要考虑的问题

weibo目前的架构经历了多次演变才做到目前支持大并发的成熟产品， 我们在设计架构时要考虑以下问题
亿级用户数据的存储如何高效实现？
用户发一条微博，后台要进行入库、分发、推送等多个动作才能完成，如何让用户感觉发微博速度快？
用户发weibo要推送给关注他的人，如何提高推送效率？
如何降低不同产品、模块、服务之前的耦合，使产品、功能的水平扩展等？
“Break large complex systems down into many services… google.com search touches 100s of service(ads, web search, books, news, spelling correction…”
如何做到去中心化，避免单点及瓶颈
如何实现接口安全
 

2.2 架构实现

所需服务组件:

django: 用户页面呈现
nginx: 前端高并发必备
cdn:异地高并发、静态内容速度快必备
redis: 热点weibo\话题数据高效存储
rabbitMQ: 用户weibo推送
SOA：服务解耦，服务接口化
zabbix,nagios: 系统监控
google analysis: 用户访问质量、行为分析监控


项目截图:
 ![image](https://github.com/triaquae/Weibo/docs/screenshots/weibo_flow.png)
 ![image](https://github.com/triaquae/Weibo/docs/screenshots/weibo_demo.png)
