`通用样式`
```json
[
  "block": "block的名字",
  "child": "下一条语句",
  "comment": "伪代码",
  "comment_id": 1
]
```

Tips:

- 涉及到下标的从 1 开始
- 开始初始变量
- 变量包含了普通变量和列表
- `增加变量的值`之前需要判断是否是列表, 使用的时候也需要判断
- for 变量单独设立数组来防止重复变量名

# Page List

  - ### `logic`
    1. [条件语句](#条件语句)
    2. [比较语句](#比较语句)
    3. [逻辑运算符](#逻辑运算符)
    4. [布尔值](#布尔值)
    5. [空值](#空值)
    6. [repeat循环](#repeat循环)
    7. [while循环](#while循环)
    7. [until循环](#until循环)
    8. [for循环](#for循环)
    9. [循环控制](#循环控制)
  - ### `math`
    1. [数字](#数字)
    2. [四则运算](#四则运算)
    3. [数学方法](#数学方法)
    4. [数学常数](#数学常数)
    5. [数字检查](#数字检查)
    6. [随机数](#随机数)
  - ### `text`
    1. [文本](#文本)
    2. [合并文本](#合并文本)
    3. [文本长度](#文本长度)
    4. [文本是否为空](#文本是否为空)
    5. [查找文本](#查找文本)
    6. [获取文本中的字符](#获取文本中的字符)
    7. [获取文本的子串](#获取文本的子串)
    8. [转换大小写](#转换大小写)
  - ### `variables`
    1. [获得变量](#获得变量)
    2. [赋值变量](#赋值变量)
    3. [增加变量的值](#增加变量的值)
  - ### `list`
    1. [创建空线性表](#创建空线性表)
    2. [创建包含一系列项目的线性表](#创建包含一系列项目的线性表)
    3. [通过一个项目重复多次创建线性表](#通过一个项目重复多次创建线性表)
    4. [获得线性表的长度](#获得线性表的长度)
    5. [线性表是否为空](#线性表是否为空)
    6. [查找线性表](#查找线性表)
    7. [获取/移除线性表元素](#获取/移除线性表元素)
    8. [添加/修改线性表元素](#添加/修改线性表元素)
  - ### `base_list`
    1. [设置链表坐标](#设置链表坐标)
    2. [获得链表变量](#获得链表变量)
    3. [设置链表变量](#设置链表变量)
    3. [创建链表](#创建链表)
    4. [获得结点变量](#获得结点变量)
    5. [设置结点变量](#设置结点变量)
    0. [获得当前结点](#获得当前结点)
    0. [移除下一个结点(显示上)](#移除下一个结点(显示上))
    0. [删除被移除的结点](#删除被移除的结点)
    0. [移动到下一个结点](#移动到下一个结点)
    0. [将当前结点指向另外结点(显示上)](#将当前结点指向另外结点(显示上))
    0. [将新节点指向另外结点(显示上)](#将新节点指向另外结点(显示上))
    0. [将新节点添加进链表(实际上)](#将新节点添加进链表(实际上))
    0. [获取新节点](#获取新节点)
    0. [生成新节点](#生成新节点)
    0. [获取链表节点数量](#获取链表节点数量)
    0. [获取结点的值](#获取结点的值)
    0. [获取链表当前结点的值](#获取链表当前结点的值)
    0. [判断当前结点是否是最后一个结点](#判断当前结点是否是最后一个结点)
    0. [获取链表的下一个结点](#获取链表的下一个结点)


## 条件语句

> for if/elseif/else condition

#### 格式

```
{
  block: 'IF',
  condition_number: 条件的个数,
  conditions: [
    [
      '条件' or [],
      '执行语句' or []
    ]
  ]
}
```

#### example

```json
{
  "block": "IF",
  "condition_number": 1,
  "conditions": [
    [
      false,
      ""
    ]
  ]
}
```

[Back To Top](#logic)

## 比较语句

> include <, >, =, <=, >=

#### 格式

```
{
  block: 'COMPARE',
  type: 比较的符号,
  left: 左边的表达式, []
  right: 右边的表达式, []
}
```

#### example

```json
{
  "block": "COMPARE",
  "type": "==",
  "left": {
    "block": "COMPARE",
    "type": "!=",
    "left": true,
    "right": false
  },
  "right": true
}
```

[Back To Top](#logic)

## 逻辑运算符

> include AND, OR, NOT

#### 格式

```
{
  block: 'LOGIC_OPERATION',
  type: 运算符符号,
  left: 左边的表达式, []
  right: 右边的表达式, [] // 如果是NOT，则没有
}
```

#### example

```json
{
  "block": "LOGIC_OPERATION",
  "type": "AND",
  "left": {
    "block": "COMPARE",
    "type": "!=",
    "left": true,
    "right": false
  },
  "right": false
}
```

#### example

```json
{
  "block": "LOGIC_OPERATION",
  "type": "NOT",
  "left": {
    "block": "COMPARE",
    "type": "!=",
    "left": true,
    "right": false
  }
}
```

[Back To Top](#logic)

## 布尔值

> include "true", "false"

#### 格式

```
{
  block: 'BOOLEAN',
  value: bool值,
}
```

#### example

```json
{
  "block": "BOOLEAN",
  "value": true
}
```

[Back To Top](#logic)

## 空值

> NULL

#### 格式

```
{
  block: 'LOGIC_NULL'
}
```

#### example

```json
{
  "block": "LOGIC_NULL"
}
```

[Back To Top](#logic)

## repeat循环

> repeat n times do something

#### 格式

```
{
  block: 'LOOP_REPEAT',
  times: 循环次数,
  branch: 循环体
}
```

#### example

```json
{
  "block": "LOOP_REPEAT",
  "times": {
    "block": "NUMBER",
    "value": 10,
  },
  "branch": {
    "block": "IF",
    "condition_number": 1,
    "conditions": [
      "false", ""
    ]
  }
}
```

[Back To Top](#logic)

## while循环

#### 格式

```
{
  block: 'LOOP_WHILE',
  condition: 循环条件,
  branch: 循环体
}
```

#### example

```json
{
  "block": "LOOP_WHILE",
  "condition": {
    "block": "COMPARE",
    "type": "==",
    "left": "true",
    "right": "false"
  },
  "branch": {
    "block": "IF",
    "condition_number": 1,
    "conditions": [
      "false", ""
    ]
  }
}
```

[Back To Top](#logic)

## until循环

#### 格式

```
{
  block: 'LOOP_UNTIL',
  condition: 循环条件,
  branch: 循环体
}
```

#### example

```json
{
  "block": "LOOP_UNTIL",
  "condition": {
    "block": "COMPARE",
    "type": "==",
    "left": "true",
    "right": "false"
  },
  "branch": {
    "block": "IF",
    "condition_number": 1,
    "conditions": [
      "false", ""
    ]
  }
}
```

[Back To Top](#logic)

## for循环

#### 格式

```
{
  block: 'LOOP_FOR',
  var_name: 循环变量名字,
  var_start: 循环起点,
  var_end: 循环终点,
  var_step: 循环步长,
  branch: 循环体
}
```

#### example

```json
{
  "block": "LOOP_FOR",
  "var_name": "i",
  "var_start": {
    "block": "NUMBER",
    "value": 10
  },
  "var_end": {
    "block": "NUMBER",
    "value": 20
  },
  "var_step": {
    "block": "NUMBER",
    "value": 1
  },
  "branch": {
    "block": "IF",
    "condition_number": 1,
    "conditions": [
      "false", ""
    ]
  }
}
```

[Back To Top](#logic)

## 循环控制

> include `BREAK` and `CONTINUE`

#### 格式

```
{
  block: 'LOOP_FLOW_CONTROLS',
  type: 控制类型
}
```

#### example

```json
{
  "block": "LOOP_FLOW_CONTROLS",
  "type": "BREAK"
}
```

[Back To Top](#logic)

## 数字

#### 格式

```
{
  block: 'NUMBER',
  value: 数字的值
}
```

#### example

```json
{
  "block": "NUMBER",
  "value": 12
}
```

[Back To Top](#math)

## 四则运算

> include ADD, MINUS, MULTIPLY, DIVIDE, POWER, MOD

#### 格式

```
{
  block: 'MATH_OPERATOR',
  type: 运算符号,
  left: 左值,
  right: 右值
}
```

#### example

```json
{
  "block": "MATH_OPERATOR",
  "type": "ADD",
  "left": {
    "block": "NUMBER",
    "value": 12
  },
  "right": {
    "block": "NUMBER",
    "value": 20
  }
}
```

[Back To Top](#math)

## 数学方法

> 包括 三角函数 常用数学函数 取整函数

> 三角函数的输入输出全为角度

#### 包含以下内容

| 标签 | 解释 | 对应函数 |
| --- | --- | --- |
| ROOT | 平方根 | Math.sqrt(x) |
| ABS | 绝对值 | Math.abs(x) |
| NEG | 负数 | -1 * x |
| LN | 自然对数 | Math.log(x) |
| LOG10 | 常用对数 | Math.log(x) / Math.log(10) |
| EXP | e^x | Math.exp(x) |
| POW10 | 10^x | Math.pow(10, x) |
| ROUND | 四舍五入 | Math.round(x) |
| ROUNDUP | 向上取整 | Math.ceil(x) |
| ROUNDDOWN | 向下取整 | Math.floor(x) |
| SIN | 正弦 | Math.sin(x / 180 * Math.PI) |
| COS | 余弦 | Math.cos(x / 180 * Math.PI) |
| TAN | 正切 | Math.tan(x / 180 * Math.PI) |
| ASIN | 反正弦 | Math.asin(x) / Math.PI * 180 |
| ACOS | 反余弦 | Math.acos(x) / Math.PI * 180 |
| ATAN | 反正切 | Math.atan(x) / Math.PI * 180 |

#### 格式

```
{
  block: 'MATH_FUNCTION',
  type: 运算标签,
  value: 运算值
}
```

#### example

```json
{
  "block": "MATH_FUNCTION",
  "type": "ROOT",
  "value": {
    "block": "NUMBER",
    "value": 4
  }
}
```

[Back To Top](#math)

## 数学常数

> 包括常用的数学常数

#### 包含以下内容

| 标签 | 解释 | 对应函数 |
| --- | --- | --- |
| PI | 圆周率 | Math.PI |
| E | 自然常数 | Math.E |
| GOLDEN_RATIO | 黄金分割率 | (1 + Math.sqrt(5)) / 2 |
| SQRT2 | 2的平方根 | Math.SQRT2 |
| SQRT1_2 | 1/2 的平方根 | Math.SQRT1_2 |
| INFINITY | 无限大 | Infinity |

#### 格式

```
{
  block: 'MATH_CONSTANT',
  type: 运算标签
}
```

#### example

```json
{
  "block": "MATH_CONSTANT",
  "type": "PI"
}
```

[Back To Top](#math)

## 数字检查

#### 包含以下内容

| 标签 | 解释 | 对应函数 |
| --- | --- | --- |
| PRIME | 是否是质数 | prime |
| EVEN | 是否是偶数 | x % 2 == 0 |
| ODD | 是否是奇数 | x % 2 == 1 |
| WHOLE | 是否是整数 | x % 1 == 0 |
| POSITIVE | 是否是正数 | x > 0 |
| NEGATIVE | 是否是负数 | x < 0 |
| DIVISIBLE_BY | 能否被整除 | x % y == 0 |

#### 格式

```
{
  block: 'MATH_NUMBER_CHECK',
  type: 运算标签,
  value1: 被检查值,
  value2: 整除的除数
}
```

#### example

```json
{
  "block": "MATH_NUMBER_CHECK",
  "type": "EVEN",
  "value1": 20
}
```

[Back To Top](#math)

## 随机数

> type 支持 int 和 float, float 没有区间

#### 格式

```
{
  block: 'MATH_RANDOM',
  type: 运算标签,
  min: 最小值,
  max: 最大值
}
```

#### example

```json
{
  "block": "MATH_RANDOM",
  "type": "INT",
  "min": 20,
  "max": 50
}
```

[Back To Top](#math)

## 文本

#### 格式

```
{
  block: 'TEXT',
  value: 文本的值
}
```

#### example

```json
{
  "block": "TEXT",
  "value": "Example String"
}
```

[Back To Top](#text)

## 合并文本

#### 格式

```
{
  block: 'TEXT_JOIN',
  text_number: 要合并的文本数量,
  texts: 文本的数组
}
```

#### example

```json
{
  "block": "TEXT_JOIN",
  "text_number": 2,
  "texts": [
    {
      "block": "TEXT",
      "value": "String1"
    },
    {
      "block": "TEXT",
      "value": "String2"
    }
  ]
}
```

[Back To Top](#text)

## 文本长度

#### 格式

```
{
  block: 'TEXT_LENGTH',
  text: 要计算长度的文本
}
```

#### example

```json
{
  "block": "TEXT_LENGTH",
  "text": {
    "block": "TEXT",
    "value": "String"
  }
}
```

[Back To Top](#text)

## 文本是否为空

#### 格式

```
{
  block: 'TEXT_ISEMPTY',
  text: 要判断的文本
}
```

#### example

```json
{
  "block": "TEXT_ISEMPTY",
  "text": {
    "block": "TEXT",
    "value": "String"
  }
}
```

[Back To Top](#text)

## 查找文本

| type | function |
| --- | --- |
| FIRST | indexOf |
| LAST | lastIndexOf |

#### 格式

```
{
  block: 'TEXT_INDEX_OF',
  type: 查找方式,
  text: 被查找文本,
  subString: 查找文本
}
```

#### example

```json
{
  "block": "TEXT_INDEX_OF",
  "type": "FIRST",
  "text": {
    "block": "TEXT",
    "value": "StringStringsubString"
  },
  "subString": {
    "block": "TEXT",
    "value": "subString"
  }
}
```

[Back To Top](#text)

## 获取文本中的字符

| type | function |
| --- | --- |
| FIRST | string.charAt(0) |
| LAST | string.slice(-1) |
| FROM_START | string.charAt(x) |
| FROM_END | string.slice(-x).charAt(0) |
| RANDOM | string[Math.floor(Math.random() * string.length)] |

#### 格式

```
{
  block: 'TEXT_CHAR_AT',
  type: 查找方式,
  text: 被查找文本,
  index: 获取字母的下标
}
```

#### example

```json
{
  "block": "TEXT_CHAR_AT",
  "type": "FROM_START",
  "text": {
    "block": "TEXT",
    "value": "StringStringsubString"
  },
  "index": {
    "block": "NUMBER",
    "value": 10
  }
}
```

[Back To Top](#text)

## 获取文本的子串

> use the function `string.slice(start - 1, end)`

> slice the substring of `[start, end]`

| type1 |
| --- |
| FIRST |
| FROM_START |
| FROM_END |

| type2 |
| --- |
| LAST |
| FROM_START |
| FROM_END |

#### 格式

```
{
  block: 'TEXT_GET_SUBSTRING',
  type1: 子串起始的类型,
  type2: 子串终止的类型,
  text: 被查找文本,
  index1: 获取子串的起始下标,
  index2: 获取子串的终止下标
}
```

#### example

```json
{
  "block": "TEXT_GET_SUBSTRING",
  "type1": "FROM_START",
  "type2": "FROM_START",
  "text": {
    "block": "TEXT",
    "value": "StringStringsubString"
  },
  "index1": {
    "block": "NUMBER",
    "value": 10
  },
  "index2": {
    "block": "NUMBER",
    "value": 15
  }
}
```

[Back To Top](#text)

## 转换大小写

| type | explain | function |
| --- | --- | --- |
| UPPERCASE | 转为大写 | string.toUpperCase() |
| LOWERCASE | 转为小写 | string.toLowerCase() |
| TITLECASE | 单词首字母大写 | function changeCase(str){return str.replace(/\S+/g,function(txt) {return txt[0].toUpperCase() + txt.substring(1).toLowerCase();});} |

#### 格式

```
{
  block: 'TEXT_CHANGE_CASE',
  type: 转换大小写方式,
  text: 改变文本
}
```

#### example

```json
{
  "block": "TEXT_CHANGE_CASE",
  "type": "UPPERCASE",
  "text": {
    "block": "TEXT",
    "value": "StringStringsubString"
  }
}
```

[Back To Top](#text)

## 获得变量

#### 格式

```
{
  block: 'VAR_GET',
  var_name: 变量名称
}
```

#### example

```json
{
  "block": "VAR_GET",
  "var_name": "my_1"
}
```

[Back To Top](#variables)

## 赋值变量

#### 格式

```
{
  block: 'VAR_SET',
  var_name: 变量名称,
  value: 赋的值
}
```

#### example

```json
{
  "block": "VAR_SET",
  "var_name": "my_1",
  "value": {
    "block": "NUMBER",
    "value": 10
  }
}
```

[Back To Top](#variables)

## 增加变量的值

#### 格式

```
{
  block: 'VAR_ADD',
  var_name: 变量名称,
  change: 改变的量
}
```

#### example

```json
{
  "block": "VAR_ADD",
  "var_name": "my_1",
  "change": {
    "block": "NUMBER",
    "value": -10,
  }
}
```

[Back To Top](#variables)

## 创建空线性表

#### 格式

```
{
  block: 'LIST_CREATE_EMPTY'
}
```

#### example

```json
{
  "block": "LIST_CREATE_EMPTY"
}
```

[Back To Top](#list)

## 创建包含一系列项目的线性表

#### 格式

```
{
  block: 'LIST_CREATE_WITH',
  item_num: 项目的数量,
  items: [所有项目...]
}
```

#### example

```json
{
  "block": "LIST_CREATE_WITH",
  "item_num": 3,
  "items": [
    {
      "block": "NUMBER",
      "value": 1
    },
    {
      "block": "NUMBER",
      "value": 2
    },
    {
      "block": "NUMBER",
      "value": 3
    }
  ]
}
```

[Back To Top](#list)

## 通过一个项目重复多次创建线性表

#### 格式

```
{
  block: 'LIST_CREATE_REPEAT',
  repeat_times: 重复的数量,
  item: 重复的项目
}
```

#### example

```json
{
  "block": "LIST_CREATE_REPEAT",
  "repeat_times": {
    "block": "NUMBER",
    "value": 10,
  },
  "item": {
    "block": "NUMBER",
    "value": 1
  }
}
```

[Back To Top](#list)

## 获得线性表的长度

#### 格式

```
{
  block: 'LIST_LENGTH',
  list: 要求长度的线性表
}
```

#### example

```json
{
  "block": "LIST_LENGTH",
  "list": {
    "block": "VAR_GET",
    "var_name": "my_list",
  }
}
```

[Back To Top](#list)

## 线性表是否为空

#### 格式

```
{
  block: 'LIST_IS_EMPTY',
  list: 需要判断的线性表
}
```

#### example

```json
{
  "block": "LIST_IS_EMPTY",
  "list": {
    "block": "VAR_GET",
    "var_name": "my_list",
  }
}
```

[Back To Top](#list)

## 查找线性表

| type | explain | function |
| --- | --- | --- |
| FIRST | 第一次出现的位置 | list.indexOf(x) + 1 |
| LAST | 最后一次出现的位置 | list.lastIndexOf(x) + 1 |

#### 格式

```
{
  block: 'LIST_INDEX_OF',
  list: 需要查找的线性表,
  type: 查找的类型,
  value: 需要查找的值
}
```

#### example

```json
{
  "block": "LIST_INDEX_OF",
  "type": "FIRST",
  "list": {
    "block": "VAR_GET",
    "var_name": "my_list",
  },
  "value": {
    "block": "NUMBER",
    "value": 20
  }
}
```

[Back To Top](#list)

## 获取/移除线性表元素

| mode | explain | function |
| --- | --- | --- |
| GET | 获取元素 | list\[x - 1\] |
| GET_REMOVE/REMOVE | 获取并移除/移除 | list.splice(x - 1, 1)\[0\] |

| type | explain | function |
| --- | --- | --- |
| FIRST | 第一次出现的位置 | list.shift() |
| LAST | 最后一次出现的位置 | list.splice(list.length - 1, 1) |
| FROM_START | 从开始的第 x 个 | list.splice(x - 1, 1) |
| FROM_END | 从末尾开始的第 x 个 | list.splice(list.length - x, 1) |
| RANDOM | 随机 | list[Math.floor(Math.random() * list.length)] |

#### 格式

```
{
  block: 'LIST_GET_INDEX',
  list: 需要查找的线性表,
  mode: 获取或是删除,
  type: 查找的类型,
  index: 获取或删除的下标
}
```

#### example

```json
{
  "block": "LIST_GET_INDEX",
  "mode": "GET",
  "type": "FIRST",
  "list": {
    "block": "VAR_GET",
    "var_name": "my_list",
  },
  "index": {
    "block": "NUMBER",
    "value": 2
  }
}
```

[Back To Top](#list)

## 添加/修改线性表元素

| mode | explain | function |
| --- | --- | --- |
| SET | 设置元素 | list\[x - 1\] = v |
| INSERT | 插入元素 | list.splice(x, 0, v)|

| type | explain | function |
| --- | --- | --- |
| FIRST | 第一次出现的位置 | list.unshift(v) |
| LAST | 最后一次出现的位置 | list.push(v) |
| FROM_START | 从开始的第 x 个 | list.splice(x, 0, v) |
| FROM_END | 从末尾开始的第 x 个 | list.splice(list.length - x + 1, 0, v) |
| RANDOM | 随机 | list.splice(Math.floor(Math.random() * list.length), 0, v) |

#### 格式

```
{
  block: 'LIST_SET_INDEX',
  list: 需要修改的线性表,
  mode: 添加或是修改,
  type: 修改的类型,
  index: 添加或修改的下标,
  value: 添加或修改的值
}
```

#### example

```json
{
  "block": "LIST_SET_INDEX",
  "mode": "SET",
  "type": "FIRST",
  "list": {
    "block": "VAR_GET",
    "var_name": "my_list",
  },
  "index": {
    "block": "NUMBER",
    "value": 2
  },
  "value": {
    "block": "NUMBER",
    "value": 10
  }
}
```

[Back To Top](#list)

## 设置链表坐标

#### 格式

```
{
  block: 'BASELIST_SET_POSITION',
  list: 需要修改的链表,
  x: x坐标,
  y: y坐标
}
```

#### example

```json
{
  "block": "BASELIST_SET_POSITION",
  "list": "list1",
  "x": {
    "block": "NUMBER",
    "value": 2
  },
  "y": {
    "block": "NUMBER",
    "value": 10
  }
}
```

[Back To Top](#base_list)

## 获得链表变量

#### 格式

```
{
  block: 'BASELIST_GET',
  var_name: 链表的名称
}
```

#### example

```json
{
  "block": "BASELIST_GET",
  "var_name": "list1"
}
```

[Back To Top](#base_list)

## 设置链表变量

#### 格式

```
{
  block: 'BASELIST_SET',
  var_name: 链表的名称,
  value: 链表
}
```

#### example

```json
{
  "block": "BASELIST_SET",
  "var_name": "list1",
  "value": {
    "block": "BASELIST_CREATE_FROM",
    "type": "RANDOM"
  }
}
```

[Back To Top](#base_list)

## 创建链表

| type | explian |
| --- | --- |
| RANDOM | 随机 |
| RANDOM_WITH_NODE_NUMBER | 确定结点数的随机 |
| FROM_LIST | 通过列表创建 |

#### 格式

```
{
  block: 'BASELIST_CREATE_FROM',
  type: 创建的方式,
  value: 结点数或是列表变量
}
```

#### example

```json
{
  "block": "BASELIST_GET",
  "type": "RANDOM_WITH_NODE_NUMBER",
  "value": {
    "block": "VAR_GET",
    "var_name": "list1"
  }
}
```

[Back To Top](#base_list)

## 获得结点变量

#### 格式

```
{
  block: 'BASENODE_GET',
  var_name: 结点变量的名称
}
```

#### example

```json
{
  "block": "BASENODE_GET",
  "var_name": "node1"
}
```

[Back To Top](#base_list)

## 设置结点变量

#### 格式

```
{
  block: 'BASENODE_SET',
  var_name: 结点变量的名称,
  node: 用来设置的结点或数字
}
```

#### example

```json
{
  "block": "BASENODE_SET",
  "var_name": "node1",
  "node": {
    "block": "NUMBER",
    "value": 20
  }
}
```

[Back To Top](#base_list)

## 获得当前结点

#### 格式

```
{
  block: 'BASELIST_GET_NOW_NODE',
  list: 获取当前结点的链表
}
```

#### example

```json
{
  "block": "BASELIST_GET_NOW_NODE",
  "list": {
    "block": "BASELIST_GET",
    "var_name": "list1"
  }
}
```

[Back To Top](#base_list)

## 移除下一个结点(显示上)

#### 格式

```
{
  block: 'BASELIST_REMOVE_NODE_ONVIEW',
  list: 需要移除的链表
}
```

#### example

```json
{
  "block": "BASELIST_REMOVE_NODE_ONVIEW",
  "list": {
    "block": "BASELIST_GET",
    "var_name": "list1"
  }
}
```

[Back To Top](#base_list)

## 删除被移除的结点

#### 格式

```
{
  block: 'BASELIST_REMOVE_NODE_REAL',
  list: 需要移除的链表
}
```

#### example

```json
{
  "block": "BASELIST_REMOVE_NODE_REAL",
  "list": {
    "block": "BASELIST_GET",
    "var_name": "list1"
  }
}
```

[Back To Top](#base_list)

## 移动到下一个结点

#### 格式

```
{
  block: 'BASELIST_MOVE_TO_NEXT',
  list: 需要向后移动的链表
}
```

#### example

```json
{
  "block": "BASELIST_MOVE_TO_NEXT",
  "list": {
    "block": "BASELIST_GET",
    "var_name": "list1"
  }
}
```

[Back To Top](#base_list)

## 将当前结点指向另外结点(显示上)

#### 格式

```
{
  block: 'BASELIST_NOW_POINT_TO_OTHER',
  list: 需要修改指向的链表,
  node: 指向的结点
}
```

#### example

```json
{
  "block": "BASELIST_NOW_POINT_TO_OTHER",
  "list": {
    "block": "BASELIST_GET",
    "var_name": "list1"
  },
  "node": {
    "block": "BASENODE_GET",
    "var_name": "node1"
  }
}
```

[Back To Top](#base_list)

## 将新节点指向另外结点(显示上)

#### 格式

```
{
  block: 'BASELIST_NEW_POINT_TO_OTHER',
  list: 需要修改指向的链表,
  node: 指向的结点
}
```

#### example

```json
{
  "block": "BASELIST_NEW_POINT_TO_OTHER",
  "list": {
    "block": "BASELIST_GET",
    "var_name": "list1"
  },
  "node": {
    "block": "BASENODE_GET",
    "var_name": "node1"
  }
}
```

[Back To Top](#base_list)

## 将新节点添加进链表(实际上)

#### 格式

```
{
  block: 'BASELIST_ADD_NEW_NODE_TRUE',
  list: 需要实际添加新节点的链表
}
```

#### example

```json
{
  "block": "BASELIST_ADD_NEW_NODE_TRUE",
  "list": {
    "block": "BASELIST_GET",
    "var_name": "list1"
  }
}
```

[Back To Top](#base_list)

## 获取新节点

#### 格式

```
{
  block: 'BASELIST_GET_NEW_NODE',
  list: 需要获取新节点的链表
}
```

#### example

```json
{
  "block": "BASELIST_GET_NEW_NODE",
  "list": {
    "block": "BASELIST_GET",
    "var_name": "list1"
  }
}
```

[Back To Top](#base_list)

## 生成新节点

#### 格式

```
{
  block: 'BASELIST_CREATE_NEW_NODE',
  list: 需要获取新节点的链表,
  node: 新节点的值
}
```

#### example

```json
{
  "block": "BASELIST_GET_NEW_NODE",
  "list": {
    "block": "BASELIST_GET",
    "var_name": "list1"
  },
  "node": {
    "block": "BASENODE_GET",
    "var_name": "node1"
  }
}
```

[Back To Top](#base_list)

## 获取链表节点数量

#### 格式

```
{
  block: 'BASELIST_GET_NODE_NUMBER',
  list: 需要获取节点数量的链表
}
```

#### example

```json
{
  "block": "BASELIST_GET_NODE_NUMBER",
  "list": {
    "block": "BASELIST_GET",
    "var_name": "list1"
  }
}
```

[Back To Top](#base_list)

## 获取链表当前结点的值

#### 格式

```
{
  block: 'BASELIST_GET_NOWNODE_VALUE',
  list: 需要获取当前结点的值的链表
}
```

#### example

```json
{
  "block": "BASELIST_GET_NOWNODE_VALUE",
  "list": {
    "block": "BASELIST_GET",
    "var_name": "list1"
  }
}
```

[Back To Top](#base_list)

## 判断当前结点是否是最后一个结点

#### 格式

```
{
  block: 'BASELIST_NOWNODE_IS_LAST',
  list: 需要判断当前结点是否是最后一个结点的链表
}
```

#### example

```json
{
  "block": "BASELIST_NOWNODE_IS_LAST",
  "list": {
    "block": "BASELIST_GET",
    "var_name": "list1"
  }
}
```

[Back To Top](#base_list)

## 获取结点的值

#### 格式

```
{
  block: 'BASENODE_GET_VALUE,
  node: 需要获取值的结点
}
```

#### example

```json
{
  "block": "BASENODE_GET_VALUE",
  "node": {
    "block": "BASENODE_GET",
    "var_name": "node1"
  }
}
```

[Back To Top](#base_list)

## 获取链表的下一个结点

#### 格式

```
{
  block: 'BASELIST_GET_NEXT_NODE,
  list: 需要获取下一个结点的链表
}
```

#### example

```json
{
  "block": "BASELIST_GET_NEXT_NODE",
  "node": {
    "block": "BASENODE_GET",
    "var_name": "node1"
  }
}
```

[Back To Top](#base_list)
