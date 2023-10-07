# mavenPublishProject
maven-publish 插件配置

#### 文章参考
[Android：发布aar包到maven仓库以及 maven插件 和 maven-publish 插件的区别](https://juejin.cn/post/7017608469901475847#heading-13)
[发布包含源码的Kotlin项目aar包到Maven](https://juejin.cn/post/6844904198350323720#comment)

#### 文章说明
该文章是整理文章，方便自己不到处找源代码

[Demo地址--->gitHub](https://github.com/CMzhizhe/mavenPublishProject)

#### 已经完成了什么
1、配置maven-publish，见github
<br/>
2、可以上传源码(包含kt)，见github
<br/>
3、默认上传源码注释，见github
<br/>
4、sdk含有第三方依赖库，依赖传递，见github
<br/>
5、全局gradle配置
<br/>
6、上传源代码，传递注释说明

#### 全局gradle配置
什么叫全局gradle配置？大家都用git来开发，我们访问私人Maven仓库，是需要配置账号、密码，如果每个人都修改gradle.properties文件，总不是特别的好，或者说你可以额外创建一个xxxxx.properties然后再引入去，在配置git的时候再忽略掉，可以是可以，但是我不想每次创建一个新项目，都配置一份这样的文件吧，所以我们需要配置一个全局的gradle
![mac.png](https://upload-images.jianshu.io/upload_images/1945114-732f3d589cffc969.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
![window.jpg](https://upload-images.jianshu.io/upload_images/1945114-0882b86354c7da72.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

自己是window的还是mac的，自己按需要的来。注意，如果你自己修改了默认的.gradle位置的话，就放到自己修改的位置去就行了
创建gradle.properties文件，配置账号密码即可
USERNAME=xxxxx
PASSWORD=xxxxx


#### 注释说明
```
//注释内容........

/**
  * 注释内容.........
  * @param key  描述该key
  */
```
我发现maven只支持以上2种方式的注释上传。对于/****/这样的注释，你想增加@Auther 或者 @Date 都不会进行上传，我也很纳闷为啥，而且上传完后格式还不是很好看，注意格式/****/，如果不按这个格式来，不会显示注释的
