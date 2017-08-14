# 链接，Button这种组件要不要封装

必须封装，a必须要有个class

``` html
<button class="v-button">Test</button>
<a class="v-button" href="fwefewf">Test</a>

<ul>
    <li>Test</li>
    <li>Test</li>
    <li>awbwe</li>
    <li>wfew</li>
</ul>

<u-button href="http://rest.test.com">Test</u-button>
```

## ListView

``` html
<u-list-view>
    <u-list-view-item>xxx</u-list-view-item>
    <u-divider />
    <u-list-view-item>xxx</u-list-view-item>
</u-list-view>
```

``` html
<u-list-view>
    <u-list-view-item class="u-item">xxxx</u-list-view-item>
    <u-list-view-item class="u-item">abcd</u-list-view-item>
    <u-list-view-item class="u-item">xxxx</u-list-view-item>
</u-list-view>
```

VS

``` html
<u-list-view :list="list">
    <template slot="item" scope="props">
        <u-list-view-item class="xxx">{{ props.text }}</u-list-view-item>
    </template>
</u-list-view>
```

u-list-view对处理过多数据有效


## 组件属性命名
优先使用有意义的，如list, tree, date, color,
然后再使用没有意义的，如data, value等

## 组件命名

- Sidebar
- SidebarItem


先不实现button的href和to属性。


## slot

slot只更换内容

bad
``` html
<div class="$style.title">
    <slot name="title">{{ title }}</slot>
</div>
```

good
``` html
<slot name="title">
    <div class="$style.title">
    {{ title }}
    </div>
</slot>
```

## 组件继承

异名继承

HTML -> 存在则覆盖
JS -> extend增加
CSS -> @import增加
MD -> 存在则覆盖

同名继承

HTML -> 存在则覆盖
JS -> export继承
CSS -> 直接补充 or @import增加
MD -> 存在则覆盖

### 直接补充 vs @import增加

@import增加：
- 思路清晰bug少
- 代码要复制几份
- hash值不好追踪
- 要手动添加@import
