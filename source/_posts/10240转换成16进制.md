---
title: Python进制转换与通用转换器实现
categories:
  - Python
tags:
  - Python
  - 进制转换
comments: false
date: 2018-03-19 20:11:35
updated: 2018-03-19 20:11:35
---

## 进制通用转换器 
{% codeblock 进制通用转换器 lang:python  line_numbers:true hightlight:true wrap:true %}
def get_num_common(original_num, base_num):
    result = []
    
    while(original_num/base_num > base_num):
        result.append(original_num%base_num)
        original_num = original_num//base_num
    
    result.append(original_num%base_num)
    result.append(original_num//base_num)
    
    result.reverse()
    
    new_num = ''.join(str(i) for i in result)
    
    if base_num == 2:
        return '0b' + new_num
    elif base_num == 8:
        return '0o' + new_num
    elif base_num == 16:
        return '0x' + new_num
    elif base_num == 10:
        return int(new_num)
    else:
        return None
{% endcodeblock %}

## 十进制转换成16进制
{% codeblock 十进制转换成16进制 lang:python  line_numbers:true hightlight:true wrap:true %}
def get_num(original_num):
    '''hex(original_num)'''
    
    result = []
    
    while(original_num*1.0/16 > 16):
        result.append(original_num%16)
        original_num = original_num//16
    
    result.append(original_num%16)
    result.append(original_num//16)
    
    result.reverse()
    
    return '0x' + ''.join(str(i) for i in result)
{% endcodeblock %}

## 延伸 
### Python内置函数转换器
1、十进制数转换成N进制数

| 内置函数转换器 | 二进制数 | 八进制数 | 十六进制数 |
| --- | --- | --- | --- |
| 十进制数 | bin(num) | oct(num) | hex(num) |

2、N进制数转换成十进制数

| 内置函数转换器 | 十进制数 | 
| --- | --- |
| 二进制数 | int(num,2) | 
| 八进制数 | int(num,8) |
| 十六进制数 | int(num,16) |