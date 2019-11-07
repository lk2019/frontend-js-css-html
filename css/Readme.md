## css基础
  ### 盒模型
   #### w3c模型
     width(height)=content
     转换形式:box-size:content-box
   #### ie模型
     width(height)=content+padding+border
     转换形式:box-size:border-box
  ### BFC
   #### 定义
     BFC(Block formatting context)直译为"块级格式化上下文"。它是一个独立的渲染区域，只有Block-level box参与， 它规定了内部的
     Block-level Box如何布局，并且与这个区域外部毫不相干。
   #### BFC作用
     1.解决外边距margin塌陷问题
     2.清除内部浮动问题
     3，避免文字环绕
     4.分属于不同的BFC时，可以阻止margin重叠
     5.多列布局中使用BFC
   #### 如何触发BFC
     1.根元素，即HTML元素（最大的一个BFC）
     2.float的值不为none
     3。position的值为absolute或fixed
     4.overflow的值不为visible（默认值。内容不会被修剪，会呈现在元素框之外，一般hidden用的比较多）
     5.display的值为inline-block、table-cell、table-caption
   #### BFC布局规则
     1.内部的Box会在垂直方向，一个接一个地放置。
     2.属于同一个BFC的两个相邻的Box的margin会发生重叠
     3.BFC就是页面上的一个隔离的独立容器，容器里面的子元素不会影响到外面的元素。反之也如此, 文字环绕效果，设置float
     4.BFC的区域不会与float box重叠。
     5.计算BFC的高度，浮动元素也参与计算
   ### float
   #### 规则
     1.元素"浮动"
     2.脱离文档流
     3.不脱离文本流
     4.位置尽量靠上，并靠左或右
     
   #### 对自己的影响
     1.形成"块"(BFC)
     2.这个块会负责自己的布局，宽高由自己决定
   #### 对兄弟元素的影响 
     1.上面一般贴非float元素
     2.靠边贴float元素或边
     3.不影响其他块级元素位置
     4.影响其他块级元素文本
   #### 对父级元素的影响
     1.从布局上"消失"
     2。高度塌陷
   #### 说明
     浮动的元素布局时不会占据父元素的布局空间，即父元素布局时不会管浮动元素，浮动元素有可能超出父元素，从而对其他元素造成影响。
     1.用overflow：hodden，定义width：0
     2.使用：：after
   ### css的单位
     1.px
     2.em   向上查找父元素字体，若没有，则是浏览器默认大小
     3，rem  根据根元素html字体
     4.%
     5vw/vh
   ### css优化性能
     1.多个 css 合并，尽量减少 HTTP 请求
     2.css 雪碧图
     3、抽象提取公共样式，减少代码量
     4、选择器优化嵌套，尽量避免层级过深 （用‘>’替换‘ ’）
     5.属性值为 0 时，不加单位
     6.压缩CSS代码
     7.避免使用 CSS 表达式
   ### link 与 @import 的区别
     1.link 是 HTML 方式， @import 是 CSS 方式
     2.link 最大限度支持并行下载，@import 过多嵌套导致串行下载，出现 FOUC
     3.link 可以通过 rel="alternate stylesheet" 指定候选样式
     4.浏览器对 link 支持早于@import ，可以使用 @import 对老浏览器隐藏样式
     5.@import 必须在样式规则之前，可以在 css 文件中引用其他文件
     总体来说：link 优于@import
