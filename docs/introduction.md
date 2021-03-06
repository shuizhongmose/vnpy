# 功能介绍

作为一套基于Python的量化交易程序开发框架，vn.py致力于提供从交易API对接到策略自动交易的完整解决方案。

## 目标用户

如果有以下需求，不妨试试看vn.py：

* 基于Python语言来开发自己的量化交易程序，充分利用Python社区强大的数据研究和机器学习生态
* 通过一套标准化的交易平台体系，对接国内诸多不同类型的金融市场：证券、期货、期权、外汇、数字货币等
* 使用经过充分实盘检验的量化策略引擎，来完成从数据维护、策略开发、回测研究到实盘自动交易的整个业务流程
* 对平台进行各种定制扩展，满足个性化的交易需求：增加交易接口，修改GUI图形界面，基于事件驱动引擎开发复杂策略应用
* 掌控交易程序的所有源代码细节，彻底杜绝各种程序后门，避免被窃取策略、截获交易信号、偷盗账号密码等风险
* 节约为量化交易平台付出的资金成本，不必再支出上万每年的软件授权费或者每笔成交的额外加点


## 应用场景

从专业个人投资者、创业型私募，到券商资管部门、币圈Token Fund，都能找到vn.py的应用场景。

* 专业个人投资者：使用VN Trader直连期货公司的CTP期货柜台，实现从策略开发到全实盘自动交易的完整CTA业务流程
* 创业型私募：基于RpcService构建服务器端的统一报盘通道，允许交易员在自己的本地电脑自行开发各类交易策略应用
* 券商资管部门：对接证券公司统一部署的O32资管系统，基于事件驱动引擎定制开发多策略复杂系统
* 币圈Token Fund：使用VN Trader同时连接多个币圈交易所，通过AlgoTrading算法交易模块实现自动化委托执行，降低冲击成本


## 支持的接口

**vnpy.gateway**，盖国内外所有交易品种的交易接口：

* 国内市场

  * CTP(ctp)：国内期货、期权

  * CTP Mini(mini)：国内期货、期权

  * 飞马(femas)：国内期货

  * 宽睿(oes)：国内证券（A股）

  * 中泰XTP(xtp)：国内证券（A股）

  * 华鑫奇点(tora)：国内证券（A股）

* 海外市场
    
  * 富途证券(futu)：港股、美股

  * 老虎证券(tiger)：全球证券、期货、期权、外汇等

  * Interactive Brokers(ib)：全球证券、期货、期权、外汇等

  * 易盛9.0外盘(tap)：全球期货

* 数字货币

  * BitMEX(bitmex)：数字货币期货、期权、永续合约

  * OKEX合约(okexf)：数字货币期货

  * 火币合约(huobif)：数字货币期货

  * 币安(binance)：数字货币现货

  * OKEX(okex)：数字货币现货

  * 火币(huobi)：数字货币现货

  * Bitfinex(bitfinex)：数字货币现货

  * 1Token(onetoken)：数字货币券商（现货、期货）

* 特殊应用

  * RPC服务(rpc)：跨进程通讯接口，用于分布式架构


## 支持的应用

**vnpy.app**，开箱即用的各类量化策略交易应用：

* cta_strategy：CTA策略引擎模块，在保持易用性的同时，允许用户针对CTA类策略运行过程中委托的报撤行为进行细粒度控制（降低交易滑点、实现高频策略）

* cta_backtester：CTA策略回测模块，无需使用Jupyter Notebook，直接使用图形界面直接进行策略回测分析、参数优化等相关工作

* algo_trading：算法交易模块，提供多种常用的智能交易算法：TWAP、Sniper、Iceberg、BestLimit等等，支持常用算法配置保存

* script_trader：脚本策略模块，针对多标的组合类交易策略设计，同时也可以直接在命令行中实现REPL指令形式的交易，不支持回测功能

* rpc_service：RPC服务模块，允许将某一VN Trader进程启动为服务端，作为统一的行情和交易路由通道，允许多客户端同时连接，实现多进程分布式系统

* csv_loader：CSV历史数据加载器，用于加载CSV格式文件中的历史数据到平台数据库中，用于策略的回测研究以及实盘初始化等功能，支持自定义数据表头格式

* data_recorder：行情记录模块，基于图形界面进行配置，根据需求实时录制Tick或者K线行情到数据库中，用于策略回测或者实盘初始化

* risk_manager：风险管理模块，提供包括交易流控、下单数量、活动委托、撤单总数等规则的统计和限制，有效实现前端风控功能



## 通用类组件

**vnpy.api**，Python交易API接口封装，提供上述交易接口的底层对接实现。

**vnpy.event**，简洁易用的事件驱动引擎，作为事件驱动型交易程序的核心。

**vnpy.rpc**，跨进程通讯标准组件，用于实现分布式部署的复杂交易系统。

**vnpy.chart**，Python高性能K线图表，支持大数据量图表显示以及实时数据更新功能。
