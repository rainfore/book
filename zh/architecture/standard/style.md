## 全局样式问题

import-global-loader

## normalize vs reset
normalize.css
reset.css

1. 不能直接使用tag来控制样式，因为一个DOM节点可能对应该多个样式，不想让tag样式影响到其他地方，如: ul>li, ul>li.custom；
2. 不能透传，证：因为1，所以必须要有class，既然有了class，显然就没必要透传；
3. 给tag黑白名单：ul,li,a，为每个标签都写组件成本太大；
4. 介于normalize.css和reset.css的一套默认样式的规范。

``` html
<u-link>Link</u-link>
<u-h1>H1</u-h1>
```

## 不要层叠

Bad:

``` scss
.root {
    .title {}

    .item {

    }
}
```

Good:

``` css
.root {

}

.title {}

.item {}
```

## margin问题

有三种：
- 全部向前：首个组件不可控
- +向前：不可控
- 全部向后

选择：
- 全部向后，某些情况下消除最后

## 属性的好处

.root .item {}

###

// 干掉
.u-btn // 1
.u-btn-primary // 1
.u-btn-white // 1

.u-btn // 1


.u-btn:hover // 2
.u-btn-primary // 1
.u-btn-primary:hover // 2
.u-btn-primary:disabled // 2

.u-btn:hover // 2

// good
.u-btn // 1
.u-btn[color="primary"] // 2
.u-btn[color="primary"]:hover // 3
.u-btn[color="primary"]:disabled // 3

.u-btn:hover // 2



###

.button { // 1
    background: green;
}

.button:hover {
    background: red;
}

.modal {

}

.modal_324233 {

}

.modal .modal_523523 { // 2
    background: red;
}
