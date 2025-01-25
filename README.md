# 2025MCM-c

## 问题

### 问题1：
Develop a model for medal counts for each country （for Gold and total medals at a minimum）
建立奖牌预测模型：至少包含金牌和总奖牌数
* A）基于预测模型给出2028奥运会的奖牌结果，要给出预测区间；哪些国家会取得进步？哪些国家会退步？
Based on your model, what are your projections for the medal table in the Los Angeles, USA summer Olympics in 2028? Include prediction intervals for all results. Which countries do you believe are most likely to improve? Which will do worse than in 2024? 
* B）模型要涵盖未获得奖牌的国家，同时预计他们在下一届奥运会获得奖牌的可能性
What is your prediction for how many will earn their first medal in the next Olympics? What sort of odds do you give to this estimate?
* C）考虑每一届奥运会的特定赛事，探究赛事和各个国家所获奖牌的关系，对于不同国家而言哪些赛事最为关键？原因何在？主办国选择的赛事如何影响最后的比赛结果？
Explore the relationship between the events and how many medals countries earn. What sports are most important for various countries? Why? How do the events chosen by the home country impact results?  

### 问题2：
估计名帅效应对成绩的影响：
* A）寻找名帅效应存在的原因
Examine the data for evidence of changes that might be due to a "great coach" effect
* B）估计名帅效应对于奖牌数的影响
 How much do you estimate such an effect contributes to medal counts?
* C）选择三个国家：指出他们应该在哪些项目聘请名帅，并且估计其影响
 Choose three countries and identify sports where they should consider investing in a “great” coach and estimate that impact. 

### 问题3：
对于奖牌榜的其他见解，尝试找到一些其他关系
What other original insight(s) about Olympic medal counts does your model reveal? 


## 建模思路

### 问题一：
1. 建立多元预测模型：
  * 待选模型：
    1. 传统多元时间序列模型：SARIMAX\Prophet
    2. 机器学习模型：线性回归、随机森林、XGBoost
    3. 深度学习模型：LSTM、GRU、Transformer

2. 特征工程方向：
 * 待选特征：
    (单个特征)
    1. 历史表现：金牌数量、金牌增长率、金牌的滚动平均值、总奖牌数量、奖牌结构占比、奖牌增长率、奖牌的滚动平均值、国际排名、排名变化
    2. 主办国效应：主办国标记、地缘文化标记（是否与主办国位于同一区域）、可以根据过去历届主办国表现提升量化主办国标记对成绩的影响
    3. 该届奥运会举办规模和信息：该届奥运会比赛项目数量、新增\取消项目的影响、重点项目特征、项目分布特征
    4. 国家运动员实力：运动员规模，性别比例，运动项目分布情况，奖牌效率（每名运动员平均获得的奖牌数），当前项目明星运动员数量

    5. （组合特征）主办国家结合项目数量 ......