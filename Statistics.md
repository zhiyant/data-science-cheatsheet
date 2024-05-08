[TOC]



# Statistics



# Probability

组合数的计算公式：









# Concepts

### p-value

the smaller the p-value, the evidence against the null hypothesis is more significant.

Definition:

e.g. Let's flip a coin. H0 : the coin is fair; HA: the coin is not fair.

Then we filp the coin 100 times and perform several experiments.

Observation 1: 

Got 56 heads, p = 0.193. The H0 can be true. 

Observation 2: 

Got 60 heads, p = 0.032. 

Observation 3: 

Got 90 heads, p = 0.00001. H0 may not be true. Since the observation is too extrem under the hypothesis that H0 is true.

**How to explain it to a non-tech person:**



- T test

    检验两个样本均值之间是否存在差异

    

- Z test

### Two types Error

- Type I Error

    when we incorrectly reject a true H0 (level of significance, $\alpha$) It categorizes errors in a binary hypothesis test. The larger the value, the less reliable a test is. It's commonly used in A/B test to show that we observe differences between two groups but in reality there is no difference.

    (通常零假设认为两者相同)

- Type II Error

​		when we incorrectly accept a false H0. (level of power, $1 - \beta$)

### Multi-Collinearity Diagnostics

**(Definition)**

Multi-collinearity is when the predictors are **highly related to each other.** The estimated regression coefficient of any one variable depends on which other predictors are included in the model. (and the effect is magnified)

**(impacts)**

It can lead to a decrease in the model's explanatory power and increase the risk of errors in the model's estimates.

**(approaches for detection)**

To detect multi-collinearity, we can use two approaches.

- The **Variance Inflation Factor(VIF)** is a measure of correlation between each variable and all other independent variables in the model in the set of multiple regression variables.

    The VIF p-th covariate is 
    $$
    VIF_p = \frac{1}{1 - R_p^2}
    $$
    $R_p^2$ is the R-squared value obtained by regressing the p-th predictor on the remaining predictors.

    VIF is how much the variance of $\beta_p$ is inflated when it (the

    p-th covariate) goes **from being the only predictor** in the

    model **to being one of the many in the full model**.

The higher the VIF the higher correlation between this variable and the rest. A VIF of 1 indicates no correlation, while a VIF greater than 10 is a indicate of multi-collinearity.

- 

### Confidence Intervals

For a population parameter $\theta$. A $(1 - \alpha) * 100%$ confidence interval is :
$$
\hat{\theta} +- z_{\alpha/2}\hat{SD}(\hat{\theta})
$$


### Bayesian Theory

贝叶斯定理是在一些已知先验知识的基础上，通过观测



### Simpson Paradox

**定义**

辛普森悖论是一个统计学上的悖论，指的是在分组数据中出现的一种现象：**当将数据按照不同的组别进行分组后，某一变量的关系在整体数据中的方向与在每个组别中的方向相反或者部分相反。** 【关键词：分组和整体不同】

**示例**

假设有一所大学，想要评估男女申请者在录取率上是否存在性别歧视。为了进行分析，他们查看了最近几年的录取数据，并发现整体录取率是女性略高于男性。然而，当他们将数据按照不同的学部进行分组后，却发现在每个学部里男性的录取率都高于女性。具体数据如下：





出现这种情况的原因：



中心极限定理



大数定律



假设检验的过程

1. 确定检验目标
2. 



# Generalized Linear Models



get confidence interval for GLM





<u>saturated model:</u> the model fits the observed data perfectly

Deviance: $-2log(L_M/L_S)$(natural log). The lower the deviance the closer the two models are to each other.



$L_S$: the maximized value of the likelihood under the saturated model

$L_M$: the maximized value of th likelihood under our current model

$L_N$: the maximized value of th likelihood under the null model



**null deviance**: chi-squared. with degrees of freedom $dfn - dfs$

residual deviance: 

**residual deviance**:





H0:  the null model holds

HA: the proposed model is better

**Test statistics:** null deviance minus residual deviance

Approximate chi-squared distribution with degrees of freedom $dfn - dfm = p$ (slope coefficients)

**p-value**: the area above the test statstic using a chi-squared distribution (1 - pchisq(x, df))



the total number of observations (Y=1 and Y=0) in each group is n_j and e_j 

![image-20240428184618905](./assets/image-20240428184618905.png)

low test statistics: large p-value

high test statistics: small p-value





e.g.

H0: the model is fitting the observed data fairly well

HA: 



```R
lrtest(reduced, full) # likelihood ratio test
```







## AIC

provides a method for assessing the quality of your model through comparison of related models.

The idea to use AIC is to compare different models over the AIC

two models need to have 





## T test

用途：用于检验两组样本之间的均值，通常样本假设服从正态分布

流程：

示例：



## Z test



## F test

用途：





## Chi-square test

**用途：**检验两个类别变量之间的相关性；

**流程：**

H0: 两个类别变量之间不相关

HA: 两个类别变量存在相关性

**示例：**以下是观测情况

|        | 留存 | 流失 | 用户总数 |
| ------ | ---- | ---- | -------- |
| 有动画 | 1620 | 1340 | 2960     |
| 无动画 | 930  | 860  | 1790     |

1. 计算期望频数

    总体留存率 = (1620 + 930) / (2960 + 1790) = 2550 / 4750

    总体流失率 = 1 - 

    有动画组的期望留存频数为 2960 * 

    无动画组的期望留存频数为 1790 * 

2. 找到自由度

     df = group - 1 = 2 - 1 = 1

    ps.这里的group是

3. 计算卡方统计量

    $$
    \chi^2 = \sum\frac{(O_j-E_j)^2}{E_j}
    $$
    衡量每一组的观察频数和期望频数之间的差距

4. 查表找到临界值，比较

根据显著性水平和自由度找到临界值，比较临界值和卡方值。如果卡方值小于临界值，则拒绝零假设；如果卡方值大于临界值，则接受零假设





## ANOVA 









图像降噪方法：例如，高斯滤波、中值滤波、双边滤波、小波变换



























