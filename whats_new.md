(Original Chinese version below)

0.4.5
-------

-The get_today_all interface adds real-time PE, PB and circulating market value, etc.
-Modify financial data issues
-Fix the data bug before get_h_data (obtained during the day)

0.4.2
--------

-Added movie box office data
-Fix some bugs

0.4.1
----------

-Added sina big order data
-Modify the day-dividing bug
-Shenzhen Margin Trading Data Repair

0.3.9
---------

-Add the implied volatility data of Tonglian data option

-Repair index component stock interface

0.3.8
-------

-Completed development of Tonglian Data SDK v0.2.0
-CSI 300 component stock and weight interface problem fixed
-Other bug fixes
-Tonglian Data API document released


0.3.5
-------

-Partial code correction
-Added Tonglian Data SDK version 0.1


0.3.4
-------

-Added "Dragon and Tiger List" module
1. Daily List of Dragons and Tigers
1. Statistics of individual stocks on the list
1. Statistics of sales department on the list
1. Tracking the seat of the Longhuban Institution
1. The transaction details of institutional seats


-Modify the data type of get\_h\_data to float
-Modify the open column missing from the get_index interface
-Merge bug fixes submitted on GitHub


0.3.1
-------

-Fix the bug of get\_h\_data
-Modify the get\_stock\_basics data acquisition method


0.2.9
---------

-Added the Shanghai Interbank Offered Rate Module
1. Interbank Offered Rate (Shibor)
1. Shibor Bank Quotation Data
1. Shibor mean data
1. Loan base interest rate (LPR)
1. Data on the average base interest rate of loans
-Fundamental module interface optimization
-The bug fix of the data before restoration at a certain stage of history

0.2.8
---------

1. Newly increased real-time market index list
1. The historical market data of the newly increased cap index (all)
1. Newly added list of terminated companies (delisting)
1. Added a list of suspended companies
1. Fix the defect of no date in the details of margin trading and securities lending
1. Fix some bugs in get\_h\_data


0.2.6
-----------
1. Added a list of margin trading and securities lending on the Shanghai Stock Exchange
1. Added a detailed list of margin trading and securities lending in Shanghai Stock Exchange
1. Added the list of margin trading and securities lending in Shenzhen Stock Exchange
1. Added a detailed list of margin trading and securities lending in Shenzhen Stock Exchange
1. Correct the data source of the re-weighted data to cause an abnormal problem caused by null (affecting about 300 stocks)


0.2.5
-----------
1. Complete compatibility support for python2.x and python3.x
1. Partial algorithm optimization and code reconstruction
1. Newly added CSI 500 constituent stocks
1. Add the transaction details of the day
1. Fix the bug of distribution plan (high delivery and forwarding)



0.2.3
-----------
1. "Sina Stock Bar" news and popularity
1. IPO data
1. Fix the problem of data duplication in the "Fundamental" module
1. Fix the bug that the historical data lacks a column (data source problem)
1. New futures module (experimental) by @ideaplat




0.2.2
--------
Modified the bug of the data interface before restoration (pandas v0.14 reported an error when used)

0.2.1
--------
1. Add ‘Investment Reference’ data module

-Distribution plan
-Performance forecast
-Restricted shares lifted
-Fund holdings


2. Moved the "performance forecast" to the "investment reference" module

3. Modified the code in the historical restoration method


0.2.0
--------
1. New news event module

-Real-time financial news
-Stock information mine

2. New index constituent stocks and weight classification

-CSI 300 constituent stocks and weights
-List of SSE 50 Constituent Stocks


3. Modify the get\_hist_data() interface

-Modify the dtype of numeric data to float

4. Newly added historical restoration data interface get\_h_data

-Pre-reset (default)
-Post restoration
-No restoration


0.4.5
-------

- get_today_all接口增加实时PE、PB和流通市值等
- 修改财务数据问题
- get_h_data前复权数据bug修复（白天获取）

0.4.2
--------

- 新增电影票房数据
- 修复部分bug

0.4.1
----------

- 新增sina大单数据
- 修改当日分笔bug
- 深市融资融券数据修复

0.3.9
---------

- 加入通联数据期权隐含波动率数据

- 修复指数成份股接口

0.3.8
-------

- 完成通联数据SDK v0.2.0开发
- 沪深300成份股和权重接口问题修复
- 其它bug的修复
- 通联数据API文档发布


0.3.5
-------

- 部分代码修正
- 新增通联数据SDK0.1版


0.3.4
-------

- 新增‘龙虎榜’模块
	1. 每日龙虎榜列表
	1. 个股上榜统计
	1. 营业部上榜统计
	1. 龙虎榜机构席位追踪
	1. 龙虎榜机构席位成交明细


- 修改get\_h\_data数据类型为float
- 修改get_index接口遗漏的open列
- 合并GitHub上提交的bug修复


0.3.1
-------

- 修复get\_h\_data的bug
- 修改get\_stock\_basics数据获取方式


0.2.9
---------

- 新增上海银行间同业拆放利率模块
	1. 银行间同业拆放利率（Shibor）
	1. Shibor银行报价数据
	1. Shibor均值数据
	1. 贷款基础利率（LPR）
	1. 贷款基础利率均值数据
- 基本面模块接口优化
- 历史某一阶段的前复权数据bug修复

0.2.8
---------

1. 新增大盘指数实时行情列表
1. 新增大盘指数历史行情数据（全部）
1. 新增终止上市公司列表（退市）
1. 新增暂停上市公司列表
1. 修正融资融券明细无日期的缺陷
1. 修正get\_h\_data部分bug


0.2.6
-----------
1. 新增沪市融资融券列表
1. 新增沪市融资融券明细列表
1. 新增深市融资融券列表
1. 新增深市融资融券明细列表
1. 修正复权数据数据源出现null造成异常问题（对大约300个股票有影响）


0.2.5
-----------
1. 完成python2.x和python3.x兼容性支持
1. 部分算法优化和代码重构
1. 新增中证500成份股
1. 新增当日分笔交易明细
1. 修正分配预案（高送转）bug



0.2.3
-----------
1. “新浪股吧”消息和热度
1. 新股数据
1. 修正“基本面”模块中数据重复的问题
1. 修正历史数据缺少一列column（数据来源问题）的bug
1. 新增期货模块（实验）by @ideaplat




0.2.2
--------
对前复权数据接口的bug进行了修改（pandas v0.14版本在使用时报错）

0.2.1
--------
1、增加‘投资参考’数据模块

- 分配预案
- 业绩预告
- 限售股解禁
- 基金持股


2、将“业绩预告”挪到了‘投资参考’模块中

3、对历史复权方法中的代码进行了修改


0.2.0
--------
1、新增新闻事件模块

- 即时财经新闻
- 个股信息地雷

2、新增指数成份股和权重分类

- 沪深300成份股和权重
- 上证50成份股列表


3、修改get\_hist_data()接口

- 修改数值型数据的dtype为float

4、新增历史复权数据接口get\_h_data

- 前复权（默认）
- 后复权
- 不复权

