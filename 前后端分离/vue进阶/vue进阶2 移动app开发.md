# 移动APP开发

## 移动APP开发的几种方式

1. 原生APP->NativeApp
2. WebApp->在手机的浏览器打开的应用
3. HybridApp->混合App，把前两种优点合二为一
4. 跨平台开发的App
5. 小程序/微网页（公众号）/快应用

---

## NativeApp介绍和特点

> IOS开发成本比较高，需要mac本

**定义**：传统原生App开发模式，有IOS和Android两大系统，需要个字语言开发各自App

**优点**：性能和体验都是最好的

**缺点：**开发和成本高

**应用技术**：Swift，OC，Java

---

## WebApp介绍和特点

**定义：**移动端的网站，常被称为***H5应用***，说白了就是特定运行在移动端浏览器上的网站应用。一般泛指SPA（单页面模式）模式开发出的网站。

**优点：**开发和发布成本最低

1. **开发成本低，可以跨平台，调试方便，开发速度最快**

   WebApp一般只需要一个前端人员开发出一套代码，然后即可应用于各大主流浏览器，没有新的学习成本，而且可以直接在浏览器中调试。

2. **维护成本低**

   如果代码合理，只需要一名前端就可以维护多个WebApp

3. **更新最为快速**

   由于WebApp资源是直接部署在服务器端的，所以只需要替换服务器端的文件，用户访问就是已经更新了（需要解决一些缓存问题）

4. **无需安装App，不会占用手机内存**

   通过浏览器即可访问，无需安装，用户比较愿意去用

**缺点：**性能和体验受到浏览器能力限制

1. **性能低，用户体验差**

   由于直接通过浏览器访问，所以无法使用原生API，操作体验不好

2. **依赖于网络，页面访问速度慢，耗费流量**

   WebApp每次访问都需要去服务端加载资源访问，所以必须依赖于网络，而且网速慢时访问速度很不理想，特别是在移动端，如果网站优化不好会无故消耗大量流量

3. **功能受限，大量功能无法实现**

   只使用H5的一些特殊API，无法调用原生API，所以很多功能无法实现

4. **临时入口，用户留存率低**

   既是优点也是缺点，优点是无需安装，缺点是用完后很难找到，很难专门为某个WebApp留存一个入口，导致用户很难再次使用。

**应用技术：**ReactJS，AugularJS，VueJS等

## HybridApp介绍和特点

**定义：**混合模式移动应用 ，介于WebApp、NativeApp两者之间的App开发技术，兼具“NativeApp良好交互体验的优势”和“WebApp跨平台开发的优势”，原生客户端的壳**WebView**，其实里面是**H5网页**。

- 把网页打包成移动APP
- 使你的Web程序可以访问手机原生能力

**优点：**开发和发布都比较方便，效率介于NativeApp和WebApp之间

1. **开发成本较低，可以跨平台，调试方便**

   Hybrid模式下，由原生提供统一的API给JS调用，世纪的主要逻辑有html和JS来完成，而由于最终使放在WebView中显示的，所以只需要写一套代码即可，达到跨平台的效果，另外也可以直接在浏览器中调试，很为方便。最重要的是只需要一个前端人员稍微学习下JS api的调用即可，无需两个独立的原生人员。

2. **维护成本低，功能可复用**

   如果代码合理，只需要一名前端就可以维护多个App，而且很多功能还可以互相复用

3. **更新较为自由**

   虽然没有WebApp更新那么神速，但是Hybrid中也可以通过原生API，进行资源主动下载，达到只更新资源文件，不更新apk的效果

4. **针对新手友好，学习成本较低**

   这种开发模式下，只需要前端人员关注一些原生提供的API，具体实现无需关心，没有新的学习内容，只需要前端人员即可开发

5. **功能更加完善，性能和体验要比WebApp好太多**

   因为可以调用原生API，所以很多功能只要原生提出就可以实现，另外性能也比较接近原生了

6. **部分性能要求的页面可以用原生实现**

   这应该是Hybrid模式的最多一个好处了，因为这种模式是原生混合Web，所以我们完全可以将交互强，性能要求高的页面用原生写，然后其他一些页面用JS写，嵌入WebView中，达到最佳体验

**缺点：**学习范围广，需要原生配合

1. 相比原生，性能仍然有较大损耗

   这种模式**受限于WebView**的性能桎梏，相比原生而言有不少损耗，体验无法和原生相比

2. 不适用于交互性较强的App

   这种模式的主要应用是：一些新闻阅读类，信息展示类App，但是不适用于一些交互较强或者性能要求较高的App

**应用技术**：Cordova，APPCan、DCloud、API Cloud

## 跨平台开发介绍和特点

> 特点：使用类似于Web技术的方式来开发NativeApp

**定义：**使用JSX语言写原生界面，js通过JSBridge调用原生API渲染UI交互信息

**优点：**效率体验接近Native App，发布和开发成本低于NativeApp

1. **虽说开发成本大于Hybrid模式，但是小于原生模式，大部分代码可复用**

   相比于原生模式，这种模式是统一用JS写代码，所以往往只需要一名成员投入学习，即可完成跨平台app的开发，而后续代码封装的好，很多功能可复用

2. **性能高于Hybrid，不逊色原生**

   这种模式可以认为用JS写原生，即页面用JS写，然后于三横通过Bridge胡三个月分析JS，将JS内容单独渲染成原生Android和IOS。

3. **开发人员单一技术展，一次学习，跨平台开发**

   这种模式是统一由JS编写，有独特的语法，所以只需要一次学习，即可同时开发Android和iOS

4. **社区繁荣，遇到问题容易解决**

   有个统一繁荣活跃的社区，对开发者很友好

**缺点：**学习有一定成本，且文档较少，免不了踩坑

1. 虽然可以部分跨平台，但并不是Hybrid中的一次编写，两次运行那种，而是不同平台有所区别
2. 开发人员有一定的学习成本
3. 不懂原生很难驾驭
4. 前期投入大，后劲足

**应用技术：**

***React Native（主流）***

- 公司：FaceBook
- 技术栈：React
- 基于React开发App的框架RN

**Flutter（未来趋势）**

- 公司：Google
- 提供了官方原生UI组件
- 比RN、Weex之类的体验更好
- 开发语言：Dart（和JS很像）
- 商业应用：闲鱼





