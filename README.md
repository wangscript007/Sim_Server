Linux高并发通讯框架阅读参考                                                   
=======================

 **总述**<br>
   这个项目是跟着网易云课堂的讲师课程在做，历时两个多月，总算敲完了，虽然有些功能测试起来暂时还不理想，但整个框架的基本功能已经完备且能正常运行，一些不太理想的模块，后续再敲打。因为只是个框架，所以项目的具体业务逻辑实现几近没有，主要侧重点是放在连接处理，线程同步，恶意包检测，epoll高并发，封包解包等功能。<br>
   <br>
   注意，这个项目并不适合C++新手，尤其是刚刚学过《C++ Primer》等书，对于C++迷惑又自信的朋友，急于找一些项目练手，但是网上丰满姣好，让人垂涎的C++项目少之又少，总能找得的一些《C++实战3000例》等书，打开一看，却发现是C++ Window编程方向，对于立志Linux后端开发的朋友来说，真是让人气恼苦丧，初窥门径已觉晦涩难忍，踏一脚进来，更多了迷茫难知,让人感叹学习C++到底路在何方，不禁怀疑自己选得这条路是否有达康庄。<br>
   <br>
   我也是从这样过程深深浅浅一脚一脚走了过来，庆幸自己抱定初心，俯首前行，也万幸自己遇到了这样一个技术通达，领人顿入神通的项目，让原本存在于自己理论层面的知识，实实在在的铺展在自己的面前，用起来，活起来。如果说以前学习有关C++的各种知识是从0到1，那么写完这个项目，就应该是从1到2，有人领着踏出这从虚到实的一步，感觉真是太棒了！<br>
   学习或阅读这个项目的代码，您可能需要以下知识积累<br>
   * 《C++ Primer》
   * 《鸟哥的Linux私房菜》
   * 《TCP/IP详解 卷一》
   * 《Linux网络编程》
   * 《Unix环境高级编程》
   * 《C++11并发编程实践》
   * 《Makefile中文手册》<br>
   <br>

**Sim_server项目用到技术和实现的功能**<br>
 * 使用配置文件调配程序
 * 日志记录和打印
 * 进程重命名
 * 守护进程后台运行
 * 多进程并发
 * 多线程同步
 * 线程池
 * 连接池
 * epoll高并发
 * 自定义通讯包及封包、解包<br>
 以上功能经测试可用<br>
    
**Sim_server项目已实现但还有问题的功能**<br>
 * 心跳包
 * 洪泛攻击检测
 * 连接限时<br>
 以上功能测试效果不佳，有待提高
 <br>
 
 **区别与联系**<br>
   最后想讲一下，我这版与原版教程的区别
   * 原版更多的是使用Posix标准函数，例如Posix的线程与同步机制，而我选择了C++11本身的线程标准和同步技术
   * 原版大量使用\#define定宏变量，而我更倾向于使用const、enum等代替宏，且代替的很干净
   * 原版中大量使用char\*或普通指针，而我倾向于使用string和智能指针代替，当然，随着功能的复杂和完善，走出一条和讲师相似又相离的路是困难的，所以这里只是少量代替
   * 原版中的Makefile书写语法十分复杂，而我进行了极大简化，当然，这并不是因为我对Makefile的语法掌握十分精熟，恰恰是因为我对Makefile掌握的拙陋，才迫不得已，写一份自己能看懂的Makefile<br>
   
 **具体操作**<br>
    仓库中有三个代码包，分别是<br>
      * sim_server : 这是一个服务器端代码，是文件夹，下载到本地linux主机后，进入文件夹中，直接运行./sim_server程序即可运行，如果不放心，可以先执行make，再运行./sim_server<br>
      <br>
      * clinet : 是一个测试客户端，功能简单，一运行即可看懂如何操作，其中也包含Makefile文件，可以先make再运行./client<br>
      <br>
      * SIM_SERVER.zip : 这是一个window端的项目代码，主要不是为了运行，而是为了阅读和修改代码，而且这个代码运行不了，因为window上面不支持epoll技术，为了防止编写代码时报错看着烦心，我将epoll头文打包了进去。因为我写代码主要是用Clion写的，所以这个项目尽可能用Clion打开较好。Clion本身没有编译器，所以需要安装一个C++编译器，这里推荐Cygwin,Cygwin安装及Clion配置略有麻烦，这里可以参考我以前写的攻略：[关于Clion使用mingw输入回显和Cygwin配置二三事](https://tieba.baidu.com/p/5542169501)<br>
    

   
   
   
 
    

                                                 
