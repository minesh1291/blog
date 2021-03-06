---
layout: post
title:  "My Kernel Series"
date:   2018-04-05
banner_image : house-pricing-predictions.png
tags: [Kernel, Python, Notebook, House Pricing, Kaggle, Competition, Linear Regression, Beginner]
---

# My Kernel Series
For Kaggle House Pricing Competition solving with Advanced Linear Regression
Under Construction...

1. Minimal [Kernel](https://www.kaggle.com/mineshjethva/let-s-do-the-minimal) LB: 0.60109
  * NaN =&gt; Median
  * LinearRegression

2. Minimal + Normalized X [Kernel](https://www.kaggle.com/mineshjethva/the-minimal-normalize-x) LB: 0.30013
  * LinearRegression(Normalized X)

3. Minimal + Normalized X,y [Kernel](https://www.kaggle.com/mineshjethva/the-minimal-normalize-x-y) LB: 0.14305
  * y = log2(y)

4. Minimal + Normalized X skew,y [Kernel](https://www.kaggle.com/mineshjethva/the-minimal-normalize-x-skew-y) LB: 0.14104
  * X = log2(X) if abs(skew) &gt; 1.7 &amp; no Inf issues

5. Minimal + Normalized X skew,y + filter low Var [Kernel](https://www.kaggle.com/mineshjethva/the-minimal-normalize-x-skew-y-exploratory) LB: 0.13764
  * filter X if Variance &lt; 0.2 and not correlated with target y

## ElasticNet enters...

6. Normalized X,y + dummy [Kernel](https://www.kaggle.com/mineshjethva/the-minimal-normalize-x-skew-y-categoricals) LB: 0.13817
  * dummy categorical features
  * ElasticNetCV

7.  Beginner ElasticNet [Kernel](https://www.kaggle.com/mineshjethva/beginner-elasticnet) Ver.1 LB: 0.13343
 * all previous things plus  
 * ElasticNetCV alpha optimization

8. Beginner ElasticNet + Univar_models [Kernel](https://www.kaggle.com/mineshjethva/beginner-elasticnet-univar-models) Ver.2 LB: 0.13101
 * ElasticNetCV L1_ratio = 1
 * ElasticNetCV alpha optimization
 * Bagged with 1/3 Simple Linear Regression using selected features by Univariate model performance TestMSE &lt; 0.5

9. Beginner ElasticNet + Univar_models [Kernel](https://www.kaggle.com/mineshjethva/beginner-elasticnet-univar-models) Ver.3 LB: 0.12867
 * Previous kernel with thresold 0.55 instead on 0.5
 * ver4 LB: 0.13976 didn' improve
     * Bagged with 2/3
 * ver5 LB: 0.13131
     * Bagged with 1/3
     * Thresold 0.55
     * ElasticNetCV L1_ratio = 0.2
10. Beginner ElasticNet + Univar_models [Kernel](https://www.kaggle.com/mineshjethva/beginner-elasticnet-univar-models) ver.7 LB: 0.12860


10. Beginner ElasticNet [Kernel](https://www.kaggle.com/mineshjethva/beginner-elasticnet) Ver.5 LB 0.12811
 * ElasticNetCV L1_ratio = 0.1
 * ElasticNetCV alpha optimization
 * Bagged with **5.** Minimal + Normalized X skew,y + filter low Var [Kernel](https://www.kaggle.com/mineshjethva/the-minimal-normalize-x-skew-y-exploratory) LB: 0.13764

11. Beginner ElasticNet [Kernel](https://www.kaggle.com/mineshjethva/beginner-elasticnet) Ver.7 LB 0.12408
 * ElasticNetCV L1_ratio = 1
 * ElasticNetCV alpha optimization
 * Bagged with
    1. Minimal + Normalized X skew,y + filter low Var [Kernel](https://www.kaggle.com/mineshjethva/the-minimal-normalize-x-skew-y-exploratory) LB: 0.13764
and
    2. Beginner ElasticNet [Kernel](https://www.kaggle.com/mineshjethva/beginner-elasticnet) Ver.5 LB 0.12811




Next things in the list are:

 * max_iter=1000, tol=0.0001 ? optimize
 * positive &amp; Selection with t&lt;1e-8
 * NaN Imputation
 * Outlier Remove
 * Ensemble

Under Construction...
