---
title: 功能介绍
category: Nirvana
order: 4
---

### 变量

<details>
  <summary>全局变量</summary>
全局变量（Global variables）的作用域是在整个工作空间,作为系统默认的变量存在。  
</details>
<details>
  <summary>环境变量</summary>
环境变量（Environment variables）的作用域是用例执行时所选择的环境内，如果一个key即存在全局变量中，又存在环境变量中，优先使用环境变量的值。
  <p>
    <em>环境，在实际测试中会有多套环境，包括测试环境、预生产环境、或者针对不同版本的环境，每个环境对应的一些变量如请求地址、用户信息和中间件地址等都不相同，为了避免每测试一个环境都要手动修改相关数据，引入环境概念。
    </em>
  </p>
</details>
<details>
  <summary>引用变量</summary>
通过特殊符号$引用变量，例如$Variables
</details> 

  
### 脚本
<details>
  <summary>概念</summary>

脚本是一种灵活的，强大的辅助接口请求的方式，脚本分为：预定义脚本和自定义脚步。 

<li>预定义脚本：提前内置写好的脚本，我们可以把一些普遍通用的功能写成预定义脚本放在那里，方便大家使用。</li>
<li>自定义脚本：用户自己写的脚本，根据用户自己的实际情况编写脚本，然后上传到服务器，然后进行调用。</li>

</details>
<details>
  <summary>引用脚本</summary>
引用脚本的方法：${get_message_center_token()}，通过此方式平台会去执行get_message_center_token()这个函数。
</details>  

 
### 响应断言
  Nirvana 可以解析多层嵌套的json数据，从中抽取指定的信息，将“期望值”与“实际值”通过“匹配规则”进行比对，判断接口执行是否成功。
<details>
  <summary>解析响应</summary>
<li>默认提供:</li>  
  
Key | 描述
---|---
content|响应体全部，json格式多级content.person.name.first_name
status_code | 响应状态码
elapsed| 响应时间days, seconds, microseconds, total_seconds
headers|响应头headers.content-type
cookies|cookies

---
title: 功能介绍
category: Nirvana
order: 4
---
</details>

- 默认提供：  




- 可通过jsonpath解析：


JSONPath | 描述
---|---
$ | 根节点，用于表示一个json数据，可以是数组或对象
@| 当前节点对象
.or[]|取子节点
..|不管位置，选择所有符合条件的条件
*|匹配所有元素节点
[]	|迭代器标示（可以在里边做简单的迭代操作，如数组下标，根据内容选值等）
[,]|支持迭代器中做多选
?()|支持过滤操作
()|支持表达式计算

- 支持正则表达式


##匹配规则 Match Rules

规则 | 描述
---|---
equals | 判断实际结果和期望结果是否相等
less_than| 判断实际结果小于期望结果
less_than_or_equals|判断实际结果小于等于期望结果
greater_than|判断实际结果大于期望结果
greater_than_or_equals|判断实际结果大于等于期望结果
not_equals	|判断实际结果和期望结果不相等
string_equals|判断转字符串后，实际结果和期望结果是否相等
length_equals|判断长度（字符串、列表、字典）




 
