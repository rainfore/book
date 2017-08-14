# 命名学

类名、对象名、标签名等等最好一致，能够一一对应。

## 组件tag命名
1. 无特点：不好实现，可能会与原生的有冲突。而且Vue会阻止；
2. 大驼峰：貌似不合群，与原生冲突的Vue同样会提示；
3. 前缀连字符：OK，u-前缀应该比较适合。
4. `<u:`不合适

Good:

``` html
<u-button>Test</u-button>
<u-list>
    <u-item>Test</u-item>
    <u-item>Test</u-item>
    <u-item>Test</u-item>
    <u-item>Test</u-item>
</u-list>
<u-progress></u-progress>
<u-input></u-input>
```

Bad:

``` html
<progress-bar></progress-bar>
<date-picker></date-picker>
<input-field></input-field>
```

## 样式命名

.u-progress
.u-progress[status="primary"]
.u-progress_bar { }

## name是否要注册
组件都写上name

## 命名空间

不是u-开头的是浏览器的原生组件
是u-开头的是Vusion组件
u-命名空间中的基类组件是唯一的。

其他在该组件基础上衍生，API只增不减。

## 结论

- 类　名：CamelCase
- 对象名：camelCase
- 文件名：u-kabel-case
- 标签名：u-kabel-case
- 样式名：u-kabel-case
