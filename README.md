# css-layout
![](https://user-gold-cdn.xitu.io/2019/4/16/16a2474aad6a80e6?w=1110&h=596&f=png&s=68964)
### 单栏布局
[预览地址](https://luoyuda.github.io/css-layout/单栏布局.html)
```html
<!--公共样式-->
<style>
*{
  margin:0;
  padding:0;
}
.header,.banner,.footer{
  min-height: 50px;
  border-bottom: 1px solid #003300;
  background: #c6ffdd; /* fallback for old browsers */
  background: -webkit-linear-gradient(to right, #c6ffdd, #fbd786, #f7797d); /* Chrome 10-25, Safari 5.1-6 */
  background: linear-gradient(to right, #c6ffdd, #fbd786, #f7797d); /* W3C, IE 10+/ Edge, Firefox 16+, Chrome 26+, Opera 12+, Safari 7+ */
}
.parent{
  margin-bottom: 30px;
}
</style>
```
#### margin
##### 代码实现
```html
<!-- margin -->
  <div class='parent layout1'>
    <style>
      /* 
        margin + max-width
        1.子元素 设定 margin: 0 auto; 指定宽度
        或者 父元素设定 margin: 0 auto; 指定最大宽度 子元素宽度百分百
        实用性：兼容性好，需指定宽度
      */
      .layout1 .header,.layout1 .banner,.layout1 .footer{
        margin: 0 auto;
        max-width: 960px;
      }
      /* 或者父元素直接  margin: 0 auto; max-width: 960px; 子元素宽度百分百*/
    </style>
    <div class='header'>header</div>
    <div class='banner'> 
      <p>margin + max-width</p>
      <p>1.子元素 设定 margin: 0 auto; 指定宽度</p>
      <p>或者 父元素设定 margin: 0 auto; 指定最大宽度 子元素宽度百分百</p>
      <p>实用性：兼容性好，需指定宽度</p>
    </div>
    <div class='footer'>footer</div>
  </div>
```
##### 效果
![](https://user-gold-cdn.xitu.io/2019/4/16/16a243c7b758c789?w=1184&h=207&f=png&s=152201)
#### inline-block + text-align
##### 代码实现
```html
<!-- inline-block text-align -->
  <div class='parent layout2'>
    <style>
      /* 
        inline-block text-align width max-width
        1.设置 子元素 display:inline-block 最大宽度 和 宽度百分
        2.父元素 text-align: center
        实用性：兼容性好，需要设定父元素，且子元素需指定宽度
      */
      .layout2.parent{
        text-align: center;
      }
      .layout2 .header,.layout2 .banner,.layout2 .footer{
        max-width: 960px;
        width: 100%;
        display: inline-block;
      }
    </style>
    <div class='header'>header</div>
    <div class='banner'> 
      <p>inline-block text-align width max-width 兼容性好，需要设定父元素，且子元素需要指定宽度 </p>
      <p>1.设置 子元素 display:inline-block 最大宽度 和 宽度百分百</p>
      <p>2.父元素 text-align: center </p>
      <p>实用性：兼容性好，需要设定父元素，且子元素需指定宽度 </p>
    </div>
    <div class='footer'>footer</div>
  </div>
```
##### 效果
![](https://user-gold-cdn.xitu.io/2019/4/16/16a24588008adad9?w=1183&h=201&f=png&s=161083)
#### flexbox
##### 代码实现
```html
<!-- flexbox -->
  <div class='parent layout3'>
    <style>
      /* 
        flexbox
        1.父元素display:flex; 
        2.父元素 设定 子元素 排列方向 flex-direction: column;
        3.父元素 设定 子元素 根据交叉轴的对齐方式 align-items: center;
        4.子元素 设定宽度，最大宽度
        实用性：PC端ie9+ 移动端常用，写起来简洁明了
      */
      .layout3.parent{
        display:flex; 
        align-items: center;
        flex-direction: column;
      }
      .layout3 .header,.layout3 .banner,.layout3 .footer{
        max-width: 960px;
        width: 100%;
      }
    </style>
    <div class='header'>header</div>
    <div class='banner'> 
      <p>flexbox</p>
      <p>1.父元素display:flex; </p>
      <p>2.父元素 设定 子元素 排列方向 flex-direction: column;</p>
      <p>3.父元素 设定 子元素 根据交叉轴的对齐方式 align-items: center;</p>
      <p>4.子元素 设定宽度，最大宽度</p>
      <p>实用性：PC端ie9+ 移动端常用，写起来简洁明了</p>
    </div>
    <div class='footer'>footer</div>
  </div>
```
##### 效果
![](https://user-gold-cdn.xitu.io/2019/4/16/16a2459be914b6c0?w=1184&h=248&f=png&s=191712)
### 双栏布局
[预览地址](https://luoyuda.github.io/css-layout/两栏布局.html)
```html
<!--公共样式-->
<style>
    *{
      margin:0;
      padding:0;
    }
    .left{
      background-color: rgba(0, 0, 0, 0.1);
      width: 200px;
    }
    .right{
      background-color: rgba(0, 0, 0, 0.2);
    }
    .parent{
      margin-bottom: 30px;
      background: #c6ffdd; /* fallback for old browsers */
      background: -webkit-linear-gradient(to right, #c6ffdd, #fbd786, #f7797d); /* Chrome 10-25, Safari 5.1-6 */
      background: linear-gradient(to right, #c6ffdd, #fbd786, #f7797d); /* W3C, IE 10+/ Edge, Firefox 16+, Chrome 26+, Opera 12+, Safari 7+ */
    }
</style>
```
#### margin + float 
##### 代码实现
```html
  <!-- 浮动+边距 -->
  <div class='parent layout1'>
    <style>
      /* 
        float + margin
        1.浮动左列
        2.右列自适应，且设置margin-left
        实用性：兼容性好，但是浮动后超出无法顶开父容器高度
      */
      .layout1 .left{
        float:left;
      }
      .layout1 .right{
        margin-left: 200px;
      }
    </style>
    <div class="left">
      <p>left</p>
    </div>
    <div class="right">
      <p>float + margin</p>
      <p>1.浮动左列</p>
      <p>2.右列自适应，且设置margin-left</p>
      <p>实用性：兼容性好，但是浮动后超出无法顶开父容器高度</p>
    </div>
  </div>
```
##### 效果
![](https://user-gold-cdn.xitu.io/2019/4/16/16a245db3fd9802a?w=1186&h=104&f=png&s=84157)
#### float
##### 代码实现
```html
  <!-- 全浮动 -->
  <div class='parent layout2'>
    <style>
      /* 
        float + margin
        1.浮动左列 
        2.右列自适应, 右列负margin-left
        3.右列子元素正margin-left
        实用性：兼容性虽好，但是相当麻烦的方案，从布局角度看 右列 部分超到了 左列 部分，还额外需要一个子元素，父元素由于两个子元素都浮动，高度彻底塌陷，还额外需要清除浮动
      */
      .layout2 .left{
        float:left;
      }
      .layout2 .right{
        width: 100%;
        float: right;
        margin-left: -200px;
      }
      .layout2 .right-box{
        margin-left: 200px;
      }
      .layout2{
        height: 120px;
      }
    </style>
    <div class="left">
      <p>left</p>
    </div>
    <div class="right">
      <div class="right-box">
        <p>float + margin</p>
        <p>1.浮动左列 </p>
        <p>2.右列自适应, 右列负margin-left</p>
        <p>3.右列子元素正margin-left</p>
        <p>实用性：兼容性虽好，但是相当麻烦的方案，从布局角度看 右列 部分超到了 左列 部分，还额外需要一个子元素，父元素由于两个子元素都浮动，高度彻底塌陷，还额外需要清除浮动</p>
      </div>
    </div>
  </div>
```
##### 效果
![](https://user-gold-cdn.xitu.io/2019/4/16/16a245ed9ff95f54?w=1186&h=145&f=png&s=128147)
#### float + overflow
##### 代码实现
```html
  <!-- 浮动 overflow 触发BFC -->
  <div class='parent layout3'>
    <style>
      /* 
        float + overflow
        1.浮动左列，左列指定宽度
        2.右列overflow: hidden, 触发右列 BFC 模式
        3.父元素 overflow 之后，触发 BFC 模式，浮动后仍然可以撑开父容器高度
        实用性：兼容性好，较为常用的实现方式，基本没什么后遗症
      */
      .layout3{
        overflow: hidden;
      }
      .layout3 .left{
        float:left;
      }
      .layout3 .right{
        overflow: hidden;
      }
    </style>
    <div class="left">
      <p>left</p>
      <p>left</p>
      <p>left</p>
      <p>left</p>
      <p>left</p>
      <p>left</p>
    </div>
    <div class="right">
      <p>float + overflow</p>
      <p>1.浮动左列，左列指定宽度</p>
      <p>2.右列overflow: hidden, 触发右列 BFC 模式</p>
      <p>3.父元素 overflow 之后，触发 BFC 模式，浮动后仍然可以撑开父容器高度</p>
      <p>实用性：兼容性好，较为常用的实现方式，基本没什么后遗症</p>
    </div>
  </div>
```
##### 效果
![](https://user-gold-cdn.xitu.io/2019/4/16/16a2460ba18021a4?w=1181&h=139&f=png&s=132477)
#### 表格布局
##### 代码实现
```html
  <!-- 表格 -->
  <div class='parent layout4'>
    <style>
      /* 
        表格布局
        1.父元素设置 display:table; table-layout:fixed; 设置宽度
        2.子元素设置 table-cell
        3.左列设置宽度
        实用性，不需要用到浮动，高度不会塌陷，且可以实现双边等高布局，但是也只会是等高布局，无法设置左右列边距
      */
      .layout4 .parent{
        display: table;
        table-layout: fixed;
        width: 100%;
      }
      .layout4 .right,.layout4 .left{
        display: table-cell;
      }
    </style>
    <div class="left">
      <p>left</p>
    </div>
    <div class="right">
      <p>表格布局</p>
      <p>1.父元素设置 display:table; table-layout:fixed; 设置宽度</p>
      <p>2.子元素设置 table-cell</p>
      <p>3.左列设置宽度</p>
      <p>实用性：不需要用到浮动，高度不会塌陷，且可以实现双边等高布局，但是也只会是等高布局，无法设置左右列边距</p>
    </div>
  </div>
```
##### 效果
![](https://user-gold-cdn.xitu.io/2019/4/16/16a2461798851755?w=1185&h=126&f=png&s=115136)
#### flexbox布局
##### 代码实现
```html
  <!-- flexbox -->
  <div class='parent layout5'>
    <style>
      /* 
        flexbox
        1.父元素 display:flex
        2.左列设置宽度，右列flex:1
        3.右列flex:1
        4.align-items: start; 设置为 start 就不撑满
        实用性：PC端IE9+，简洁明了的布局方式，可以通过控制 align-items 实现等高或者不等高。
      */
      .layout5.parent{
        display: flex;
      }
      .layout5 .right{
        flex:1;
      }
    </style>
    <div class="left">
      <p>left</p>
    </div>
    <div class="right">
      <p>flexbox</p>
      <p>1.父元素 display:flex</p>
      <p>2.左列设置宽度，右列flex:1</p>
      <p>3.右列flex:1</p>
      <p>4.align-items: start; 设置为 start 就不撑满</p>
      <p>实用性：PC端IE9+，简洁明了的布局方式，可以通过控制 align-items 实现等高或者不等高。</p>
    </div>
  </div>
```
##### 效果
![](https://user-gold-cdn.xitu.io/2019/4/16/16a24625028093c9?w=1184&h=139&f=png&s=126051)
#### 网格布局
##### 代码实现
```html
  <!-- 网格布局 -->
  <div class='parent layout6'>
    <style>
      /* 
        网格布局
        1.父元素 设置 display:grid 
        2.父元素 设置 grid-template-columns: 200px 1fr; 实现 左列100px 右列自适应
        3.align-items: start; 设置为 start 就不撑满
        实用性：更加简洁，高效的二维布局方式，但是兼容性 ie11+ 还是相对蛋疼
      */
      .parent.layout6{
        display: grid;
        grid-template-columns: 200px 1fr;
      }
    </style>
    <div class="left">
      <p>left</p>
    </div>
    <div class="right">
      <p>网格布局</p>
      <p>1.父元素 设置 display:grid </p>
      <p>2.父元素 设置 grid-template-columns: 200px 1fr; 实现 左列100px 右列自适应</p>
      <p>3.align-items: start; 设置为 start 就不撑满</p>
      <p>实用性：更加简洁，高效的二维布局方式，但是兼容性 ie11+ 还是相对蛋疼</p>
    </div>
  </div>
```
##### 效果
![](https://user-gold-cdn.xitu.io/2019/4/16/16a2462b26411dc3?w=1186&h=116&f=png&s=114456)
### 三栏布局
[预览地址](https://luoyuda.github.io/css-layout/三栏布局.html)
```html
<!-- 公共样式 -->
  <style>
    *{
        margin:0;
        padding:0;
      }
      .left,.right{
        background-color: rgba(0, 0, 0, 0.1);
      }
      .parent{
        margin-bottom: 10px;
        background: #c6ffdd; /* fallback for old browsers */
        background: -webkit-linear-gradient(to right, #c6ffdd, #fbd786, #f7797d); /* Chrome 10-25, Safari 5.1-6 */
        background: linear-gradient(to right, #c6ffdd, #fbd786, #f7797d); /* W3C, IE 10+/ Edge, Firefox 16+, Chrome 26+, Opera 12+, Safari 7+ */
      }
  </style>
```
#### 圣杯布局
##### 代码实现
```html
  <!-- 圣杯布局 -->
  <div class="parent layout1">
    <style>
      /* 
        圣杯布局
        两边固定宽度，中间自适应
        1. 子元素都左浮动，父元素 padding 留出空间
        2. 中间元素宽度100%
        3. 左右元素相对定位 配合负边距
        缺点: 如果center部分宽度效于left部分，会造成布局塌陷，旁边两列不能自动填充高度
      */
      .layout1.parent{
        position: relative;
        padding-left: 100px;
        padding-right: 100px;
      }
      .layout1 .left,.layout1 .right{
        position: relative;
        height: 100px;
        width: 100px;
      }
      .layout1 .center{
        height: 300px;
        width:100%;
      }
      .layout1 .left,.layout1 .right,.layout1 .center{
        float: left;
      }
      .layout1 .left{
        left: -100px;
        margin-left: -100%;
      }
      .layout1 .right{
        right: -100px;
        margin-left: -100px;
      }
      .layout1{
        height: 300px;
      }
    </style>
    <div class="center">
      <p>圣杯布局</p>
      <p>两边固定宽度，中间自适应</p>
      <p>1. 子元素都左浮动，父元素 padding 留出空间</p>
      <p>2. 中间元素宽度100%</p>
      <p>3. 左右元素相对定位 配合负边距</p>
      <p>缺点: 如果center部分宽度效于left部分，会造成布局塌陷，旁边两列不能自动填充高度</p>
    </div>
    <div class="left">
      <p>left</p>
    </div>
    <div class="right">
      <p>right</p>
    </div>
  </div>
```
##### 效果
![](https://user-gold-cdn.xitu.io/2019/4/16/16a246686fe4562e?w=1165&h=311&f=png&s=283225)
##### 缺陷
![](https://user-gold-cdn.xitu.io/2019/4/16/16a24677779478b5?w=267&h=813&f=png&s=75245)
#### 双飞翼布局
##### 代码实现
```html
  <!-- 双飞翼布局 -->
  <div class="parent layout2">
    <style>
      /* 
        双飞翼布局
        圣杯布局的优化，实现内容和布局的分离
        1.在圣杯布局的基础上
        2.设定 parent 元素的最小宽度
        3.center 元素再增加一个子元素来撑开双边
        优点: 避免使用了无用的定位，由于父元素使用了 overflow 三个部分都能撑开高度
        缺点: 增加了一个 inner 层
      */
      .layout2.parent{
        min-width: 200px;
        overflow:hidden;
      }
      .layout2 .left,.layout2 .right{
        height: 100px;
        width: 100px;
      }
      .layout2 .center{
        width:100%;
        height: 300px;
      }
      .layout2 .left,.layout2 .right,.layout2 .center{
        float: left;
      }
      .layout2 .center .inner{
        margin: 0 100px;
      }
      .layout2 .left{
        margin-left: -100%;
      }
      .layout2 .right{
        margin-left: -100px;
      }  
    </style>
    <div class="center">
      <div class="inner">
        <p>双飞翼布局</p>
        <p>圣杯布局的优化，实现内容和布局的分离</p>
        <p>1.在圣杯布局的基础上</p>
        <p>2.设定 parent 元素的最小宽度</p>
        <p>3.center 元素再增加一个子元素来撑开双边</p>
        <p>优点: 避免使用了无用的定位，由于父元素使用了 overflow 三个部分都能撑开高度</p>
        <p>缺点: 增加了一个 inner 层</p>
      </div>
    </div>
    <div class="left">
      <p>left</p>
    </div>
    <div class="right">
      <p>right</p>
    </div>
  </div>
```
##### 效果
![](https://user-gold-cdn.xitu.io/2019/4/16/16a246814020aaa1?w=1164&h=388&f=png&s=357597)
#### 表格布局
##### 代码实现
```html
  <!-- 表格布局 -->
  <div class="parent layout3">
    <style>
      /* 
        表格布局
        1.父元素 diplay:table
        2.子元素 display: table-cell
        3.左右两边设置宽度，中间元素不设置宽度
        优点: 实现等高布局，兼容性很好,如果需要兼容flex不能用的情况，优先考虑此种实现
        缺点: 无法设置栏边距，等高布局无法改变，对SEO不友好
      */
      .layout3.parent{
        display: table;
        height: 150px;
        width: 100%;
      }
      .layout3 .left,.layout3 .right,.layout3 .center{
        display: table-cell;
      }
      .layout3 .left,.layout3 .right{
        width: 100px;
      }
      .layout3 .center{
        height: 300px;
      }
    </style>
    <div class="left">
      <p>left</p>
    </div>
    <div class="center">
      <p>表格布局</p>
      <p>1.父元素 diplay:table</p>
      <p>2.子元素 display: table-cell</p>
      <p>3.左右两边设置宽度，中间元素不设置宽度</p>
      <p>优点: 实现等高布局，兼容性很好,如果需要兼容flex不能用的情况，优先考虑此种实现</p>
      <p>缺点: 无法设置栏边距，等高布局无法改变，对SEO不友好</p>
    </div>
    <div class="right">
      <p>right</p>
    </div>
  </div>
```
##### 效果
![](https://user-gold-cdn.xitu.io/2019/4/16/16a24687558d582b?w=1165&h=385&f=png&s=354011)
#### flexbox 布局
##### 代码实现
```html
  <!-- flexbox -->
  <div class="parent layout4">
    <style>
      /* 
        flexbox布局
        1.父元素 diplay:flex
        2.左右两边 设置宽度
        3.中间元素 flex: 1
        4.父元素 align-items: stretch(填满)/start/end/center;控制是否填满等高
        优点：书写方便简洁，可以等高也可以不等高，基本就是一个属性设置的区别，移动端常用
        缺点：PC端IE10才开始支持
      */
      .layout4.parent{
        display: flex;
      }
      .layout4 .left,.layout4 .right{
        width: 100px;
      }
      .layout4 .center{
        flex: 1;
        height: 300px;
      }
    </style>
    <div class="left">
      <p>left</p>
    </div>
    <div class="center">
      <p>flexbox布局</p>
      <p>1.父元素 diplay:flex</p>
      <p>2.左右两边 设置宽度</p>
      <p>3.中间元素 flex: 1</p>
      <p>4.父元素 align-items: stretch(填满)/start/end/center;控制是否填满等高</p>
      <p>优点：书写方便简洁，可以等高也可以不等高，基本就是一个属性设置的区别，移动端常用</p>
      <p>缺点：PC端IE10才开始支持</p>
    </div>
    <div class="right">
      <p>right</p>
    </div>
  </div>
```
##### 效果
![](https://user-gold-cdn.xitu.io/2019/4/16/16a246a5d692508d?w=1165&h=390&f=png&s=356348)
#### 网格布局
##### 代码实现
```html
  <!-- 网格布局 -->
  <div class="parent layout5">
    <style>
      /* 
        网格布局
        1.父元素diplay:grid
        2.父元素设置 grid-template-columns
        3.align-items: stretch(填满)/start/end/center;控制是否填满等高
        优点：布局强大，二维布局能力出色，可以玩出很多骚操作。未来最流弊的布局方案了
        缺点：ie 谷歌一条街，打听打听谁是爹
      */
      .layout5.parent{
        display: grid;
        grid-template-columns: 100px 1fr 100px;
      }
      .layout5 .center{
        height: 300px;
      }
    </style>
    <div class="left">
      <p>left</p>
    </div>
    <div class="center">
      <p>网格布局</p>
      <p>1.父元素diplay:grid</p>
      <p>2.父元素设置 grid-template-columns</p>
      <p>3.align-items: stretch(填满)/start/end/center;控制是否填满等高</p>
      <p>优点：布局强大，二维布局能力出色，可以玩出很多骚操作。未来最流弊的布局方案了</p>
      <p>缺点：ie 谷歌一条街，打听打听谁是爹</p>
    </div>
    <div class="right">
      <p>right</p>
    </div>
  </div>
```
##### 效果
![](https://user-gold-cdn.xitu.io/2019/4/16/16a246af682d5674?w=1165&h=393&f=png&s=353970)
