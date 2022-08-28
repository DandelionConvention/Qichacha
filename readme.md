企业查查爬虫

爬取内容：
企业名称、企业负责人、负责人电话、创立时间

默认获取范围：2021年一月至今

爬取范围：

医药，制造业，材料，智能，科技

项目文件：
更目录下包括：

chromedriver.exe 谷歌浏览器内核

spider02.py 爬虫py文件

data 文件夹，存放数据

logs 文件夹，存放日志

项目说明
spider02.py中参数说明：

type_list：实现多内容爬取。

start_time：自定义爬取起始时间，每次修改建议转移或删除data下的数据，不然会导致数据重复或文件过大

end_time：自定义爬虫停止时间，如果为空数组，默认获取当前时间

spider02.py实现原理：
本爬虫主要基于selenium和requests模块进行爬取，lxml使用xpath和正则表达式进行数据清洗。文件保存格式为.csv文件。

目标网站主要反爬机制：

1.登陆滑块验证

2.访问频繁滑块验证

3.访问频繁重新登陆

4.访问频繁账号封禁，封禁时间在20分钟到1小时不等

5.账号无法登陆（需要手动修改密码）

6.访问频繁ip封禁，连续爬取2小时或收集到20万条数据左右导致ip封禁，建议使用手机热点

7.访问频繁返回无用信息

针对上述的反爬机制，本代码都有相对应的应对方案，如有其它其它错误，或其它未发现的反爬机制，请联系作者。

/*************************************************************************************/

使用说明：

修改info.json文件，对程序参数进行调整。info.json使用记事本打开即可。

time格式，遵循[ 年 , 月 , 日 ]，start_time 必须指定，end_time默认当前日期，也可以指定

"type_list" 添加 ["制造业","科技","材料","智能","医药","添加type01","添加type02","添加type03"]

爬取顺序跟随type_list顺序先后。

如果调整info.json文件，请将data文件夹的数据转存，否则数据会重复写入。

调整info.json文件后，在是否读取日志中选择0不读取。

首次运行时，请核对info.json文件，且在是否读取日志中选择0不读取。

强行终止程序 ctrl + c

**************************************************************************

前面我展示的是文件配置和程序启动，后面我强制关闭程序模拟意外情况程序终止。在重新开始时输入1可以继续上次中断的地方继续爬取。在正常启动下输入0即可。
