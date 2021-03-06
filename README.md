# auto_invest
定投策略回测程序

此程序的基本策略见HELP.txt文件

####环境需求
- Python 2.6以上
- PyAlgoTrade 0.16版本（代码中已包含，更详细可见http://gbeced.github.io/pyalgotrade/）

####运行脚本说明
- 数据准备：数据存放于Data目录，按照csv模版即可，例如通达信等都支持csv导出。
- auto_invest.py：回测某一个基金或股票
```
$ python ./auto_invest.py Data/510050.csv 2011-06-01
OnBegin from 2013-06-01
OnStart: Initial Fund Value 500000.00
Tag,   Date,      profit,  bias, price,     shares,   buyMoney,TotalShares, TotalValue,  TotalFund
buy  , 2013-07-08,  0.00, -0.12,  1.45,    3450.00,    4999.05,    3450.00,    4999.05,    5000.00  
buy  , 2013-08-08,  0.03, -0.08,  1.50,    3335.00,    4999.16,    6785.00,   10170.72,   10000.00  
buy  , 2013-09-09,  0.14,  0.03,  1.68,       0.00,       0.00,    6785.00,   11371.66,   10000.00  
buy  , 2013-10-08,  0.10, -0.01,  1.62,       0.00,       0.00,    6785.00,   10998.49,   10000.00  
buy  , 2013-11-08,  0.05, -0.06,  1.54,       0.00,       0.00,    6785.00,   10469.25,   10000.00  
buy  , 2013-12-09,  0.10, -0.01,  1.62,       0.00,       0.00,    6785.00,   11012.06,   10000.00  
buy  , 2014-01-08, -0.00, -0.12,  1.47,       0.00,       0.00,    6785.00,    9973.95,   10000.00  
buy  , 2014-02-10, -0.01, -0.11,  1.46,       0.00,       0.00,    6785.00,    9892.53,   10000.00  
buy  , 2014-03-10, -0.07, -0.17,  1.36,    3663.00,    4999.99,   10448.00,   14261.52,   15000.00  
buy  , 2014-04-08,  0.04, -0.05,  1.49,       0.00,       0.00,   10448.00,   15557.07,   15000.00  
buy  , 2014-05-08, -0.00, -0.08,  1.43,       0.00,       0.00,   10448.00,   14971.98,   15000.00  
buy  , 2014-06-09, -0.00, -0.06,  1.43,       0.00,       0.00,   10448.00,   14930.19,   15000.00  
buy  , 2014-07-08,  0.02, -0.03,  1.47,       0.00,       0.00,   10448.00,   15306.32,   15000.00  
buy  , 2014-08-08,  0.11,  0.05,  1.59,       0.00,       0.00,   10448.00,   16654.11,   15000.00  
buy  , 2014-10-08,  0.14,  0.07,  1.63,       0.00,       0.00,   10448.00,   17061.58,   15000.00  
buy  , 2014-11-10,  0.18,  0.11,  1.69,       0.00,       0.00,   10448.00,   17678.02,   15000.00  
zone1, 2014-12-02,  0.41,  0.25,  2.02,  -10448.00,  -21136.30,       0.00,       0.00,       0.00  
buy  , 2014-12-08,  0.00,  0.34,  2.31,       0.00,       0.00,       0.00,       0.00,       0.00  
buy  , 2015-01-08,  0.00,  0.36,  2.52,       0.00,       0.00,       0.00,       0.00,       0.00  
buy  , 2015-02-09,  0.00,  0.27,  2.33,       0.00,       0.00,       0.00,       0.00,       0.00  
buy  , 2015-03-09,  0.00,  0.27,  2.40,       0.00,       0.00,       0.00,       0.00,       0.00  
buy  , 2015-04-08,  0.00,  0.36,  2.90,       0.00,       0.00,       0.00,       0.00,       0.00  
buy  , 2015-05-08,  0.00,  0.35,  3.06,       0.00,       0.00,       0.00,       0.00,       0.00  
buy  , 2015-06-08,  0.00,  0.38,  3.43,       0.00,       0.00,       0.00,       0.00,       0.00  
buy  , 2015-07-08,  0.00,  0.13,  2.60,       0.00,       0.00,       0.00,       0.00,       0.00  
buy  , 2015-08-10,  0.00,  0.10,  2.62,       0.00,       0.00,       0.00,       0.00,       0.00  
buy  , 2015-09-08,  0.00, -0.11,  2.18,    2296.00,    4998.39,    2296.00,    4998.39,    5000.00  
buy  , 2015-10-08,  0.01, -0.12,  2.20,    2276.00,    4998.10,    4572.00,   10040.11,   10000.00  
buy  , 2015-11-09,  0.16,  0.00,  2.53,       0.00,       0.00,    4572.00,   11576.30,   10000.00  
buy  , 2015-12-08,  0.08, -0.09,  2.37,       0.00,       0.00,    4572.00,   10817.35,   10000.00  
buy  , 2016-01-08,  0.01, -0.17,  2.22,       0.00,       0.00,    4572.00,   10145.27,   10000.00  
OnFinish: Final Fund Value $505103.46
profit: 5103.46 and years: 3.00
Simple,     3,     1701.15,   15000.00,    1926.00,      88.3%
```
PS: 如果时间参数省略，则从最早数据开始回测
- 批量运行(Linux下运行)：即回测Data目录里的所有数据，并取平均值
```
$ ./run.sh
  code, Simple, years, profitPyear,    fundMax,   averFund,  ratePyear
000016.csv, Simple,    24,     5841.78,  120000.00,   47500.00,      12.3%
000018.csv, Simple,    24,     6638.03,  120000.00,   33268.00,      20.0%
000021.csv, Simple,     9,     6176.93,   70000.00,   32002.00,      19.3%
000100.csv, Simple,    12,     6885.50,  110000.00,   22459.00,      30.7%
000725.csv, Simple,    15,     7168.63,  120000.00,   39933.00,      18.0%
100032.csv, Simple,     7,     3244.62,   50000.00,   26688.00,      12.2%
150023.csv, Simple,     6,     5672.36,  120000.00,   64227.00,       8.8%
150176.csv, Simple,     2,     1569.06,   35000.00,   13513.00,      11.6%
159902.csv, Simple,    10,     5997.36,   85000.00,   30094.00,      19.9%
159915.csv, Simple,     5,     1670.00,   15000.00,    4405.00,      37.9%
159920.csv, Simple,     4,     1552.05,   15000.00,   12048.00,      12.9%
160416.csv, Simple,     4,    -1137.14,   45000.00,   14265.00,      -8.0%
160719.csv, Simple,     4,     3058.96,   90000.00,   45216.00,       6.8%
510050.csv, Simple,    11,     6351.26,  105000.00,   30705.00,      20.7%
510880.csv, Simple,     9,     6810.87,   90000.00,   32063.00,      21.2%
513100.csv, Simple,     3,     1499.78,   10000.00,    6831.00,      22.0%
600023.csv, Simple,     2,     6693.00,   30000.00,   14979.00,      44.7%
600190.csv, Simple,    17,     4941.18,  120000.00,   39667.00,      12.5%
600276.csv, Simple,    16,     4273.55,  120000.00,   29880.00,      14.3%
600383.csv, Simple,    10,     6958.77,   55000.00,   13001.00,      53.5%
600795.csv, Simple,    16,     7245.16,  120000.00,   29750.00,      24.4%
601288.csv, Simple,     6,     1062.73,   15000.00,   11169.00,       9.5%
601600.csv, Simple,     9,     8312.22,  120000.00,   59549.00,      14.0%
601857.csv, Simple,     9,    -1573.84,  120000.00,   95210.00,      -1.7%
630005.csv, Simple,     6,     5481.65,   55000.00,   16720.00,      32.8%
999999.csv, Simple,    21,     6693.27,  120000.00,   60417.00,      11.1%
AVERAGE PROFIT:                                                 18.51%
```
####参数调整
参数在Config目录中，含义如下：
```
{
  "baseMoney":"5000",       #每次定投额m
  "zone1_profit":"0.4",     #第一区盈利40%卖出
  "zone2_profit":"0.3",     #第二区盈利30%卖出
  "zone3_profit":"0.2",     #第三区盈利20%卖出
  "zone4_profit":"0.1",     #第四区盈利10%卖出
  "zone1_unit":"6",         #第一区，m－6m之间
  "zone2_unit":"12",        #第二区，6m－12m之间
  "zone3_unit":"18",        #第三区，12m－18m之间
  "zone4_unit":"24",        #第四区，18m－24m之间
  "buy_bias":"-0.05"        #亏损-5%以下进行定投
}
```