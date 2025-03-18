# ESIS
A Fast Time-Series InSAR Processing Software

https://southern-saxophone-c79.notion.site/ESIS-28bb22a6db2c4043a099ae3fb3959685?pvs=4                     
![image](https://github.com/ZGHHGZ/ESIS/assets/88225620/5e3e38ef-d2f7-4b98-8b97-0e1784666466)

# ESIS软件使用说明书（测试版）

## 1 简介

本软件主要用于SBAS-InSAR的数据处理，通过本软件可完成SBAS-InSAR数据处理的全流程。其中原始数据来自于ASF，干涉解缠服务基于HyP3（基于GAMMA、ISCE），时序处理基于MintPy。

本软件除可用于SBAS-InSAR数据处理的全流程外，还提供SLC影像数据下载、精密轨道数据下载、地形数据下载、地物分类数据下载等服务。

本软件基于Windows11开发，建议在Windows11操作系统下使用此软件。计算机的屏幕分辨率不得低于1366×768，屏幕缩放比例设置为100%。（本软件同时兼容Windows7、Windows10。）

本软件所调用的InSAR开源软件包如下：

| 软件包 | 功能 | 链接 |
| --- | --- | --- |
| asf_search | 影像数据搜索与下载 | https://github.com/asfadmin/Discovery-asf_search |
| hyp3_sdk | 干涉解缠服务 | https://github.com/ASFHyP3/hyp3-sdk |
| MintPy | SBAS时序处理 | https://github.com/insarlab/MintPy |

引用:

[1]于志刚,张光辉,张晨晰,等.基于PySide的时序InSAR处理可视化及形变监测实验[J].测绘工程,2024,33(06):41-48.DOI:10.19349/j.cnki.issn1006-7949.2024.06.006.

⚠本软件仅可用于学习交流，不可用于商业用途。

## 2 下载

GitHub

[Releases · ZGHHGZ/ESIS](https://github.com/ZGHHGZ/ESIS/releases)


## 3 安装

运行安装包文件，一直单击界面右下角的“下一步”即可。

![Untitled](pic/Untitled%201.png)

⚠提示：若软件运行出错，请尝试以”管理员“方式运行。

## 4 操作流程

软件主界面如下图所示，主界面为影像选择界面。（鼠标左键单击地图可查看点击位置的经纬度，用于搜索）。

![Untitled](pic/Untitled%202.png)

首先输入研究区域中心位置的经纬度，单击搜索以获取研究区域的影像信息。搜索结束后，会显示当前位置的全部影像数据。

![Untitled](pic/Untitled%203.png)

将右侧的“全部影像”切换为“分组影像”即可查询当前位置的影像序列。可选择组别以查看不同的影像序列。其中地图上绿色区域为影像序列的公共区域。

![Untitled](pic/Untitled%204.png)

单击”导入至→②像对筛选“以进行像对筛选工作。此界面可进行时空基线阈值的设置、像对的添加与剔除等操作。

![Untitled](pic/Untitled%205.png)

单击”导入至→③干涉解缠“以进行干涉解缠处理。此步骤需登录账号。可在界面左侧的”功能选项“中的”账户管理“中登录（若之前已经登录过账号，账号会自动保存到软件目录下，后续使用时可跳过“登录账号”这一步骤）。

账号每月有10000个积分，用户可从earth data免费注册。

单击上传任务按钮以上传当前选择的干涉像对。上传完成后，软件提示保存”项目信息“，此文件用于查询当前任务进度与下载数据，即单击”查看干涉解缠项目“并导入此”项目信息“文件以查询和下载。

![Untitled](pic/Untitled%207.png)

下载完成干涉解缠数据后，将其解压至一个空文件夹内。并通过影像裁剪功能选择此文件夹的路径。（鼠标左键单击地图可查看点击位置的经纬度，用于裁剪）。手动输入要裁剪的研究区域的经纬度范围，单击开始裁剪即可。裁剪完成后，即可进入④时序处理。

![Untitled](pic/Untitled%208.png)

时序处理功能仅提供默认参数运行，后续更新参数设置选项。选择影像数据文件夹后，单击”运行“按钮即可。（若多次进行时序处理，请将上次时序处理生成的文件删除后再运行。）

![Untitled](pic/Untitled%209.png)

选择右侧文件列表中的文件可快速预览运行结果。

![Untitled](pic/Untitled%2010.png)

时序处理运行结束后，进入⑤项目成果，即可预览形变速率图。

![Untitled](pic/Untitled%2011.png)

![Untitled](pic/Untitled%2012.png)

### C-SBAS模块

C-SBAS模块用于分类优化基线连接方式，以尽量保证高相干区域的监测精度及低相干区域的监测密度。\
[分类SBAS-InSAR模块处理流程](https://southern-saxophone-c79.notion.site/SBAS-InSAR-fa7d046a65ea4e138c96e89eb9d3205c?pvs=4)
<center class="half">
<img src="pic/Untitled%2013.png" width=550/>
</center>

### 时序数据浏览

![Untitled](pic/Untitled%2014.png)

### 结果展示

时序处理运行结束后，生成timeseries.shp文件，文件位于影像数据的文件夹下。可导入QGIS或ArcGIS中以查看。

![Untitled](pic/Untitled%2015.png)

![Untitled](pic/Untitled%2016.png)

![Untitled](pic/Untitled%2017.png)

![Untitled](pic/Untitled%2018.png)

![image](https://github.com/ZGHHGZ/ESIS/assets/88225620/271c53d3-d192-4dec-9c69-71cb237d8e8d)



## 5 说明

由于作者能力有限且不同电脑系统的环境不同，本软件使用过程中可能会出现一些未知错误，若用户发现一些可重现的错误，可提供截图及详细描述等信息，发送至邮箱2336164866@qq.com中，或通过下方群聊进行反馈，作者会尽快更正错误。
<center class="half">
<img src="pic/qqq.png" width=300/>
</center>

