# TreeInfotip

### TreeInfotip能做什么？

> TreeInfotip是基于IntelliJ 开发的项目目录自定义备注显示，主要通过自定义XML来生成项目目录树备注。

 ![样列](https://raw.githubusercontent.com/Link-Kou/intellij-treeInfotip/master/image/2020-03-18_16-47-30.jpg "样列")
 
 
---

### 使用环境

`IntelliJ IDEA Ultimate版（172+）`

`WebStrom（172+）`

### 源代码构建

    项目管理：Gradle
    
    注意：国内网络原因，构建十分费力，耐心一点
   
### 在线安装(搜索)

 IDEA或WebStrom -> Preferences -> Plugins -> TreeInfotip
 
### 手动安装

 [plugin.intellij.assistant-1.0.0.zip](https://raw.githubusercontent.com/Link-Kou/intellij-treeInfotip/master/builds/plugin.intellij.assistant-1.0.0.zip)
 
### 一、示列
> ##### 图片示列教程：（国内有些网络啊！tmd图片看不了的）


 ![样列](https://raw.githubusercontent.com/Link-Kou/intellij-treeInfotip/master/image/2020-03-18_16-46-20.gif "样列")
 

> ##### 说明文档：

1. 在项目根目录下创建Directory.xml文件(文件名称不能改变)

2. 文件内容示列
```xml：
  <?xml version="1.0" encoding="UTF-8"?>
  <trees>
      <tree path="/src">
          <tree path="/main">
              <tree path="/java/com">
                  <tree path="/plugins" title="插件">
                      <tree path="/infotip" title="信息显示">
                          <tree path="/parsing" title="读取"/>
                      </tree>
                  </tree>
              </tree>
              <tree path="/resources" title="资源文件夹"/>
          </tree>
      </tree>
      <tree path="/builds" title="构建文件"/>
      <tree path="/image" title="图片示例"/>
  </trees>
```

3. 标签说明
```xml：

  //trees只能有一个，所有子标签都在此标签里面
  <trees/>

  //模块（Maven多模块可以采用此标签作为标识） 
  <model/>

  //普通文件夹
  <tree/> 文件夹说明
```

4. 属性说明
```xml：

    //路径，MAC与Win的路径都是通用的，上下级的标签会拼接上父节点的path属性
    <path/> 

    //显示的内容
    <title/> 
```