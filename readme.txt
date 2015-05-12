解决方案中的项目列表及说明:

1. Rosin：直接作为Fiddler的扩展，整个项目的入口，立面涉及到对Fiddler相关接口的实现，整个项目的初始化。

2. Rosin.Base：会被解决方案中的其他项目所引用，包含了解决方案中其他项目所公用的代码，考虑到应用并不复杂，所以把以下四个公用模块合并到一个项目。

   Model 用来存放公用的数据结构或者类。

   Cache 实现了Rosin在运行时所使用的公共存储区域及相关方法。

   Configuration 包括了对配置的序列化，存储，读取等相关操作，最好使用.net的Configuration类和App.config。

   Util 包括了常用的公共功能和方法。

3. Rosin.Forms：包括了所有Rosin的可视化窗体。

4. Rosin.Logger：Logger单独拿出来作为一个项目，可以用来保存供我们调试的信息日志和用户通过Rosin取得的页面的日志，
   考虑使用Log4net。

5. Rosin.WebServer：Rosin的内建Web Server用来建立Rosin与页面间的上下行通道。以后也可以支持保存基于Web的管理界面等。

6. Rosin.Channel：实现了Rosin与页面间的上下行通道。

7. Rosin.Manager：用来解耦各个项目间的通信，可以考虑用事件的方式来实现。

新建项目注意事项：

除了Rosin外所有项目统一命名空间前缀 AlloyTeam.Rosin.项目名