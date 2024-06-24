# 插件帮助文档
## 界面布局说明
1. 布局如下图
![img.png](https://gitee.com/biyusheng/maven-plus/blob/master/images/img.png)
    A)左部分树形结构是完整pom依赖树的直观体现，常规如：jump in以及exclude操作可以直接在树形节点上右键进行操作。

    B)右部分是你选择了左侧树形节点后，会将当前节点和下一级节点平级展示在右侧表格中，并会异步抓取对应jar包的CVE信息，由于此过程耗时，因此目前CVE展示是比较慢的，需要等，建议选择子节点少的进行使用。

    C)Reimport按钮是在exclude以及add了jar包后，需要手动触发刷新依赖，并且树形数据也需要刷新

    D)Add POM按钮，会弹出一个添加jar包的弹窗，你可以通过搜索jar包名字进行可视化添加

    E)输入关键字搜索指定的jar包，这个过程会让你直接在树形结构中进行过滤，而不需要把树形数据展示为平级列表数据
2. 功能场景详解

   A)解决jar包冲突
   ![img.png](https://gitee.com/biyusheng/maven-plus/blob/master/images/resolve-conflicti-mg.png)
   如上图，点击exclude后，pom文件对应的jar依赖会添加相应的exclude，此时你需要再点击一下reimport手动触发一次刷新，项目的maven依赖才会更新，并且树形结构的数据也会随之更新。

   B)添加新的pom依赖
   ![img.png](https://gitee.com/biyusheng/maven-plus/blob/master/images/add-pom-img.png)
   如上图步骤，在弹窗中，输入关键字后，左侧表格中会显示所有的匹配的选项，此时选择你需要的pom后

   ![img.png](https://gitee.com/biyusheng/maven-plus/blob/master/images/select-left-ga-img.png)
   右侧会展示该pom的所有匹配的版本，此时你如果需要知道版本列表中的cve，可以手动点击Check CVE按钮进行检查，如果不需要则直接选择版本号记录

   ![img.png](https://gitee.com/biyusheng/maven-plus/blob/master/images/select-version-img.png)
   <font color='red'>特别说明</font>：如果你是打开了pom文件后点击的add pom按钮弹窗进行的上述添加操作，则pom依赖会自动加入当前打开的pom文件中，同时也提供右下角提示框供复制用；另外，安装了本插件后在`Tools`-->`Search Maven GAV`的功能按钮，点击这个按钮也会弹出弹窗，但是此入口弹窗就仅会右下角提示框进行copy依赖，不会主动添加到pom文件中。

   C)通过search everwhere搜索pom依赖
   按两下shift按键后会弹出search everywhere，里面会有一个maven的tab，在里面可以搜索pom并显示对应的CVE
   ![img.png](https://gitee.com/biyusheng/maven-plus/blob/master/images/search-everywhere-img.png)
