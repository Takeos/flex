# flex
flex布局


>注意，设为Flex布局以后，子元素的float、clear和vertical-align属性将失效。
>首先如果需要某个元素使用flex来排版的话，需要在自身设置flex，如下所示

```
<div flex >
    //code	
</div>
```

>box：设置子元素如何去分配空间。写在子元素。（默认可设置10个box）
>如果只有一个子元素设置了box:1甚至任意值，都会把盒子剩余的空间给他。
>如果子元素都设置了box:1，则去平均分配盒子的空间。
>如果子元素其中某个设置了box:2，则该元素是其他元素的两倍。

```
<div flex >
    <div box="1"></div>
    <div box="2">该元素是上面元素的两倍宽</div>
</div>
```

>dir：设置子元素在盒子中的排列方向。写在父元素。
>dir : row，默认值，正常排列，起点在左侧。
>dir : row-reverse，跟上面相反，起点在右侧。即反向排序
>dir : column，垂直排列，起点在上面。
>dir : column-reverse，跟上面相反，起点在下面。

```
<div flex dir="row-reverse">
    <div></div>
    <div></div>
</div>
```

>wrap：子元素默认是显示在一行，如果需要多行显示或者自动换行，则设置改属性。写在父元素。
>wrap : nowrap，默认值，单行显示。
>wrap : wrap ，多行显示，超过自动向下换行
>wrap : wrap-reverse，多行反转显示。

```
<div flex wrap="wrap">
    <div></div>
    <div></div>
</div>
```

>justify：设置子元素的对齐方式。写在父元素。
>justify : start，默认值，左对齐。
>justify : end ，右对齐
>justify : center，居中对齐
>justify : between，两端对齐
>justify : around，每个元素之间的间距相等，如果只有一个元素的时候，该值等效于’center’

```
<div flex justify="center">
    <div></div>
    <div></div>
</div>
```

>align：多行对齐方式。如果子元素只有一行，该属性不起作用，通过设置wrap : wrap来使元素换行。写在父元素。
>align : start，上对齐。
>align : end ，下对齐
>align : center，居中对齐
>align : between，上下对齐
>align : around，每个元素之间的间距相等
>align : stretch，height为auto的时候，铺满整个盒子

```
<div flex align="stretch" wrap="wrap">
    <div></div> 
    <div></div>
    <div></div> 
</div>
```

>items：这类似于justify属性，但是是另一个方向,justify如果是X轴对齐，这个可以看成是Y轴对齐。写在父元素。
>items : start，上对齐。
>items : end ，下对齐
>items : center，居中对齐
>items : baseline ，第一个子元素文字的基线对齐。
>items : stretch，height为auto的时候，铺满整个盒子

```
<div flex items="stretch">
    <div></div> 
    <div></div>
    <div></div> 
</div>
```

>order：排序，数值越小越靠前。可以有负数，默认值(或者不写)为0。写在子元素。（默认最大值到10）。

```
<div flex >
    <div order="2"></div> 
    <div order="3"></div>
    <div order="1"></div> 
</div>
```

>grow：根据比例来填充盒子。根据盒子剩下的空间，来分配给设置了该属性的元素。默认值为0，意思是该元素不索取父元素的剩余空间，如果值大于0，表示索取。值越大，索取的越厉害。（默认最大值到10）。
>比如盒子宽500，两个子元素分别宽100，那么剩下300，第一个元素设置了grow: 1，第二个元素设置了grow: 2；则把300分成3分，第一个占100，第二个占200。该属性写在子元素。

```
<div flex >    
    <div grow="1"></div>    
    <div grow="2"></div>
</div>
```

>shrink：根据比例来填充盒子。根据盒子超出的空间，来分配给设置了改属性的box，默认值为1，当父元素的宽度小于所有子元素的宽度的和时，子元素的宽度会减小。值越大，减小的越厉害。如果值为0，表示不减小，大小不变化。（默认最大值到10）。
>比如盒子宽度400，有3个子元素，每个子元素宽度为200，则200*3 =600，超出200，此时把第一个元素设置了shrink: 2，则把盒子分成了4分，其他元素各占1份，设置了该属性的元素占2份，那么超出的200，需要被这4分平分，设置了该属性的宽度是其他两个元素的2倍。同样该属性写在子元素。

```
<div flex >    
    <div shrink="1"></div>    
    <div shrink="2"></div>
</div>
```

>self：单独设置一个子元素的对齐方式。同样该属性写在子元素。。默认值为auto，表示继承父元素的items属性。其他使用方法同items完全一致。同样该属性写在子元素。

```
<div flex >    
    <div self="start"></div>    
    <div self="end"></div>
</div>
```

>另外在Flex中还有一个flex-basis：这是定义子元素的宽度，由于该属性需要写入具体的单位（px，em，% …），所以并没有写进去，需要的时候自己写上（注意兼容性），该属性会覆盖width，虽然可以通过width来设置宽度，但是如果子元素设置了例如 box 的属性，会导致width失效，就可设置该属性。

点击这里<http://itakeo.com/blog/2016/05/18/flexcss/?none=123>。
