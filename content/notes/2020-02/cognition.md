---
title: "认知"
date: 2020-02-16T23:12:56+08:00
description: "对目前现状认知、探讨;科学上网节点分享"
keywords:
- 认知
- 真相
- v2ray
- trojan
- 肺炎
- BGP
- IPLC
- 机场
- 科学上网
featured_image: "cover/confusion.jpg"
---

上一篇博客已经是19年12月底了，距离现在过了一个多月，过去的一个月中，回老家过年，2月1号回重庆，然后上了两周远程班，王者荣耀用鲁班从黄金打到星耀；
看了几部美剧（安眠书店、陌生人、致命钥匙、诸神的黄昏...），几部电影（急速车王、1917、缩小人生、美国甜心小姐、致所有我曾爱过的男孩...）；
越来越懒散，完全不想学习、看书。

## 也有在关注疫情

- 10天火神山
- 习主席在北京亲自指挥、亲自部署
- 红十字会囤积口罩、发国难财
- 李文亮医生事件
- 8名肇事者被依法查处
- 陈秋实失联
- 方斌被抓
- 华春莹推特点赞“灭共、习近平下台”

## 关于疫情来源

- 有人说是吃蝙蝠、果子狸等野生动物
- 也有人说是美国投放病毒、不之前武汉军运会嘛，那会儿放的
- 还有人说是武汉p4研究室泄露

我个人更偏向于p4实验室泄露，因为有新闻揭露在18年武汉曾研究出SARS病毒、目前中国还不允许美国专家介入...不管怎样，但愿抗体药物早点研制出来，实在不行等温度上升，病毒无法存活自然消失

## 谈谈认知

早在19年12月31号，文昭先生曾发布武汉疑似非典病毒已在武汉蔓延
<a href="https://www.youtube.com/watch?v=QIZLTGcWxsY&t=921s" target="_blank">https://www.youtube.com/watch?v=QIZLTGcWxsY&t=921s</a>,
那会并没有放在心上，按获取信息处理，事实并非如此，早该买口罩自用。
为什么人家会有这样的消息，其实是收集民间消息，当然在我们国家从来都是报喜不报忧，等到忧无法掩盖时才暴露出来。很多隐藏消息只能通过科学上网来获取，至于真实性还得有自己的理性分析。

在这堵墙的“保护”下，获取不到外面世界信息，我们的生活不就是像楚门一样么，所有信息被接收，真相被隐藏，只有权威人士知道，老百姓一直生活在襁褓里，或许这就是真相只存在少部分人之中。

去年我在深圳工作，相邻对岸的香港“暴乱”真相信息也只能通过科学上网获取，而且我的一个vps服务器ip被ban掉，在不知道cdn能挽救回来情况下，只能重新换个ip。

## 知道真相又怎样呢

是的，有的人知道真相，选择沉默，闷声发大财；有的人不想知道真相，生活依旧有滋有味；有的人无法知道真相，这就是现状。
容易传递的是那些“很自然地就令人相信（感觉）是正确的”，而不是“事实上正确的”事情。

最近在追《毒枭》第一季，为了利益，官场和黑道狼狈为奸，老百姓任由警察被割韭菜，就算有奇奇这类的好警察也无法改变现状，被权利压制。

哪有什么岁月静好，有权利、有关系的，傻白甜静好

## 如何改变现状

当下政权体质改变，民主投票选举，推翻赵家人专政，人民舆论自由。恐怕没那么容易，这会儿科学上网还是违法的呢，在我有生之年，墙能倒下就不错了。

我们能做到的，做好自己，做个明白人，永远不要叫醒装睡的人。多科学上网获取第三方资讯对比，化被动为主动，不会可以学。

最近统计我博客访问量，发现查看搭建trojan的剧增，还有网友打赏感谢的，这里再次谢谢你。
![alt viewtrojan](https://betterme.xin/images/viewtrojan.png "受访页面")

## 自己科学上网部分经验分享，只给需要的人

买个vps服务器，搬瓦工或捋谷歌云（需外币信用卡，谷歌邮箱），一键脚本；购买第三方机场。
目前ss、ssr基本已被墙识别，建议搭v2ray或trojan

### 自建梯子节点，懂的人自然懂

- **v2ray**:

```text
vmess://ewogICJ2IjogIjIiLAogICJwcyI6ICJ3dWxhYmluZ193d3cubmxnYmdmdy54eXoiLAogICJhZGQiOiAid3d3Lm5sZ2JnZncueHl6IiwKICAicG9ydCI6ICI0NDMiLAogICJpZCI6ICI0OTUxZTQ1Ny0yZWUzLTRlNGItYjI3YS00OGM0NWU4NzQ4OTYiLAogICJhaWQiOiAiMiIsCiAgIm5ldCI6ICJ3cyIsCiAgInR5cGUiOiAibm9uZSIsCiAgImhvc3QiOiAid3d3Lm5sZ2JnZncueHl6IiwKICAicGF0aCI6ICIvM2NlYjMyZDEvIiwKICAidGxzIjogInRscyIKfQo=
```


- **trojan**

节点1

- 域名:93jc.cn
- 端口:443
- 密码:www93jccn

节点2

- 域名:ttjoy.cc
- 端口:443
- 密码:wwwttjoycc

这些节点都是搭在搬瓦工上面，不支持奈飞等流媒体观看，不出意外vps到期之前都可以免费用，个人用来备用，用的多的还是机场。

### 第三方稳定机场推荐

- <a href="https://www.flycloud.win/auth/register?code=Jjxk" target="_blank">flycloud</a>
提供v2ray，BGP，IPLC专线节点，三种套餐等级，节点超多，等级一30+节点

- <a href="https://xtunnel.cc/auth/register?code=d3Yk" target="_blank">xtunnel</a>
全v2ray中转节点，节点不是很多，但够用了，刚开张不久，最近7折优惠，便宜实惠

推荐的机场都可以流畅性看4k（自己网络质量要好），都支持奈飞等流媒体观看

最后，祝各位身体健康，吃嘛嘛香。




