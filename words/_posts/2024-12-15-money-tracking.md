---
categories : words
date       : 2024-12-15
title      : 我怎么用电子表格记账
---

- [第一步：理解问题](#第一步理解问题)
- [第二步：想好怎么用电子表格](#第二步想好怎么用电子表格)
- [第三步：理解电子表格的细节](#第三步理解电子表格的细节)
    - [支出](#支出)
    - [收入](#收入)
    - [存款](#存款)
    - [负债](#负债)
    - [其他](#其他)
- [最后一步：动手做表格](#最后一步动手做表格)

## 第一步：理解问题

解决问题的第一步是弄明白想要达到什么目的。在过去的几年里我都不太确定我要搞明白什么。最一开始我只是想要记下来我都把钱花哪儿了。后来我想准确地知道我一共有多少钱。再后来我赚钱了，我想知道收入减去支出之后还剩多少。明年我就要借学生贷款了，我得知道我会欠多少钱。

我从 2020 年开始用电子表格记账。从别人做的模板开始学习，后来自己慢慢改。我每年都试着做些调整。我因为想把所有的记录都写在一个大表格里，搞得到处都是字，很复杂。我今天开始为明年做新的表格了，做的时候我就觉得其实我之前弄的很多数字我都不在乎，看起来也没那么方便。所以我一边做一边试着简化我对问题的理解。试着试着就得到了这样的结果。

所以现在看来我记账要搞清楚的问题是：
2. 我花了多少钱？平均一星期花多少？都花哪儿了？
3. 我赚了多少钱？平均一星期赚多少？都怎么赚的？
1. 我现在一共有多少钱？
4. 我欠了多少债？怎么欠的？

## 第二步：想好怎么用电子表格

我对应上面的每个问题都单独做了一个表单（<span lang="en">sheet</span>）。又额外做了一个叫做“其他”的表单，在里面放了一个算数用的表（<span lang="en">table</span>）和计算天数的表，天数是用来帮我算平均花费的。

我一共有下面这五个表单。

1. 支出
2. 收入
3. 存款
4. 负债
5. 其他

我一般每个周末都会打开表格把每个表单里的记录更新一下。每个表单也都会显示一些对我来说有用的统计结果，比如从开始记账到现在我一共花了多少钱、吃饭一共花了多少钱、平均每周吃饭花多少钱、每个月平均吃饭花多少钱。

## 第三步：理解电子表格的细节

我用的表格软件是斥巨资买苹果电脑送的 <span lang="en">Numbers</span>，我下面写的计算公式都是它的格式。各个表格软件比如微软的 <span lang="en">Excel</span> 和 <span lang="en">Libre Office</span> 开源免费的 <span lang="en">Calc</span> 公式都大同小异。你去网上搜索搜索应该都是可以弄明白我用的公式在它里面怎么写。

提一嘴我讨厌的表格软件是金山的 <span lang="en">WPS</span>。不是因为它不好用，而是因为里面全是广告。但是如果它对你来说用起来比较顺手的话就用它吧。我把自己的表格文件上传到了网盘，以免我在电脑上弄丢了或者出了意外。提醒你一下也要做好备份噢。

下面来看看我是怎么做每个表单的吧。

### 支出

在支出表单里，我放了两个表格。

第一个表格就一直往下填每次花了多少钱，像下面这样。我每次记账的时候都会写一个关键字，比如“吃饭”和“房租”。记下来日期可以方便我自己去看看每周花了多少钱。


| 关键字  | 金额  | 详情                           | 日期      | 周号  |
| ------ | ---- | ------------------------------ | -------- | ---- |
| 吃饭    | 9    | 不确定写什么，但这里要宽一点。      | 1/1/2025 | 1    |
| 房租    | 99   | 嗯，房租就是很贵。                | 1/1/2025 | 1    |

我的周号是让表格自动帮我算的，我用的计算公式（函数）是 `WEEKNUM(D2,2)`。\\
`D2` 是周号左边的日期单元格。\\
`2` 是公式要求我告诉它把星期一当作一周里的第一天。\\
我想显示周号是因为它能比日期更直观地告诉我哪些记录是在同一个星期里的。\\
一个我知道的小技巧是如果我在表格软件里选中一列数字，表格软件的状态栏会显示他们的总和和平均数。这是我在代工厂里上班的时候上司教我的。

<br>

第二个表格用来显示一些自动算出的统计数字。下面的例子里分别是：总计一共花了多少钱、吃饭花多少钱、房租花多少钱。

| 关键字  | 小结 | 周平均              | 月平均                      |
| ------ | ---- | ----------------- | -------------------------- |
| 总计   | 108  | 108 ÷ 1 × 7 = 756 | 108 ÷ 1 × 30.42 = 3,285.36 |
| 吃饭   | 9    | 9 ÷ 1 × 7 = 63    | 9 ÷ 1 × 30.42 = 273.78     |
| 房租   | 99   | 99 ÷ 1 × 7 = 693  | 99 ÷ 1 × 30.42 = 3,011.58  |

第一行“总计”就是把金额列的总和算出来，这样我就知道了一共花了多少钱。公式是 `SUM(支出::金额)`。\\
`支出::` 是上面提到的第一个表（<span lang="en">table</span>）；\\
`金额` 是金额的那一列。\\
整个公式就是算那一列的总和。

我计算吃饭花多少钱的时候用了一个 `SUMIF` 的公式。它能帮我算出来一个关键字对应的金额的总和。我的算式是 `SUMIF(支出::$关键字,$A3,支出::$金额)`。\\
算式里面的 `支出::$关键字` 是“支出”表的“关键字”列，公式会观察这一列记下的所有的关键字，用它来跟我要的关键字匹配；\\
`$A3` 是告诉公式我要的关键字是哪个，公式会找对应这个关键字的行。它就是统计的表格里左边的关键字；\\
`支出::$金额` 是支出表里的金额列，这个部分是告诉公式把这个数字加起来。

我算平均花费的办法不太精准。它是算从开始记账到现在的每天平均花了多少钱，再用这个数字算每周每月的数字。我也想不出来更好的算法，我就把这个数字当个估计吧。它的估计最准确时候是一周一月过完的时候。其他时候都只能当作一个大概的估计。

我是怎么算出来过了多少天呢？\\
在我的“其他”表格里面，我有一个地方记下了记账的开始日期，比如 2024 年的最后一天。\\
然后我有了一个公式用今天的日期减去 2024 的最后一天来算出开始记账了多少天。文章下面在“其他”表单的部分会告诉你。

### 收入

收入跟支出的计算方法是一模一样的，是相似的两个表单。同样的算式。改改表单和关键字的名字就好。

### 存款

存款里有三个表格：
1. 记银行里有多少钱。
2. 记现金有多少。
3. 对账。确认一下没有多记或者漏记。

对我来说，银行的部分就是把各个账户里的钱输进去而已。这个表格会算出来加起来我银行里一共有多少钱，像下面最后一列这样。

| 银行账户                                           | 余额  | 备注                                       |
| ------------------------------------------------- | ---- | ------------------------------------------ |
| 银行的现金账户（支票账户）                            | 0    | 这账户是刷卡直接扣款的地方，但是它不给利息。       |
| 有利息的存款账户（<span lang="en">Saving</span>）    | 0    |                                            |
| 其他账户                                           | 0    | 可以在这里记定期存款之类的确定可以收回来的投资。   |
| 总计                                              | 0    |                                            |

<br>

现金的计算有点意思了。就是要写一个公式来算各个面额的纸币硬币加起来一共有多少钱。在我的表格里面我只需要输入我有多少个或多少张这种钱。

| 硬币纸币  | 钱包   | 小金库  | 备注  |
| -------- | ----- | ------ | ---- |
| 10¢      | 1     | 0      | 0.1 |
| 20¢      | 1     | 0      | 0.2 |
| 50¢      | 1     | 0      | 0.5 |
| $1       | 1     | 0      |     |
| $2       | 1     | 0      | 2   |
| $5       | 1     | 0      | 5   |
| $10      | 1     | 0      | 10  |
| $20      | 1     | 0      | 20  |
| $50      | 1     | 0      | 50  |
| $100     | 1     | 0      | 100 |
| 总计      | 188.8 | 0      |     |

对于左边的钱包列，我的算式是：`0.1×B$2 + 0.2×B$3 + 0.5×B$4 + B$5 + 2×B$6 + 5×B$7 + 10×B$8 + 20×B$9 + 50×B$10 + 100×B$11`。\\
公式里的美元符号 `$` 是用来锁定它后面的行号的。加这个的作用是我在把公式往右复制或者拓展的时候表格软件更不容易出错。这是个我最近在学校里学到的小技巧呢。\\
接下来把公式复制到右边的小金库列应该就可以直接用了。你想要再多加几个小金库列都可以直接加。

现金的总额就是把钱包和小金库的总计结果加在一起。

<br>

对账的表格可能稍微需要花点心思理解。

我在这里不仅记下了去年的存款，还记下了前两年的存款，只是为了大概看看每年我的存款变化。实际上只有去年的存款，也就是**开始记账的日期的存款金额**才是对账用到的数字。

来看下面的表格吧。第一行右边的数字会告诉我有咩有记错账。如果等于零就说明没有记错。请看我下面怎么解释我的思路。\\
现有存款就是我现在表格里的银行与现金的总和相加。这个数字就是我自己也可以数出来的我一共有多少钱。\\
“收入减支出”是我的“收入”和“支出”两个表单里面的总和数字相减。这个数字的意义是根据我记下来的账，我攒下来了多少钱，或者我花掉了多少钱。我下面把这个数字叫做“金额变化”。

| 现有存款 − 去年存款 −（收入减支出） =   | 0          |
| ---------------------------------- | ---------- |
| 现有存款                             | $	1      |
| 2024 余额                           | $	0     |
| 2023 余额                           | $	0     |
| 2022 余额                           | $	0     |
| 收入减支出                           | **$	1**|

那行算式怎么来的呢？\\
“现有存款”减“去年的存款”是**实际上的金额变化；**\\
“收入减支出”得到的是从开始记账到现在**账上记录的金额变化。**这两个数字应该相等。也就是说：

现有存款 − 去年存款 = 收入减支出 \\
现有存款 − 去年存款 −（收入减支出）= 零

所以如果这个结果是零的话就表示没有记错账。\\
如果结果是正数的话说明是现有的钱比账上记得多，可能是有收入漏记了；\\
如果是负数的话应该是有支出漏记了。

“收入减支出”怎么用公式来算呢？\\
收入和支出的总和数字在它们各自的表单上，你先输入一个等号进入公式输入的界面，然后切换到对应的表单点一下要用的那个数字就可以把它输进公式里了。

### 负债

我还不确定我都需要记下来什么，因为我对于负债没什么经验。目前我只是粗略放了一个表格记下我什么时候借了多少。\\
以后应该再放一个表来记还了多少，这样可以知道还剩多少要还。

| 账单          | 金额 | 日期 | 备注 |
| ------------ | ---- | ---- | ---- |
| 2025 第一学期 | 0    |      |      |
| 2025 第二学期 | 0    |      |      |
| 2025 生活支出 | 0    |      |      |
| 总计         | 0    |      |      |

### 其他

这里有一个拼单算钱表和一个计算记账天数的小表格。

| **3**                                    | **3 ÷ 3 + 1** | **3 ÷ 3 + 2** | **3 ÷ 3 + 3** |
| ---------------------------------------- | ------------- | ------------- | ------------- |
| **这一列的价格用来除以上面的数字算平均**       | **第一个人**   | **第二个人**    | **第三个人**   |
| 3                                        | 1             |               |               |
|                                          |               | 2             |               |
|                                          |               |               | 3             |

这个表最多就算三个人，而且只能算平均分钱。当每个人有自己买的东西和一起分钱的东西的时候用它算就安心一点。\\
一起分钱的东西写进最左边的一列算平均。每个人自己买的东西写在自己的那一列算总和。这样表格就会算出来每个人该付多少钱。

<br>

计算天数的表是下面这样。\\
为了比较准确的算每个月的平均花费，我用每天的平均花费乘以这一年的月份平均有几天。比如平年就是 `365 ÷ 12 = 30.417`；\\
闰年就是 `366 ÷ 12 = 30.5`。

| 开始算账的日期       | 31/12/2024        |
| ------------------ | ----------------- |
| 今年的总天数         | 365               |
| 今年一个月平均有几天  | 365 ÷ 12 = 30.417 |
| 记账多少天了         | 今天 − 31/12/2024 |

有点难弄的是最后一行的算记账多少天了。我用的算式是 `DATEDIF(B1,TODAY(),"D”)`。\\
里面的 `B1` 是引用上面的“开始算账的日期”；\\
`"D"` 是一个公式要求的参数，它让公式算出来天数而不是月数之类的。

## 最后一步：动手做表格

如果你不熟悉使用电子表格软件的话可能会多花点些时间。去网上搜索搜索会找到些有用的东西的。比如搜索“<span lang="en">Excel  DATEDIF</span>”这样的关键字。

解决问题的最后一步是搜集反馈，更新自己对问题的理解，然后想办法去优化自己的做法。没有一劳永逸的解决办法呀。就耐心的慢慢来吧。\\
所以我没有直接给你一个我做的文件，因为那对你来说不是真的帮忙。慢慢来你肯定可以的。祝你好运。