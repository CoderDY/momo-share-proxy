## 简介

此脚本用于提高墨墨背单词单词上限。

墨墨每日分享上限20个。于是我就写了一个自动刷访问量的脚本。
运行Momo/momo_proxy_useful.py即可，需要注意的是该文件第78行：proxies = self.jl_api('写自己的代码url')将代理换为自己的代理url。

本项目仅用于个人学习测试使用，勿用于非法用途。由于其他用途所产生的一切不良后果，本人概不负责。

# 忽略后面的所有介绍
以下为旧版本思路，忽略即可
大体思路是：
 1. 去免费代理ip网站爬代理
 2. 利用代理访问文章
 3. 增加访问量

**Python开发版本[3.10.13]**

## 版本说明

**momo-share1.x**之前用的是模仿人为操作去访问网页，这种方法更真实也更有效，缺点是速度慢。

**momo-share2.x**改用异步访问网页，以提高访问速度，亲测有效。

`1.x`

需要安装：

`pip install selenium`  // 需要安装浏览器驱动 该项目用的chrome浏览器

`chromedriver(对应浏览器版本下载)：`[下载地址](http://npm.taobao.org/mirrors/chromedriver)

`pip install requests`

`pip install bs4`

用到的库：bs4、random、requests、re、selenium、time

`2.x`

最近学习异步库所以借此机会将代码改用异步操作访问页面，经过一天的时间证明此方法有效可用。代码有许多不足的地方，欢迎指正。

在前期开发此脚本时，想过用requests去访问页面，结果事与愿违，此方法并没有被墨墨记录访问。因此就想着用selenium模仿人为操作，结果可想而知，但速度缺令人着急。可能是之前抓取代理个数太多原因，所以目前就改用异步脚本。

需要安装：

`pip install asyncio`

`pip install aiohttp`

`pip install bs4`

用到的库：re、random、asyncio、bs4、aiohttp


## 脚本使用
#### 一: 在本地运行
`Momo`文件夹下的代码

**1. 建议打包使用。**
    
**2. 正确使用脚本**

首次使用会在该脚本路径下创建一个用于读取墨墨分享链接的文件。文件名为 `momo_link.txt`。
> 该文件可自行手动创建，把要访问的分享链接放到文件内。
> 
> 这样首次运行即可跳过脚本对文件判断，读取文件内容，并访问链接。
> 
> 如果是脚本自动创建的`momo_link.txt`文件，则需要放入分享链接即可。

`运行结果`
- 程序运行结束，会在路径下创建一个结果提示文件。

**3. 更改存放链接和结果提示位置(可选择默认)**

> 第一步:打开`main.py`。
>  
> 第二步:更改变量`reminder_path`和`link_path`
> 
- reminder_path: 结果提示文件路径。
- link_path: 墨墨分享链接读取文件路径。

`提示`
- 此脚本使用的均为网络免费代理，质量一般。
- 可以在Windows下创建计划，每天定时运行几次。
- 如果你有更好的代理，可自行更换！！！


**4. 内容可依据自身需求进行更改**

例如:
   - 代理IP抓取
   - 异步限制
   - 读取分享链接文件的地址
   - 程序运行结果的文件创建地址


#### 二: 在云端运行

感谢`Lin1031`大佬，对本项目的修改和支持。

在云端运行，即把此项目挂在Github上运行。让Github充当24小时不停止工作的电脑。
只需每天更换`墨墨的分享链接`即可。

具体操作在`auto-momo`文件夹下。

自动执行默认是1小时,按需求可在`\.github\workflows\Auto.yaml`下的`- cron:`进行更改。

**本项目不定时更新，如有更新请及时更新自己的仓库，以保持最新！！！**

#### 觉得不错，请随手给个星。谢谢!!!

## 声明

代码中有很多可以优化的地方，目前功能可用加上学务繁忙，就先挖个坑等有机会再填。也非常欢迎，学习本项目的道友指正和更改，提高本项目内容质量。

本项目仅用于个人学习测试使用，勿用于非法用途。由于其他用途所产生的一切不良后果，本人概不负责。



