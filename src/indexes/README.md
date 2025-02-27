---
title: Indexes 索引
description: 用于页面中信息快速检索，可以根据目录中的页码快速找到所需的内容。
spline: navigation
isComponent: true
---

<span class="coverages-badge" style="margin-right: 10px"><img src="https://img.shields.io/badge/coverages%3A%20lines-88%25-blue" /></span><span class="coverages-badge" style="margin-right: 10px"><img src="https://img.shields.io/badge/coverages%3A%20functions-87%25-blue" /></span><span class="coverages-badge" style="margin-right: 10px"><img src="https://img.shields.io/badge/coverages%3A%20statements-85%25-blue" /></span><span class="coverages-badge" style="margin-right: 10px"><img src="https://img.shields.io/badge/coverages%3A%20branches-65%25-red" /></span>
## 引入

全局引入，在 miniprogram 根目录下的`app.json`中配置，局部引入，在需要引入的页面或组件的`index.json`中配置。

```json
"usingComponents": {
  "t-indexes": "tdesign-miniprogram/indexes/indexes",
  "t-indexes-anchor": "tdesign-miniprogram/indexes-anchor/indexes-anchor"
}
```

## 代码演示

### 基础索引


{{ base }}

### 自定义索引

{{ custom }}

### API
### Indexes Props

名称 | 类型 | 默认值 | 说明 | 必传
-- | -- | -- | -- | --
custom-style | String | - | `0.25.0`。自定义组件样式 | N
index-list | Array | - | `0.32.0`。索引字符列表。不传默认 `A-Z`。TS 类型：`string [] \| number[]` | N
list | Array | [] | 已废弃。索引列表的列表数据。每个元素包含三个子元素，index(string)：索引值，例如1，2，3，...或A，B，C等；title(string): 索引标题，可不填将默认设为索引值；children(Array<{title: string}>): 子元素列表，title为子元素的展示文案。。TS 类型：`ListItem[] ` `interface ListItem { title: string;  index: string;  children: { title: string; [key: string]: any} [] }`。[详细类型定义](https://github.com/Tencent/tdesign-miniprogram/tree/develop/src/indexes/type.ts) | N
sticky | Boolean | true | 索引是否吸顶，默认为true。TS 类型：`Boolean` | N

### Indexes Events

名称 | 参数 | 描述
-- | -- | --
select | `(indexes: { groupIndex: string; childrenIndex: number })` | 点击行元素时触发事件

### IndexesAnchor Props

名称 | 类型 | 默认值 | 说明 | 必传
-- | -- | -- | -- | --
custom-style | String | - | 自定义组件样式 | N
external-classes | Array | - | 组件类名，用于设置组件外层元素类名。`['t-class']` | N
index | String / Number | - | 索引字符 | N
