### :point_right:Xpath 选择器技巧
1、选择一个class属性不唯一的节点</br>
`<p class="msg ltype">`
- 选择其中一个属性即可
</br>`//p[contains(@class, 'msg')]`
- 用and链接，选择所有属性，更精确
</br>`//p[contains(@class, 'msg') and contains(@class,'ltype')]`

2、选择一个节点的兄弟节点
```markdown
<dt>主屏幕尺寸（英寸）</dt>
<dd>5.5英寸</dd>
```
  - 选择该节点后面所有兄弟
  </br>`//dt[text()='主屏幕尺寸（英寸）']/following-sibling::*`
  - 选择第一个兄弟
  </br>`//dt[text()='主屏幕尺寸（英寸）']/following-sibling::*[1]`
