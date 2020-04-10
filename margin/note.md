# margin


## margin合并
### 什么是margin合并： 块级元素的的上外边距（margin-top）与下外边距（margin-bottom）有时会合并为单个外边距。
* 块级元素
* 只发生在垂直方向（不考虑writing-mode）

### margin合并的三种场景
* 相邻的兄弟元素margin合并
* 父级元素和第一个/最后一个子元素
	
	阻止margin-top的合并
	* 父元素设置为块状格式化上下文元素
	* 父元素设置border-top值
	* 父元素设置padding-top值
	* 父元素和第一个子元素之间添加内联元素进行分隔

	阻止margin-bottom的合并
	* 父元素设置为块状格式化上下文元素
	* 父元素设置border-bottom值
	* 父元素设置padding-bottom值
	* 父元素和最后一个子元素之间添加内联元素进行分隔
	* 父元素设置height/min-height/max-height

* 空块级元素的margin合并
		
	阻止
	* 设置垂直方向的border
	* 设置垂直方向的padding
	* 里面添加内联元素
	* 设置height/min-height

### margin合并的计算规则
* 正正取最大值
* 正负值相加
* 负负取最小值（即绝对值最大值）

### margin合并的意义
兄弟元素：让图文信息的排版更加舒服自然
父子元素：在页面中任何地方嵌套或直接放入任何裸div，都不会影响原来的块状布局
自身：可以避免不小心遗落或者生成的空标签影响排版和布局


### margin:auto
* 如果一侧定值，一侧auto，则auto为剩余空间大小
* 如果两侧均是auto，则平分剩余空间。

为什么明明容器定高、元素定高，margin:auto却无法垂直居中？、
触发margin:auto计算有一个前提条件，就是width或height为auto时，元素是具有对应方向的自动填充特性。

### margin无效情形解析
* display计算值inline的非替换元素的垂直margin是无效，对于内联替换元素，垂直margin有效，并且没有margin合并问题。
* 表格中的tr 和 td 元素或者设置display计算值是table-cell或者table-row的的margin都是无效。
* margin合并的时候，更改margin的值可能是没有效果的。
* 绝对定位元素非定位方位的margin值“无效”。
* 定高容器的子元素的margin-bottom或者宽度定死的子元素的margin-right的定位“失效”。
* 鞭长莫及导致的margin无效（需要对float和overflow深入了解）。
* 内联特性导致的margin无效（需要对verti-align和盒模型深入了解）。
