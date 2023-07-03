# ESIS
A Fast Time Series InSAR Processing Software
# ESIS使用说明（测试版）

## 1 简介

本软件主要用于SBAS-InSAR的数据处理，通过本软件可完成SBAS-InSAR数据处理的全流程。其中原始数据由ASF提供，干涉解缠服务由HyP3提供（基于GAMMA 20220630），时序处理由MintPy提供。

本软件除可用于SBAS-InSAR数据处理的全流程外，还提供SLC影像数据下载、精密轨道数据下载、地形数据下载、地物分类数据下载等服务，哨兵二号的多光谱影像下载功能预计下一版本更新。

本软件基于Windows11开发，建议在Windndows11操作系统下使用此软件。计算机的屏幕分辨率不得低于1366*768，屏幕缩放比例设置为100%。（同时兼容Windows7、Windows10，界面可能会出现布局遮挡问题。）

本软件所调用的InSAR开源软件包如下：

| 软件包 | 功能 | 链接 |
| --- | --- | --- |
| asf_search | 影像数据搜索与下载 | https://github.com/asfadmin/Discovery-asf_search |
| hyp3_sdk | 干涉解缠服务 | https://github.com/ASFHyP3/hyp3-sdk |
| mintpy | SBAS时序处理 | https://github.com/insarlab/MintPy |

⚠本软件仅可用于学习交流，不可用于商业用途。

## 2 下载
[GitHub下载](https://objects.githubusercontent.com/github-production-release-asset-2e65be/660898540/03a5933b-f894-4f4e-b523-0b18d876a275?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAIWNJYAX4CSVEH53A%2F20230703%2Fus-east-1%2Fs3%2Faws4_request&X-Amz-Date=20230703T072659Z&X-Amz-Expires=300&X-Amz-Signature=6fd2cf047766ecb577fcea64581340095a5ae73b316d3d9e9f41d68a2976c0f4&X-Amz-SignedHeaders=host&actor_id=88225620&key_id=0&repo_id=660898540&response-content-disposition=attachment%3B%20filename%3DESIS-TEST-V003.exe&response-content-type=application%2Foctet-stream)


[百度网盘下载](https://pan.baidu.com/s/1INE1vyQdIaZN0EWozX5oqw?pwd=972m)

## 3 安装

运行安装包文件，一直单击界面右下角的“下一步”即可。

![Untitled](readme_pic/Untitled.png)

⚠提示：若软件运行出错，请尝试以”管理员“方式运行。

## 4 操作流程

软件主界面如下图所示，主界面为影像选择界面。

![Untitled](readme_pic/Untitled%201.png)

首先输入研究区域中心位置的经纬度，单击搜索以获取研究区域的影像信息。搜索结束后，会显示当前位置的全部影像数据。

![Untitled](readme_pic/Untitled%202.png)

将右侧的“全部影像”切换为“分组影像”即可查询当前位置的影像序列。可选择组别以查看不同的影像序列。其中地图上绿色区域为影像序列的公共区域。

![Untitled](readme_pic/Untitled%203.png)

单击”导入至→②像对筛选“以进行像对筛选工作。此界面可进行时空基线阈值的设置、像对的添加与剔除等操作。

![Untitled](readme_pic/Untitled%204.png)

单击”导入至→③干涉解缠“以进行干涉解缠处理。此步骤需登录账号。可在界面左侧的”功能选项“中的”账户管理“中登录。

账号每月有1000个像对额度，用户可从earth data免费注册（本软件自带的账号为测试账号，因使用人数较多，余额可能不足）。

![Untitled](readme_pic/Untitled%205.png)

单击上传任务按钮以上传当前选择的干涉像对。上传完成后，软件提示保存”项目信息“，此文件用于查询当前任务进度与下载数据，即单击”查看干涉解缠项目“并导入此”项目信息“文件以查询和下载。

![Untitled](readme_pic/Untitled%206.png)

下载完成干涉解缠数据后，将其解压至一个空文件夹内。并通过影像裁剪功能选择此文件夹的路径。

手动输入要裁剪的研究区域的经纬度范围，单击开始裁剪即可。裁剪完成后，即可进入④时序处理。

![Untitled](readme_pic/Untitled%207.png)

时序处理功能仅提供默认参数运行，后续更新参数设置选项。选择影像数据文件夹后，单击”运行“按钮即可。（若多次进行时序处理，请将上次时序处理生成的文件删除后再运行。）

![Untitled](readme_pic/Untitled%208.png)

选择右侧文件列表中的文件可快速预览运行结果。

![Untitled](readme_pic/Untitled%209.png)

时序处理运行结束后，生成timeseries.shp文件，文件位于影像数据的文件夹下。可导入QGIS或ArcGIS中以查看。

![未命名_副本.jpg](readme_pic/immm.jpg)

![Untitled](readme_pic/Untitled%2010.png)

## 5 说明

本软件为测试版，使用过程中可能会出现一些未知错误，若用户发现一些可重现的错误，可提供截图及详细描述等信息，发送至邮箱2336164866@qq.com中，或通过下方群聊进行反馈，作者会尽快更正错误。

![qqq.png](readme_pic/qqq.png)

## 6 历史版本

（3）2023.06.21：ESIS-测试版V003

[百度网盘 请输入提取码](https://pan.baidu.com/s/1INE1vyQdIaZN0EWozX5oqw?pwd=972m)

①修复因获取的时空基线参数为空而造成影像漏选的情况。

---

（2）2023.06.20：ESIS-测试版V002

[百度网盘 请输入提取码](https://pan.baidu.com/s/1uKCoKKUpySraTGOMvuUnag?pwd=axcs)

①修复”功能选项“当中的精密轨道数据下载出错的现象。

②支持无水体掩膜的干涉解缠图进行SBAS时序处理。

---

（1）2023.05.20：ESIS-测试版V001

[百度网盘 请输入提取码](https://pan.baidu.com/s/1IGFbDW7aLhXCV0WoecJx9Q?pwd=luqi)

①修复因干涉解缠内部分任务失败而无法下载的错误。

②修复多次进行时间筛选后，导出或上传的像对参数与筛选的像对不一致的错误。

③优化账号登录界面，固定窗口大小。

④更改安装包默认安装路径，无需管理员权限即可运行软件。

---

（0）2023.05.04：ESIS-测试版

[](https://pan.baidu.com/s/1PWQ_hQqSnKverZLVwRKIzg?pwd=ktce)

①此版本为首发版本。
