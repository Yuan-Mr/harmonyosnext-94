大家好，欢迎回来鸿蒙5莓创图表组件的专场，我们这一期来讲解组合图组件中title属性的深度用法，带大家掌握标题模块的完整配置技巧！

* * *

### 一、show属性

作用：控制标题模块的显示与隐藏 类型：Boolean 默认值：true 可选值：true（显示标题）、false（隐藏标题） 使用场景：需要动态切换标题可见性时使用

```
title: {
  show: false  //隐藏整个标题模块
}
```

* * *

### 二、text属性

作用：设置主标题文本内容 类型：String 默认值：空字符串 使用场景：展示图表核心主题，如"2023年销售数据统计"

```
title: {
  text: "莓创科技用户分布图"  //主标题文字
}
```

* * *

### 三、subtext属性

作用：设置副标题补充说明 类型：String 默认值：空字符串 使用场景：添加辅助信息，如"数据截止至2023-12"

```
title: {
  subtext: "数据来源：国家统计局"  //灰色小字副标题
}
```

* * *

### 四、direction排版方向

作用：控制主副标题的排列方式 类型：String 默认值：'column' 可选值：

-   'column'（垂直排列，默认）
-   'row'（水平并排） 使用场景：窄屏设备适合垂直排列，宽屏可尝试水平布局

```
title: {
  direction: 'row'  //标题与副标题横向排列
}
```

* * *

### 五、itemGap间距控制

作用：设置主副标题之间的间隔距离 类型：Number 默认值：5 使用场景：当使用大字号时需要增大间距

```
title: {
  itemGap: 15  //增加标题间距
}
```

* * *

### 六、定位四要素（left/right/top/bottom）

作用：精准控制标题容器位置 类型：String | Number 默认值：'auto'（自动居中） 特殊值说明：

-   数字类型：像素值（如20）
-   字符串：百分比（如'20%'） 使用场景：需要标题靠左/右对齐时

```
title: {
  left: '10%',   //左侧留10%边距
  top: 30        //距离顶部30像素
}
```

* * *

### 七、offset偏移量

作用：微调标题位置（基于定位后的二次调整） 类型：Array 默认值：[0, -20] 参数说明：

-   第一个元素：水平偏移（正右负左）
-   第二个元素：垂直偏移（正下负上） 使用场景：精细调整标题位置

```
title: {
  offset: [10, -10]  //向右10px，向上10px
}
```

* * *

### 八、textStyle主标题样式

作用：定制主标题文本样式 子属性详解：

1.  color

-   类型：String
-   默认：#333
-   示例：'#2c7be5'（品牌色）

1.  fontSize

-   类型：Number
-   默认：36
-   建议：移动端建议24-28

1.  fontWeight

-   类型：String
-   默认：'bold'
-   可选：'normal' | 'lighter'

1.  textAlign

-   类型：String
-   默认：'center'
-   可选：'left' | 'right'

```
textStyle: {
  color: '#1a73e8',
  fontSize: 28,
  fontWeight: 'lighter',
  textAlign: 'left'
}
```

* * *

### 九、subtextStyle副标题样式

配置方式与textStyle相同，特殊注意：

-   默认字号28小于主标题
-   默认颜色为红色（可改为灰色更协调）

```
subtextStyle: {
  color: '#666',
  fontSize: 20,
  fontStyle: 'italic'  //添加斜体
}
```

* * *

### 十、rLevel渲染层级

作用：控制标题与其他元素的叠加顺序 类型：Number 默认值：20 使用场景：当标题被其他元素遮挡时提升层级

```
rLevel: 99  //确保标题在最顶层
```

* * *

### 十一、animationCurve动画曲线

作用：设置标题出现动画的缓动效果 类型：String 默认值：'easeOutCubic' 推荐值：'linear'（线性）、'bounceOut'（弹跳效果）

```
animationCurve: 'bounceOut'  //添加入场弹性动画
```

* * *

### 十二、animationFrame动画帧数

作用：控制动画流畅度的帧数设置 类型：Number 默认值：30 注意：值越大越流畅但消耗性能

```
animationFrame: 60  //高端设备启用高帧率
```

* * *

### 🌟 综合实战案例

```
const chart = new McPieChart({
  title: {
    show: true,
    text: "鸿蒙5设备占比",
    subtext: "2023年Q4数据快报",
    direction: 'row',
    itemGap: 20,
    left: 'center',
    top: 20,
    offset: [0, 10],
    textStyle: {
      color: '#1890ff',
      fontSize: 32,
      fontFamily: 'Microsoft YaHei'
    },
    subtextStyle: {
      color: '#666',
      fontSize: 22
    },
    animationCurve: 'elasticOut'
  }
});
```

该配置实现：

1.  横向排列的主副标题
1.  顶部居中+微调偏移
1.  定制化字体与品牌色
1.  弹性入场动画效果

* * *

好，这期讲到这里就结束了，希望大家能灵活运用title属性打造专业级图表标题！下期我们继续深入讲解图例(legend)模块的配置技巧，敬请期待！