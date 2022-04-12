## AROON指标基础用法
通过aroonup和aroondown的绝对值突破进行趋势判断，决定入场做多或者做空

## 算法
AROON指标分位两个具体指标，分别为aroonup和aroondown
借助pandas_ta库的aroon函数进行了指标还原
1. aroonup计算
[（计算期天数 - 最高价天数）/ 计算期天数]*100
2. aroondown计算
[（计算期天数 - 最低价天数）/ 计算期天数]*100
3. aroon
aroon = aroonup + aroondown
常用参数为20

## 策略回测
1. 回测样本
沪深300日频指数 (2005-09-01 ~ 2012-03-15)

2. 指标参数
n = 20

3. 持仓信号判断
AROON_UP上穿70，并且AROON>0，开仓买进，1
AROON_DN上穿70，并且AROON<0，卖空，-1
AROON_UP下穿50，并且AROON<0，卖空，-1
AROON_DN下穿50，并且AROON>0，开仓买进，1