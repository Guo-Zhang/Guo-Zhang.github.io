---
layout: blog
title:  Programming
date:   2016-10-22
categories: Stata
tags: Stata
---


# Stata Programming

## do文件
- .do: 脚本命令
- .ado: 定义Stata命令


### 打开do文件编辑器

    doedit  //打开do文件编辑器

### 注释
    * 单行注释
    // 单行注释
    /* 多行注释 */

### do文件结构
    //example.do
    program <programname>
    <command>
    end

### 运行do文件
    do example
    panel

### Note:改进
    //example.do
    capture program drop <programname>
    program <programname>
    <command>
    end
    <programname>  //显示变量

## Stata Macro
- local: do文件，program,循环语句内
- global: 全局

### local
    local x = 2
    display 2+`x' //注意符号，前面那个是`,后面那个是'


### global
    global y = 2
    display 2+$y //$是全局

## 循环

### forvalues
    capture program drop count5
    program count5
    forvalues i=1/5{
    display `i'
    }
    end
    count5
    // i = 0(5)100

### foreach
可以操作变量、文件、字符串、数值
    capture program drop count3
    program count3
    foreach num of numlist 1/4 8 105{
    di `num'
    }
    end 
    count3

    /*
    . count3
    1
    2
    3
    4
    8
    105
    */

### while
    local iterate = 1
    while `iterate'<=6{
    display `iterate'
    local iterate = `iterate' + 1
    }
    end 
    count6

    /*
    . count6
    1
    2
    3
    4
    5
    6
    */

### if
    if int(`span'/2)!=(`span'-1)/2{
    display "span is NOT an odd number"
    }
    else{
    display "span IS an odd number"
    }

    /* 
    . local span = 1

    . if int(`span'/2)!=(`span'-1)/2{
    . display "span is NOT an odd number"
    . }

    . else{
    . display "span IS an odd number"
    span IS an odd number
    . }

    . 
    end of do-file

    */
