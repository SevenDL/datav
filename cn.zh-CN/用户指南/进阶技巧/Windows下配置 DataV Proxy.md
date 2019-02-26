# Windows下配置 DataV Proxy {#concept_ldm_y25_q2b .concept}

**说明：** 

-   本文档所用系统环境为 Windows7，若使用 Windows Server 系统，安装方法会存在差异。
-   Linux 应用在 Windows 环境下安装，需要手动配置安装环境。
-   Windows 安装会去掉日志管理功能。

DataV Proxy 源码地址：[https://files.alicdn.com/tpsservice/3b30abf1b9f8a2056cc135d2a6587bb9.zip](https://files.alicdn.com/tpsservice/3b30abf1b9f8a2056cc135d2a6587bb9.zip)。

## 配置安装环境 {#section_r1b_cf5_q2b .section}

1.  [安装](https://nodejs.org/zh-cn/download/?spm=a2c4g.11186623.2.5.ffqbAN)并配置 Node.js。

    **说明：** 注意：Node.js 版本必须高于 4.4.5。

    1.  创建node\_global目录，用于存放全局安装文件。
    2.  修改全局安装的配置文件，如：

        ```
        npm config set prefix C:\node_global\
        ```

2.  [安装](https://sourceforge.net/projects/mingw/files/?spm=a2c4g.11186623.2.6.ffqbAN)并配置 MinGW 工具。
    1.  安装完成后直接启动。
    2.  选择安装管理页面左侧的 **All Packages**。
    3.  勾选右侧列表 **Package** 下的 **mingw32-base**、**mingw32-gcc-g++** 和 **mingw32-make**，右键选择 **Mark for Installation**。

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16586/15511695698517_zh-CN.png)

    4.  在菜单栏选择 **Installation** \> **Apply Changes** 安装需要的组件。
3.  配置环境变量。

    ![](images/8518_zh-CN.gif)

    1.  按照上图所示方法，选中系统变量中的 Path。
    2.  单击**编辑**在变量值的尾部添加三个环境变量：Node.js目录、Node.js全局安装目录、MinGW 的bin目录。
    3.  根据安装 Node.js 和 MinGW 的目录配置环境变量。例如：

        ```
        C:\Program Files\nodejs\;C:\node_global\;C:\MinGW\bin\
        ```

    4.  打开 Windows 的cmd命令行界面，执行 echo %PATH% 命令查看，结果如下图所示。

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16586/15511695698519_zh-CN.png)


## 部署代码并启动服务 {#section_wdd_pf5_q2b .section}

1.  [下载](https://files.alicdn.com/tpsservice/3b30abf1b9f8a2056cc135d2a6587bb9.zip) DataV Proxy 压缩包到本地并解压缩。
2.  [下载](http://docs-aliyun.cn-hangzhou.oss.aliyun-inc.com/assets/attach/93236/cn_zh/1543211821650/Makefile.zip)Makefile文件替换掉步骤一中解压后的文件目录中的 makefile 文件。
3.  打开 Windows 的 cmd 命令行界面，切换到步骤一解压后的目录中，执行 mingw32-make 命令，如下图所示。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16586/15511695698521_zh-CN.png)


验证以及数据库的配置请参考[DataV 数据代理协议配置](cn.zh-CN/用户指南/进阶技巧/Linux下配置DataV Proxy.md#)。

