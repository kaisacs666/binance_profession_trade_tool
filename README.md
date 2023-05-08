# binance_profession_trade_tool

小广告 如有区块链范围内的外包，解疑需求或者工作，包括链上和交易所，可 + 微信详聊 ，微信号：sorry_cjl

# 开发者介绍

开发者有五年的huobi，ok，binance的交易经验和交易所，链上数据采集经验，做过数据类型的 WEB APP（注册用户10000+），多年累计有超过100亿美金的币安U本位合约交易经验，这里不仅仅是一套手操工具，也是以工具为切入，对多年经验的一个总结

# 核心数据架构介绍

这是一套专业的WEB版本币安手操交易工具，包含服务端和前端程序，前端程序采用 REACT全家桶，后端采用C++和PYTHON。


其中C++为WEBSOCKET数据聚合处理服务器，PYTHON为数据采集，以及WEB服务器。


该系统采用分布式架构，通过多台服务器（理论上可以是无限台）读取币安全市场的TICK和KLINE数据，规避币安读取频率的风控，以达到降低数据延迟的目的后，汇入WEBSOCKET服务器处理，并向客户端输出。


客户端根据TICK数据自行拟合K线，并且每隔一段时间和币安的原生K线数据进行校对调正。


# 架构费用介绍

理论上达到最优效率需采用5台服务器读取tick数据，2台服务器读取一分钟k线数据，2台服务器读取十五分钟K线数据，1台服务器读取其余时间间隔的K线数据，以及1台websocket服务器，和四台WEB服务器分别负责仓位数据，订单数据，交易，其他功能，一共是15台服务器，以及一个mysql数据库。


以阿里云抢占式服务器和最低配置的mysql的费率计算，一个月成本大约为500~1000人民币，费用大头在流量，流量视使用时间而定


原架构基于阿里云设计，如采用亚马逊云等解决方案需自行更改当中API



# 系统优势介绍

1.支持全市场高速数据读取排序，全市场裸K ，10毫秒级速率读取排序展示，包括波动率排序，涨跌幅度排序等等，可自行接入tradingview等K线工具，但由于图数过多，可能会造成卡顿，即便是在做了优化的情况下（仅展示排序前三十的币种）


2.支持编程式自定义快捷键完成各种交易功能，包括开仓，关仓，止损等，如设置按键盘a时，以选定交易对的卖一价格乘以0.9999为初始价格，每隔千分之一挂出多单，一共挂出5个，其中所有参数均可自定义， 等等...


3.自由录入api，一键切换账号，账号的流水统计，风控等均隔离


4.支持自定义下单自动设置止损，自动取消超时订单，行情波动警报等


5.可设置冷静期，单位时间亏损达到设定额度，屏蔽交易对||暂停交易功能


6.盈利手续费统计等


7.自动购买BNB抵扣手续费


...

