### Hello and welcome back to our special session on HarmonyOS 5 Berry Creative chart components! In this episode, we'll explore the in-depth usage of the `title` property in combined chart components, helping you master comprehensive configuration skills for the title module!  


### 一、`show` Property  
**Function**: Toggle the title module's visibility.  
**Type**: Boolean  
**Default**: `true`  
**Options**: `true` (show), `false` (hide)  
**Scenario**: Dynamically switch title visibility.  

```json
title: {
  show: false  // Hide the entire title module
}
```  


### 二、`text` Property  
**Function**: Set the main title text.  
**Type**: String  
**Default**: Empty string  
**Scenario**: Display the core chart theme (e.g., "2023 Sales Data Statistics").  

```json
title: {
  text: "Berry Creative User Distribution"  // Main title text
}
```  


### 三、`subtext` Property  
**Function**: Set supplementary sub-title text.  
**Type**: String  
**Default**: Empty string  
**Scenario**: Add auxiliary info (e.g., "Data as of 2023-12").  

```json
title: {
  subtext: "Data Source: National Bureau of Statistics"  // Gray sub-title text
}
```  


### 四、`direction` Layout Direction  
**Function**: Control main/sub-title arrangement.  
**Type**: String  
**Default**: `'column'`  
**Options**:  
- `'column'` (vertical, default)  
- `'row'` (horizontal)  
**Scenario**: Vertical for narrow screens; horizontal for wide screens.  

```json
title: {
  direction: 'row'  // Align title and sub-title horizontally
}
```  


### 五、`itemGap` Spacing Control  
**Function**: Set spacing between main and sub-titles.  
**Type**: Number  
**Default**: `5`  
**Scenario**: Increase spacing for larger font sizes.  

```json
title: {
  itemGap: 15  // Expand title spacing
}
```  


### 六、Positioning Properties (left/right/top/bottom)  
**Function**: Precisely control title container position.  
**Type**: String | Number  
**Default**: `'auto'` (auto-center)  
**Special Values**:  
- Number: Pixel value (e.g., `20`)  
- String: Percentage (e.g., `'20%'`)  
**Scenario**: Align title left/right.  

```json
title: {
  left: '10%',   // 10% left margin
  top: 30        // 30px from top
}
```  


### 七、`offset` Offset  
**Function**: Fine-tune title position (secondary adjustment).  
**Type**: Array  
**Default**: `[0, -20]`  
**Params**:  
- 1st element: Horizontal offset (positive=right, negative=left)  
- 2nd element: Vertical offset (positive=down, negative=up)  
**Scenario**: Precisely adjust title placement.  

```json
title: {
  offset: [10, -10]  // +10px right, -10px up
}
```  


### 八、`textStyle` Main Title Style  
**Function**: Customize main title text style.  
**Sub-properties**:  
1. `color`  
   - Type: String  
   - Default: `#333`  
   - Example: `'#2c7be5'` (brand color)  

1. `fontSize`  
   - Type: Number  
   - Default: `36`  
   - Tip: 24-28 for mobile.  

1. `fontWeight`  
   - Type: String  
   - Default: `'bold'`  
   - Options: `'normal'`, `'lighter'`  

1. `textAlign`  
   - Type: String  
   - Default: `'center'`  
   - Options: `'left'`, `'right'`  

```json
textStyle: {
  color: '#1a73e8',
  fontSize: 28,
  fontWeight: 'lighter',
  textAlign: 'left'
}
```  


### 九、`subtextStyle` Sub-title Style  
**Configuration**: Similar to `textStyle`, with notes:  
- Default font size `28` (smaller than main title).  
- Default color `red` (建议改为灰色 for harmony).  

```json
subtextStyle: {
  color: '#666',
  fontSize: 20,
  fontStyle: 'italic'  // Add italic style
}
```  


### 十、`rLevel` Rendering Layer  
**Function**: Control title overlay order with other elements.  
**Type**: Number  
**Default**: `20`  
**Scenario**: Increase layer when title is obscured.  

```json
rLevel: 99  // Ensure title is on top layer
```  


### 十一、`animationCurve` Animation Easing  
**Function**: Set title entry animation easing effect.  
**Type**: String  
**Default**: `'easeOutCubic'`  
**Recommendations**: `'linear'`, `'bounceOut'` (bounce effect).  

```json
animationCurve: 'bounceOut'  // Add elastic entry animation
```  


### 十二、`animationFrame` Animation Frames  
**Function**: Control animation smoothness (frame rate).  
**Type**: Number  
**Default**: `30`  
**Note**: Higher values = smoother but more performance-intensive.  

```json
animationFrame: 60  // Enable high frame rate for premium devices
```  


### 🌟 Comprehensive Practical Case  
```javascript
const chart = new McPieChart({
  title: {
    show: true,
    text: "HarmonyOS 5 Device Proportion",
    subtext: "2023 Q4 Data Brief",
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

**Configuration Achievements**:  
1. Horizontal main/sub-title layout  
2. Top-center positioning with fine-tuned offset  
3. Custom fonts and brand colors  
4. Elastic entry animation effect  


### Conclusion  
This wraps up our guide to crafting professional chart titles with the `title` property! Stay tuned for the next episode, where we'll dive into legend module configuration techniques. See you then! 🚀
