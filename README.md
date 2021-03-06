# Markdown
Markdown格式文档语法说明, 使用记录

[Markdown语法教程](https://markdown.com.cn/)  
[Markdown语法整理](https://guo365.github.io/study/Markdown.html)  


## 通用
### 标题
标题用`#`符号实现, `#`符号与标题内容间空一格, 几个`#`表示第几级标题, 标题内容后的空格非必须     

### 换行
在需要换行的内容后  
添加2个空格

### 空格
### space jump test
[如何在Markdown文档中插入空格?](https://www.cnblogs.com/klchang/p/10203404.html)  

半角模式下, 即使多个空格在markdown格式下也只显示一个, 可采用如下方法添加多个空格:     
 - 插入一个空格 (non-breaking space)  
    `&nbsp`; 或 `&#160`; 或 `&#xA0`;
 - 插入两个空格 (en space)  
    `&ensp`; 或 `&#8194`; 或 `&#x2002`;
 - 插入四个空格 (em space)  
    `&emsp`; 或 `&#8195`; 或 `&#x2003`;
 - 插入细空格 (thin space)  
    `&thinsp`; 或 `&#8201`; 或 `&#x2009`;

### 斜体字
两个单星号`*`符号中间文本为斜体字  
*我是斜体*

### 粗体字
两个双星号`**`符号中间文本为粗体字  
**我是粗体**

### 加粗加斜
两个三星号`***`符号中间文本为加粗加斜字  
***我是加粗加斜***

### 链接
<https://github.com>, 格式为`<链接地址>`  
[Github](https://github.com), 格式为`[链接名称](链接地址)`  

### <a name="image"></a> 图片
 - 插入图片  
格式为`![图片描述](图片地址)`, 图片描述在图片无法加载时显示, 图片地址可为网络地址或本地相对路径;  
此格式下点击图片会跳转到图片地址;  
![小鸡头像](./image/小鸡截图.png)  

- 插入并链接图片  
格式为`[![图片描述](图片地址)](链接URL)`, 即插入图片的格式嵌套到链接的链接名称中;  
此格式下点击图片会跳转到链接地址而非图片地址;  
[![小鸡头像](./image/小鸡截图.png)](http://wx1.sinaimg.cn/large/006szvLFgy1fwi58qhzm1j30b40b4q5h.jpg)  

### 符号列表
使用空格破折号空格组合` - `, 如果下行为非格式文本则符号列表行后要跟两个空格用以换行; 
符号列表行后紧邻的一行会跟符号列表对齐, 若不想请行后插入一空行;  
 - 跑步
 跑步后没加空格
- 跑步  
 跑步后加空格没插入空行, 会对齐  
 - 跑步  

跑步后插入空行

### 编号列表
使用`1. `符号组合  
1. 跑步
2. 骑车
3. 爬山

### 任务列表
使用`- [ ] `符号组合, 方括号中为为空格时标记为空, 为`x`时标记为完整  
- [ ] 跑步
- [x] 骑车
- [ ] 爬山

### 引用
使用`>`符号  
> 我是一行引用, 引用行尾也要添加空格才能自动换行    
>   
>> 嵌套引用  
>>> 多级嵌套引用  
> - 组合符号列表  
> - [x] 组合任务列表  

### 分隔线
要创建分隔线，请在单独一行上使用三个或多个星号`***`、破折号`---`或下划线`___` ，并且不能包含其他内容。  
为了兼容性，请在分隔线的前后均添加空白行。  

---

### 删除线
若要删除单词，请在单词前后分别添加双波浪号`~~`, 但Github README预览中不显示, 实际正文中是支持显示的   
 - 删除个别单词  
周末一起去~~爬山~~游泳怎么样  
 - 删除整段  
~~周末一起去爬山  
游泳怎么样~~  

### 页内跳转
[MarkDown技巧：两种方式实现页内跳转](https://www.cnblogs.com/JohnTsai/p/4027229.html)  
[如何实现Github markdown 目录/页内跳转？](https://www.zhihu.com/question/58630229)  

1. Github Flavored Markdow(GFM)
```
对于标题# Hello
正确的链接方式是[Hello](#hello)

对于标题 ## Hello World
正确的链接方式为[Hello World](#hello-world)

对于标题 ## 空格
正确的链接方式为[Hello World](#空格)

注意：()中的字母均为小写，单词之间有间隔用 '-' 连接
```
示例：[空格](#空格)
示例：[space jump test](#space-jump-test)

2. html标签实现
```
定义一个锚(id), `锚` 可以是 p 元素也可以是 a 元素也可以是 span 元素等等：  <a name="jump">跳转到的地方</a>  或 <span id="jump">跳转到的地方</span>
使用markdown语法：[点击跳转](#jump)
```
示例：[图片](#image)

### 突出显示
单个短语或单行: 使用单个反引号符号, 两个单反引号中间内容即为块  
 - 突出显示单个词语  
将`uint8_t`突出显示  

 - 突出显示整行  
`将本行突出显示`  

 - 突出显示段落
使用三个反引号符号, 两个三反引号中间内容即为块  
```
// for循环
uint8_t i = 0;
for(i = 0; i< 10; i++) {
}
```
针对代码, 紧跟第一个三反引号后添加c/java等可高亮特定语言的关键字  
```c
// for循环
uint8_t i = 0;
for(i = 0; i< 10; i++) {
}
```

## Github Issues
### 引用代码块
在仓库的Issue中引用仓库的部分源代码（某几行）：打开要引用的源代码文件，按住`shift`在代码左侧行号边选择，然后点击`···`选择`Copy permalink`，将复制的链接粘贴至Issue中即可实现插入引用代码框的效果。permalink链接内容如下所示，仅在Issue/PR的评论中可实现此效果，md文件中不可：
```
https://github.com/weycen/leetcode/blob/8cbeaa29a40ffb7a2bd76ec07d879fa7be3310c6/src/35.%E6%90%9C%E7%B4%A2%E6%8F%92%E5%85%A5%E4%BD%8D%E7%BD%AE.c#L79-L89
```
