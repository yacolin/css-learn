# padding

## padding与元素尺寸
因为CSS中默认的box-sizing是content-box，所以使用padding会增加元素尺寸

### 错误的认知：内联元素的padding只会影响水平方向，不会影响垂直方向。
上述认知是错误的，内联元素的padding在垂直方向同样会影响布局，影响布局表现。只是因为内联元素没有可视宽度和可视高度的说法（clientHeight 和 clientWidth永远是0）垂直方向的行为表现完全受line-height和vertical-align的影响，视觉上并没有改变和上一行下一行内容的间距，因此给我们的感觉会是垂直的padding没有起作用。

### 内联元素的padding利用
* 在不影响当前布局的情况下，优雅的增加链接或者按钮的点击区域大小。
* 实现高度可控的分隔线。


## padding的百分比值
padding属性值是不支持负值的；padding支持百分比值，padding百分比值无论是水平方向还是垂直方向均是相对于宽度计算的。


## 标签元素内置的padding
* ol/ul列表内置padding-left，但是单位是px不是em
* 很多表单元素都内置padding
	
	* 所有浏览器 input / textarea 输入框内置padding
	* 所有浏览器 button 按钮内置padding
	* 部分浏览器 select 下拉内置padding ，如Firefox、IE8及以上版本浏览器可以设置padding
	* 所有浏览器 radio / checkbox 单复选框无内置padding
	* button元素按钮的padding最难控制


## padding与图形绘制
