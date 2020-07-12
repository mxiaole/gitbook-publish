本节介绍不同的编程语言常用的第三方包管理工具。

我们知道在我们开发的程序中，肯定不是所有的东西都需要自己去实现，可以借助一下开源的第三方包来提高我们的开发效率，不重复造轮子。这里就涉及到使用第三方包的问题。

# 1 C语言

在c语言中没有一个相关的工具帮助我们直接下载安装我们需要的第三方库，我们需要手动的下载和安装。常用的方法就是去github上去找我们需要的包，然后按照它提供的安装方式来安装我们需要的第三方库。通常情况下都是make工具进行编译，然后make install进行安装。一般的原理如下：

* 下载安装包
* 执行make，将我们需要的第三方库进行编译生成动态库或者静态库
* 执行make install，将第三方库的头文件，静态库，动态库拷贝到相应的路径下。

C语言中头文件查找路径说明：
* C语言中引入头文件有两种写法：
    ```txt
    #include <> ： 直接到系统指定的某些目录中去找某些头文件。
    #include “” ： 先到源文件所在文件夹去找，然后再到系统指定的某些目录中去找某些头文件。
    ```
* C语言中使用gcc编译c源代码的时候，通过`-I`参数来指明头文件的路径, 这时会按照指定路径的顺序搜索头文件

* 如果没有通过`-I`参数来指定路径，那么搜索顺序如下：
    ```txt
    1. 通过查找gcc的环境变量C_INCLUDE_PATH/CPLUS_INCLUDE_PATH/OBJC_INCLUDE_PATH来搜索头文件位置
    2. 如果在1中没有找到就从指定的目录内搜索： `/usr/include`、`/usr/local/include`、`/usr/lib/gcc-lib`
    3. 当在include中使用相对路径的时候，gcc会根据上面的规则来最终构建出头文件的位置。如#include <sys/types.h>就是包含文件/usr/include/sys/types.h
    ```
# 2 Python工具pip

在Python中使用的第三方包管理工具是`pip`，该工具在Python安装的时候一般都是自带的。使用pip工具安装的包通常被安装在python安装目录下的lib\site-packages目录下。

使用该工具安装第三方包非常的简单方便，常用的命令介绍如下：

```shell
python -m pip install flask      # 安装flask包
python -m pip uninstall flask    # 卸载flask包

# 使用--user参数可以只为当前用户而非系统中的所有用户安装软件包
python -m pip install flask --user

# 更多的使用方法可以使用
python -m pip --help
```

# 3 Go工具

go语言自带的`go get`命令来进行第三方包的安装。

```shell
go get github/mxiaole/package         # 安装包
go get -u github/mxiaole/package      # 更新指定的包
```

# 4 JavaScript工具npm

npm工具是js中的一个包管理工具。使用方法如下：

```shell
npm install package-name     # 安装包, 此种方式会将安装包下载到当前目录下的node_modules目录下
npm install -g package-name  # 全局安装，安装包放在 /usr/local 下或node的安装目录
npm uninstall 模块名          # 下载包
```