---
layout: post
title:  "Welcome to Jekyll!"
date:   2016-10-22
categories: Stata
---


# Data Management 

## 准备

### 打开路径
    cd <path>

### log

格式

 - .log
 - .smcl: 原始格式

操作log文件

    log using <logname>  //打开
                       ,append  // 追加
                       ,replace   // 替代
    log close  // 关闭
    log off  // 暂停
    log on // 继续


Note： 注释不能在命令行中使用

### 下载库
    ssc install <package>


### 帮助
    help <command>

## Stata命令

    [by varlist:] command [varlist] [=exp] [if exp] [in range] [weight] [,options]
 
- varlist: 一个变量列表，对一个列表子集重复同样的命令
- command: stata命令
- exp: 一个代数表达式
- range: 观测范围
- weight: weighting expression
- option: 选项列表

## 逻辑操作符

    &  //and
    !  // not
    |  // or
   
    ==
    !=
    <
    <=
    >
    >=

    =


## 导入数据
### 手动输入
    input x y
    1 2
    3 4
    end



### .csv or .txt
    insheet using <fname>
    infile varlist using <fname>

### excel file
    import excel <fname>[,options]


## 导出数据
    export 


## 数据清洗

### 重命名变量
    rename oldvar newvar

### 标记database
    label data[<"labelname">]

### 标记变量名

    label variable varname <"labelname">

### 标记values
    label values varname <labelvalue>


### 缺失值
    

### 创建变量

    generate new_var = exp
    generate new_var = (condition)

    replace varname = exp

    egen new_varn = function(var)

### 修改编码
    encode var, generate(new_var)

### 删除变量

    drop
    keep


### merge

### reshape
    reshape long math economy, i(id name) j(year)
    reshape wide math economy, i(id name) j(year)

### 类型转换
    destring, bpstring1, genrate(shp)

### 日期型变量
    generate bdaynew = date(bday,"MDY", topyear)