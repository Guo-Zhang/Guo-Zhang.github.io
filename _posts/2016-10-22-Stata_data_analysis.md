---
layout: post
title:  "Welcome to Jekyll!"
date:   2016-10-22
categories: Stata
---

# Data Analysis

## 回归

    reg <regressand> <regressor 1> <regressor 2> .. <regressor n>
    
    e(F)  // 显示F统计量
    matrix list e(b)  // 显示回归方程
    ereturn list // 显示整个命令
   

## 概率
    
    //似乎不能用
    probcalc b 20 0.3 exactly 2  //b:binomal
    probcalc b 20 0.3 atmost 2
    probcalc b 20 0.3 atleast 2
    probcalc n 100 15 between 85 115

## 模拟
    
    // $\int_0^1 \frac{exp\{-x^2/2\}}{2*\pi} dx$
    capture program drop hw
    program hw
    scalar n = 0
    forvalues m = 0(1)10000{
    scalar x = uniform()
    scalar y = uniform()
    scalar z = exp(-x^2/2)/(2*_pi)
    if y<=z{
    scalar n = n + 1
    }
    else{
    scalar n = n
    }
    }
    scalar j = n/10000
    display j
    end
    hw



