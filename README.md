TuShare


Tushare Pro version has been released, please visit the new official website to understand and query the data interface! [https://tushare.pro](https://tushare.pro)

TuShare is a tool that realizes the process from **data collection**, **cleaning and processing** to **data storage** of financial data such as stocks/futures, and meets the needs of financial quantitative analysts and those who study data analysis in data acquisition. It is characterized by wide data coverage, simple interface call, and fast response.

![](http://tushare.org/_images/main_pic_min.png)


![](http://tushare.org/_images/ts.jpg)

QQ交流群：

- 一群（已满）：14934432
- 二群（付费高级用户群，可获得更多支持及参与圈子活动）：658562506
- 三群（免费）：665480579
- 四群 (免费) ：527416821



Dependencies
=========
python 2.x/3.x   

[pandas](http://pandas.pydata.org/ "pandas")


Installation
====

- Step 1：pip install tushare
- Step 2：python setup.py install
- Step 3: access [https://pypi.python.org/pypi/tushare/](https://pypi.python.org/pypi/tushare/) Download and install


Upgrade
=======

	pip install tushare --upgrade

Quick Start
======
**Example 1.** Get historical trading data of individual stocks (including moving average data):

    import tushare as ts

	ts.get_hist_data('600848') #Get all the data at once
	In addition, refer to the get_k_data function

The results show:

> Date, Opening Price, Highest Price, Closing Price, Lowest Price, Volume, Price Change, Change, Average Price of 5 Days, Average Price of 10 Days, Average Price of 20 Days, Average Volume of 5 Days, Average Volume of 10 Days, 20 Average daily volume, turnover rate

    			 open    high   close     low     volume    p_change  ma5 \
	date                                                                     
	2012-01-11   6.880   7.380   7.060   6.880   14129.96     2.62   7.060   
	2012-01-12   7.050   7.100   6.980   6.900    7895.19    -1.13   7.020   
	2012-01-13   6.950   7.000   6.700   6.690    6611.87    -4.01   6.913   
	2012-01-16   6.680   6.750   6.510   6.480    2941.63    -2.84   6.813   
	2012-01-17   6.660   6.880   6.860   6.460    8642.57     5.38   6.822   
	2012-01-18   7.000   7.300   6.890   6.880   13075.40     0.44   6.788   
	2012-01-19   6.690   6.950   6.890   6.680    6117.32     0.00   6.770   
	2012-01-20   6.870   7.080   7.010   6.870    6813.09     1.74   6.832 

				 ma10    ma20      v_ma5     v_ma10     v_ma20     turnover  
	date                                                                  
	2012-01-11   7.060   7.060   14129.96   14129.96   14129.96     0.48  
	2012-01-12   7.020   7.020   11012.58   11012.58   11012.58     0.27  
	2012-01-13   6.913   6.913    9545.67    9545.67    9545.67     0.23  
	2012-01-16   6.813   6.813    7894.66    7894.66    7894.66     0.10  
	2012-01-17   6.822   6.822    8044.24    8044.24    8044.24     0.30  
	2012-01-18   6.833   6.833    7833.33    8882.77    8882.77     0.45  
	2012-01-19   6.841   6.841    7477.76    8487.71    8487.71     0.21  
	2012-01-20   6.863   6.863    7518.00    8278.38    8278.38     0.23  

Set the time of historical data：      
	
	ts.get_hist_data('600848',start='2015-01-05',end='2015-01-09')

				open    high   close     low    volume   p_change     ma5    ma10 \  
	date                                                                            
	2015-01-05  11.160  11.390  11.260  10.890  46383.57     1.26  11.156  11.212   
	2015-01-06  11.130  11.660  11.610  11.030  59199.93     3.11  11.182  11.155   
	2015-01-07  11.580  11.990  11.920  11.480  86681.38     2.67  11.366  11.251   
	2015-01-08  11.700  11.920  11.670  11.640  56845.71    -2.10  11.516  11.349   
	2015-01-09  11.680  11.710  11.230  11.190  44851.56    -3.77  11.538  11.363   
	 			ma20     v_ma5    v_ma10     v_ma20 	 turnover  
	date                                                        
	2015-01-05  11.198  58648.75  68429.87   97141.81     1.59  
	2015-01-06  11.382  54854.38  63401.05   98686.98     2.03  
	2015-01-07  11.543  55049.74  61628.07  103010.58     2.97  
	2015-01-08  11.647  57268.99  61376.00  105823.50     1.95  
	2015-01-09  11.682  58792.43  60665.93  107924.27     1.54  


**Historical data**
The interface provides all the historical data since the listing of the stock, and the default is the former one. If you don't set the start and end dates, you will return the recovery data of nearly one year. From the perspective of performance, it is recommended to set the start date and end date, and it is better not to exceed one year. After obtaining the data, please store it locally in time.

	ts.get_h_data('002337') #前复权
	ts.get_h_data('002337',autype='hfq') #后复权
	ts.get_h_data('002337',autype=None) #不复权
	ts.get_h_data('002337',start='2015-01-01',end='2015-03-16') #两个日期之间的前复权数据


**Example 2.** Get the transaction data of all stocks on the most recent trading day at one time (the result display speed depends on the internet speed)
	

	ts.get_today_all()


The results show:

> Code, name, price change, current price, opening price, highest price, lowest price, latest daily closing price, trading volume, turnover rate

		  code    name     changepercent  trade   open   high    low  settlement \  
	0     002738  中矿资源         10.023  19.32  19.32  19.32  19.32       17.56   
	1     300410  正业科技         10.022  25.03  25.03  25.03  25.03       22.75   
	2     002736  国信证券         10.013  16.37  16.37  16.37  16.37       14.88   
	3     300412  迦南科技         10.010  31.54  31.54  31.54  31.54       28.67   
	4     300411  金盾股份         10.007  29.68  29.68  29.68  29.68       26.98   
	5     603636  南威软件         10.006  38.15  38.15  38.15  38.15       34.68   
	6     002664  信质电机         10.004  30.68  29.00  30.68  28.30       27.89   
	7     300367  东方网力         10.004  86.76  78.00  86.76  77.87       78.87   
	8     601299  中国北车         10.000  11.44  11.44  11.44  11.29       10.40   
	9     601880   大连港         10.000   5.72   5.34   5.72   5.22        5.20   
	10    000856  冀东装备         10.000   8.91   8.18   8.91   8.18        8.10  
			volume  	 turnoverratio  
	0        375100        1.25033  
	1         85800        0.57200  
	2       1058925        0.08824  
	3         69400        0.51791  
	4        252220        1.26110  
	5       1374630        5.49852  
	6       6448748        9.32700  
	7       2025030        6.88669  
	8     433453523        4.28056  
	9     323469835        9.61735  
	10     25768152       19.51090  

**Example 3.** Get historical data

    import tushare as ts

	df = ts.get_tick_data('600848',date='2014-01-09')
	df.head(10)

The results show:
>Transaction time, transaction price, price changes, transaction hand, transaction amount (yuan), transaction type (卖盘 is sell order)

    Out[3]: 
     	 time  		price change  volume  amount  type
	0    15:00:00   6.05     --       8    4840   卖盘
	1    14:59:55   6.05     --      50   30250   卖盘
	2    14:59:35   6.05     --      20   12100   卖盘
	3    14:59:30   6.05  -0.01     165   99825   卖盘
	4    14:59:20   6.06   0.01       4    2424   买盘
	5    14:59:05   6.05  -0.01       2    1210   卖盘
	6    14:58:55   6.06     --       4    2424   买盘
	7    14:58:45   6.06     --       2    1212   买盘
	8    14:58:35   6.06   0.01       2    1212   买盘
	9    14:58:25   6.05  -0.01      20   12100   卖盘
	10   14:58:05   6.06     --       5    3030   买盘

**Example 4.** Realtime Quotes Data

    df = ts.get_realtime_quotes('000581') #Single stock symbol
	df[['code','name','price','bid','ask','volume','amount','time']]

The results show：
>Name, opening price, yesterday price, current price, highest, lowest, buying price, selling price, trading volume, trading amount...more in docs


	   code    name     price  bid    ask    volume   amount        time
	0  000581  威孚高科  31.15  31.14  31.15  8183020  253494991.16  11:30:36 
	  
Request multiple stock methods (preferably no more than 30 at a time):
    
	ts.get_realtime_quotes(['600848','000980','000981']) #symbols from a list
	ts.get_realtime_quotes(df['code'].tail(10)) #from a Series


More documentation
========

[https://tushare.pro](https://tushare.pro)

[http://tushare.org/](http://tushare.org/ "TuShare Docs")
 

Change Logs (Original Chinese version below)
-----------

1.2.17 2018/11/24
======

-Pro version adds futures data
-Pro version adds weekly/monthly data of A shares
-The Pro version adds support for stocks/funds/futures/data currency quotations in the universal quotation pro_bar interface, and also supports the restoration of stock quotations

1.2.15 2018/10/15
====

-Add the universal market pro_bar interface
-Optimize the set_token function



1.2.12 2018/08/10
====

-Release the first draft of the Pro version
-Publish the Pro website, [https://tushare.pro](https://tushare.pro)

1.0.5 2017/11/12
======

-Added convertible bond data
-Add long connection closing function
-Fix some bugs

1.0.2 2017/10/29
==========

-Added bar interface to support more stable stocks, ETFs, futures options, Hong Kong stocks, China concept stocks and other varieties
-Added tick interface to support transaction data of the above varieties
-Added daily capital flow data for Shanghai-Shenzhen-Hong Kong Stock Connect
-Fixed some bugs

0.9.2 2017/09/13
===========

-Added data currency market data interface, which also supports Huobi, okcoin, and Chinese Bitcoin
-Some bug fixes


0.8.8 2017/08/29
===========

-Added dividend bonus data (including history)
-Added get_day_all interface
-Added BDI interface

0.8.0 2017/06/05
===========

-Added 6 interfaces for futures market data, thanks to debugo for contributing code
-Fix some bugs

0.7.6 2017/05/16
=============
-Get\_today\_all interface data supplement
-Fixed coding problem under forecast\_data mac

0.7.0 2017/03/12
=============
-get\_today\_all interface speed up
-Version cumulative update


0.6.2 2016/12/03
==========
-Added the top ten shareholders and ten outstanding shares interface top10_holders
-Added global real-time index list interface global_realtime
-Fix some bugs

0.6.1 2016/11/22
===========
-Fix get_k_databug
-Fixed real trading login problem

0.5.6 2016/11/06
=============
-Added a new market data interface get_k_data (please follow the tushare public account "Dig Rabbit" and check the historical article "New Free Market Data Interface")
-Fix program and documentation bugs


0.5.1 2016/10/16
=============
-Added real trading interface
-Fix bug


0.4.9 2016/03/26
=============
-Added Shenwan industry classification get_industry_classified(standard='sw')
-Added trade_cal() trading calendar
-Fix bug

0.4.3 2015/12/24
============
-Added movie box office data
-Fix some bugs

0.4.1 2015/11/27
==============

-Added sina big order data
-Modify the day-dividing bug
-Shenzhen Margin Trading Data Repair

0.3.9 2015/10/13
============

-Added option implied volatility data
-Fix the index component and weight interface problem

0.3.8 2015/09/19
============

-CSI 300 component stock and weight interface problem fixed
-Other bug fixes



0.3.5 2015/07/27
==========

-Partial code correction


0.3.4 2015/06/15
===========

-Added "Dragon and Tiger List" module
1. Daily List of Dragons and Tigers
1. Statistics of individual stocks on the list
1. Statistics of sales department on the list
1. Tracking the seat of the Longhuban Institution
1. The transaction details of institutional seats

-Modify the data type of get\_h\_data to float
-Modify the open column missing from the get_index interface
-Merge bug fixes submitted on GitHub


0.2.8 2015/04/28
============

-Newly increased real-time market index list
-Newly increased historical market data of the index (all)
-Added a list of terminated companies (delisting)
-Added a list of suspended companies
-Fixed the defect that the margin and securities lending details have no date
-Fixed some bugs in get\_h\_data

0.2.6
========
-Added a list of margin trading and securities lending in Shanghai Stock Exchange
-Added a detailed list of margin trading and securities lending in Shanghai Stock Exchange
-Added a list of margin trading and securities lending in Shenzhen Stock Exchange
-Added a detailed list of margin trading and securities lending in Shenzhen Stock Exchange
-Fixed an abnormal problem caused by null in the data source of re-weighting data (affecting about 300 stocks)

0.2.5 2015/04/16
===========
-Complete compatibility support for python2.x and python3.x
-Partial algorithm optimization and code reconstruction
-Added CSI 500 constituent stocks
-Add transaction details of the day
-Fix the bug of distribution plan (high delivery and forwarding)

0.2.3 2015/04/11
===========
-New "Sina Stock Bar" news and popularity
-Added IPO data
-Fixed the problem of data duplication in the "Fundamental" module
-Fixed the bug that the historical data lacks a column (data source problem)

0.2.0 2015/03/17
=======

 -Added historical restoration data interface
 -Added real-time scrolling news and information mine data
 -Added CSI 300 index into shares and dynamic weights,
 -Newly added SSE 50 Index constituent stocks
 -Modify the historical market data type to float

0.1.9 2015/02/06
========
-Add classification data
-Add data storage example

0.1.6 2015/01/27
========
-Added historical and real-time market quotations of key indexes
-Update docs

0.1.5 2015/01/26
=====

-Add fundamental data interface
-Release the first version of the manual and open the [TuShare docs](http://tushare.waditu.com) website

0.1.3 2015/01/13
===
-Increase the acquisition of real-time transaction data
-Done for crawling Realtime Quotes data

0.1.1 2015/01/11
===

-Increase the acquisition of tick data

0.1.0 2014/12/01
===

-Create the first version
-Realize the acquisition of historical data of individual stocks



Change Logs 
-----------

1.2.17 2018/11/24
======

- Pro版增加期货数据
- Pro版增加A股周/月数据
- Pro版增加通用行情pro_bar接口股票/基金/期货/数据货币行情的支持，同时支持股票的复权行情

1.2.15 2018/10/15
====

- 增加通用行情pro_bar接口
- 优化set_token功能



1.2.12 2018/08/10
====

- 发布Pro版第一稿
- 发布Pro网站，[https://tushare.pro](https://tushare.pro)

1.0.5 2017/11/12
======

- 新增可转债数据
- 增加长连接关闭函数
- 修复部分bug

1.0.2 2017/10/29
==========

- 新增bar接口，支持更稳定的股票、ETF、期货期权、港股、中概股等品种
- 新增tick接口，支持以上品种的成交数据
- 新增沪深港通每日资金流向数据
- 修复了部分bug

0.9.2 2017/09/13
===========

- 新增数据货币行情数据接口,同时支持火币、okcoin、中国比特币
- 部分bug修复


0.8.8 2017/08/29
===========

- 新增分红送股数据（包含历史）
- 新增get_day_all接口
- 新增BDI接口

0.8.0 2017/06/05
===========

- 新增期货行情数据6个接口，感谢debugo贡献代码
- 修复部分bug

0.7.6 2017/05/16
=============
- get\_today\_all接口数据补齐
- forecast\_data mac下编码问题修复

0.7.0 2017/03/12
=============
- get\_today\_all接口提速
- 版本累积更新


0.6.2 2016/12/03
==========
- 新增十大股东和十大流通股接口 top10_holders
- 新增全球实时指数列表接口 global_realtime
- 修复部分bug

0.6.1 2016/11/22
===========
- 修正get_k_databug
- 修正实盘交易登录问题

0.5.6 2016/11/06
=============
- 新增全新行情数据接口get_k_data(请关注tushare公众号“挖地兔”后查看历史文章《全新的免费行情数据接口》)
- 修复程序和文档bug


0.5.1 2016/10/16
=============
- 新增实盘交易接口
- 修复bug


0.4.9 2016/03/26
=============
- 新增申万行业分类get_industry_classified(standard='sw')
- 新增交易日历trade_cal()
- 修复bug

0.4.3 2015/12/24
============
- 新增电影票房数据
- 修复部分bug

0.4.1 2015/11/27
==============

- 新增sina大单数据
- 修改当日分笔bug
- 深市融资融券数据修复

0.3.9 2015/10/13
============

- 新增期权隐含波动率数据
- 修复指数成份及权重接口问题

0.3.8 2015/09/19
============

- 沪深300成份股和权重接口问题修复
- 其它bug的修复



0.3.5 2015/07/27
==========

- 部分代码修正


0.3.4 2015/06/15
===========

- 新增‘龙虎榜’模块
	1. 每日龙虎榜列表
	1. 个股上榜统计
	1. 营业部上榜统计
	1. 龙虎榜机构席位追踪
	1. 龙虎榜机构席位成交明细

- 修改get\_h\_data数据类型为float
- 修改get_index接口遗漏的open列
- 合并GitHub上提交的bug修复


0.2.8 2015/04/28
============

- 新增大盘指数实时行情列表
- 新增大盘指数历史行情数据（全部）
- 新增终止上市公司列表（退市）
- 新增暂停上市公司列表
- 修正融资融券明细无日期的缺陷
- 修正get\_h\_data部分bug

0.2.6
========
- 新增沪市融资融券列表
- 新增沪市融资融券明细列表
- 新增深市融资融券列表
- 新增深市融资融券明细列表
- 修正复权数据数据源出现null造成异常问题（对大约300个股票有影响）

0.2.5 2015/04/16
===========
- 完成python2.x和python3.x兼容性支持
- 部分算法优化和代码重构
- 新增中证500成份股
- 新增当日分笔交易明细
- 修正分配预案（高送转）bug

0.2.3 2015/04/11
===========
- 新增“新浪股吧”消息和热度
- 新增新股上市数据
- 修正“基本面”模块中数据重复的问题
- 修正历史数据缺少一列column（数据来源问题）的bug

0.2.0 2015/03/17
=======

 - 新增历史复权数据接口
 - 新增即时滚动新闻、信息地雷数据
 - 新增沪深300指数成股份及动态权重、
 - 新增上证50指数成份股
 - 修改历史行情数据类型为float

0.1.9 2015/02/06
========
- 增加分类数据
- 增加数据存储示例

0.1.6 2015/01/27
========
- 增加了重点指数的历史和实时行情
- 更新docs

0.1.5 2015/01/26
=====

- 增加基本面数据接口
- 发布一版使用手册，开通[TuShare docs](http://tushare.waditu.com)网站

0.1.3 2015/01/13
===
- 增加实时交易数据的获取
- Done for crawling Realtime Quotes data

0.1.1 2015/01/11
===

- 增加tick数据的获取

0.1.0 2014/12/01
===

- 创建第一个版本
- 实现个股历史数据的获取
