# 项目介绍

基于SSM的食堂点餐系统



角色:管理员、用户、食堂



前台用户可以实现商品浏览，加入购物车，加入收藏，预定，选座，个人信息管理，收货信息管理，收藏管理，评论功能，我的订单等。



食堂:个人中心、修改密码、个人信息、食堂菜单管理、菜系分类管理、消息留言管理、订单管理

系统管理员，管理员登录后，通过管理员菜单来管理后台系统。主要功能有:个人中心、用户管理、食堂管理、食堂菜单管理、菜系分类管理、消息留言管理、留言板管理、系统管理、订单管理等功能。



<font size=4 color=red>演示视频：</font><font color=red>[点击查看](https://www.bilibili.com/video/BV1KPBjYfEkC/?vd_source=889c0f0075f549c240ac1433b405c567)</font>






# 环境要求

1.运行环境：最好是java jdk1.8,我们在这个平台上运行的。其他版本理论上也可以。 

2.IDE环境：IDEA,Eclipse,Myeclipse都可以。推荐IDEA; 

3.tomcat环境：Tomcat7.x,8.X,9.x版本均可 

4.硬件环境：windows7/8/10 4G内存以上；或者Mac OS; 

5.是否Maven项目：是；查看源码目录中是否包含pom.xml;若包含，则为maven项目，否则为非maven.项目 

6.数据库：MySql5.7/8.0等版本均可；



# 技术栈

运行环境：jdk8 + tomcat9 + mysql5.7 + windows10

服务端技术：Java、Spring、SpringMVC、Mybatis，SSM



# 使用说明

1.使用Navicati或者其它工具，在mysql中创建对应sq文件名称的数据库，并导入项目的sql文件； 

2.使用IDEA/Eclipse/MyEclipse导入项目，修改配置，运行项目； 

3.将项目中config-propertiesi配置文件中的数据库配置改为自己的配置，然后运行；

# 运行指导

idea导入源码空间站顶目教程说明(Vindows版)-ssm篇：

http://mtw.so/5MHvZq 

源码地址：[http://www.codegym.top](http://www.codegym.top/)



# 运行截图

## 功能模块截图

![img](https://i-blog.csdnimg.cn/img_convert/4383bcd77dc2c481af8f387755bb7275.png)

![image-20241214192222708](https://i-blog.csdnimg.cn/img_convert/72d193c312649cb3a1c465c59da1e571.png)



### 项目截图

前台

![微信截图_20241214191546](https://i-blog.csdnimg.cn/img_convert/1424ce17d08a2486bf5fde5f2752627d.png)



![微信截图_20241214191308](https://i-blog.csdnimg.cn/img_convert/561fc7e4b5ca8ae1716a55ceca271cc3.png)

![微信截图_20241214191329](https://i-blog.csdnimg.cn/img_convert/1d9164193d57478383b69160cb36c729.png)

![微信截图_20241214191340](https://i-blog.csdnimg.cn/img_convert/50778220f109136d9c9b4159367741f8.png)

![微信截图_20241214191351](https://i-blog.csdnimg.cn/img_convert/25af09fe357f8c885c4b129bb60e5b3e.png)

![微信截图_20241214191411](https://i-blog.csdnimg.cn/img_convert/8771caddc373854867824fea2e48f93c.png)



后台

![微信截图_20241214191435](https://i-blog.csdnimg.cn/img_convert/b4cda178a6531096ff37cf81b30d9b67.png)

![微信截图_20241214191452](https://i-blog.csdnimg.cn/img_convert/9cf54c0cd05aa7f97f89a1912e64bdca.png)

![微信截图_20241214191501](https://i-blog.csdnimg.cn/img_convert/6303ea8c64067ca6f10962b9cc0cee8c.png)

![微信截图_20241214191511](https://i-blog.csdnimg.cn/img_convert/27b0a855f4c14abecf166c1b6a9df9dc.png)

![微信截图_20241214191523](https://i-blog.csdnimg.cn/img_convert/6c96a135f382bd54b1df50b8c3bd0f6e.png)
#### 代码

```java
public class CaixifenleiController {
    @Autowired
    private CaixifenleiService caixifenleiService;
    


    /**
     * 后端列表
     */
    @RequestMapping("/page")
    public R page(@RequestParam Map<String, Object> params,CaixifenleiEntity caixifenlei, HttpServletRequest request){

        EntityWrapper<CaixifenleiEntity> ew = new EntityWrapper<CaixifenleiEntity>();
    	PageUtils page = caixifenleiService.queryPage(params, MPUtil.sort(MPUtil.between(MPUtil.likeOrEq(ew, caixifenlei), params), params));
		request.setAttribute("data", page);
        return R.ok().put("data", page);
    }
    
    /**
     * 前端列表
     */
    @RequestMapping("/list")
    public R list(@RequestParam Map<String, Object> params,CaixifenleiEntity caixifenlei, HttpServletRequest request){
        EntityWrapper<CaixifenleiEntity> ew = new EntityWrapper<CaixifenleiEntity>();
    	PageUtils page = caixifenleiService.queryPage(params, MPUtil.sort(MPUtil.between(MPUtil.likeOrEq(ew, caixifenlei), params), params));
		request.setAttribute("data", page);
        return R.ok().put("data", page);
    }
    }

```





