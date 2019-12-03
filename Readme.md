### 获取方式
- 直接在插件市场下载
- 通过npm安装：npm i adcell

### 使用方式

市场下载的在 script 中引用组件

```javascript
import adCell from '@/component/ADCell/ADCell.vue';
export default {
    components: {adCell}
}
```
通过npm安装的在 script 中引用组件

```javascript
import adCell from '@/node_modules/adcell/ADCell.vue';
export default {
    components: {adCell}
}
```
在 template 中使用组件

```html
<adCell text="普通"></adCell>
<adCell text="点击事件" @click="onClick"></adCell>
<adCell text="隐藏箭头" showArrow="false"></adCell>
```

### 属性说明
| 属性        | 类型   |  默认  |  备注 |
| --------   | :-----:  | :----:  | :----:  |
| text      | String  |   -    | 主标题 |
| detail    | String  |   -   | 副标题 |
| note    | String  |   -   | 子标题1 |
| note1    | String  |   -   | 子标题2 |
| note2    | String  |   -   | 子标题3 |
| note3    | String  |   -   | 子标题4 |
| note4    | String  |   -   | 子标题5 |
| note5    | String  |   -   | 子标题6 |
| showArrow | Boolean/String | true | 是否显示右侧箭头 |
| mustInput | Boolean/String | false | 是否显示必填红星 |
| icon | String | - | 左侧图标 |
| textColor | String | #5E5E5E | 主标题文字颜色 |
| detailColor | String | #B3B3B3 | 副标题文字颜色 |
| noteColor | String | #B3B3B3 | 子标题文字颜色 |
| backgroundColor | String | #FFFFFF | 组件背景色 |
| swipeOptions | Array | - | 左滑选项集合 |

### 事件说明
| 事件名称        | 说明    |  返回 |
| --------   | :-----:  | :----:  | :----:  |
| click      | 点击Item触发的事件  |   -    |
| swipeClick    | 点击左滑出来的按钮  |   e: {index, content.text}   |
| swipeChange    | 滑动状态改变事件  |   open：true/false   |