---
title: NoticeBar 公告栏
description: 在导航栏下方，用于给用户显示提示消息。
spline: message
isComponent: true
---

<span class="coverages-badge" style="margin-right: 10px"><img src="https://img.shields.io/badge/coverages%3A%20lines-94%25-blue" /></span><span class="coverages-badge" style="margin-right: 10px"><img src="https://img.shields.io/badge/coverages%3A%20functions-100%25-blue" /></span><span class="coverages-badge" style="margin-right: 10px"><img src="https://img.shields.io/badge/coverages%3A%20statements-94%25-blue" /></span><span class="coverages-badge" style="margin-right: 10px"><img src="https://img.shields.io/badge/coverages%3A%20branches-88%25-blue" /></span>
## 引入

全局引入，在 miniprogram 根目录下的`app.json`中配置，局部引入，在需要引入的页面或组件的`index.json`中配置。

```json
"usingComponents": {
  "t-notice-bar": "tdesign-miniprogram/notice-bar/notice-bar"
}
```

## 代码演示

### 组件类型

纯文字的公告栏

{{ base }}

带图标的公告栏

{{ iconDemo }}

带操作的公告栏

{{ event }}

自定义样式的公告栏

{{ custom }}

自定义内容的公告栏

{{ customization }}

### 组件状态

公告栏类型有普通（info）、警示（warning）、成功（success）、错误（error）

{{ theme }}

### 可滚动公告栏

可滚动公告栏有水平（horizontal）和垂直（vertical）

{{ scrolling }}


## API
### NoticeBar Props

名称 | 类型 | 默认值 | 说明 | 必传
-- | -- | -- | -- | --
content | String / Array / Slot | - | 文本内容 | N
custom-style `v0.25.0` | String | - | 自定义组件样式 | N
direction | String | horizontal | 滚动方向。可选项：horizontal/vertical | N
external-classes | Array | - | 组件类名，分别用于设置 组件外层元素、文本内容、前缀图标、右侧额外信息、后缀图标 等元素类名。。`['t-class', 't-class-content', 't-class-prefix-icon', 't-class-extra', 't-class-suffix-icon']` | N
extra | String / Slot | - | 右侧额外信息 | N
marquee | Boolean / Object | false | 跑马灯效果。speed 指速度控制；loop 指循环播放次数，值为 -1 表示循环播放，值为 0 表示不循环播放；delay 表示延迟多久开始播放【仅在 direction='horizontal' 有效】。TS 类型：`boolean \| DrawMarquee` `interface DrawMarquee { speed?: number; loop?: number; delay?: number }`。[详细类型定义](https://github.com/Tencent/tdesign-miniprogram/tree/develop/src/notice-bar/type.ts) | N
prefix-icon | String / Boolean / Object / Slot | - | 前缀图标。值为字符串表示图标名称，值为 `false` 表示不显示前缀图标，值为 `'slot'` 表示使用插槽，值为 `Object` 类型，表示透传至 `icon`，不传表示使用主题图标。| N
suffix-icon | String / Object / Slot | - | 后缀图标。值为字符串表示图标名称，值为 `'slot'` 表示使用插槽。值为 `Object` 类型，表示透传至 `icon`，不传表示不显示后缀图标。 | N
theme | String | info | 内置主题。可选项：info/success/warning/error | N
visible | Boolean | false | 显示/隐藏 | N
default-visible | Boolean | false | 显示/隐藏。非受控属性 | N

### NoticeBar Events

名称 | 参数 | 描述
-- | -- | --
click | `(trigger: NoticeBarTrigger)` | 点击事件。[详细类型定义](https://github.com/Tencent/tdesign-miniprogram/tree/develop/src/notice-bar/type.ts)。<br/>`type NoticeBarTrigger = 'prefix-icon' \| 'content' \| 'extra' \| 'suffix-icon';`<br/>
