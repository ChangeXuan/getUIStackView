# getUIStackView
##Inherits From(继承关系)
- NSObject
- UIResponder
- UIView
- UIStackView

##Conforms To(遵循)
UIxxxx

##Import Statement(导入说明)
###SWIFT
```
import UIKit
```
###Availability(有效性)
允许在iOS 9.0 和后面的系统版本中使用

UIStackView这个类提供了一个提高效率的接口，用来对一行或一列的组合视图进行布局。StackView让你利用自动布局的力量，创建用户接口，就可以对设备的朝向，屏幕的尺寸，和任何一个改变在可获得的空间进行动态的适配。StackView管理着它的arrangedSubviews属性下的所有视图的布局。这些视图被布置相对于stackView的轴，排布的顺序是基于arrangedSubviews数组里的顺序。精确的布局变化依靠stackView的axis, distribution, alignment, spacing(轴线，分布，对齐，间隔)，和其他的属性<br>
<br>
![](https://developer.apple.com/library/ios/documentation/UIKit/Reference/UIStackView_Class_Reference/Art/uistack_hero_2x.png)<br>
<br>
去使用一个StackView,打开你想要编辑的那个Storyboard，从Object library中拖拽出一个Horizontal Stack View或Vertical Stack View，并放到你希望的位置上。下一步，将视图或控件拖入这个stackView的内容中。如果你需要继续添加视图和控件到你的stackView中，stackView的接口管理将会根据stack的内容duistackView进行调整。你也可以通过修改属性面板对stack的内容的外观进行调整<br>
<br>
> 备注<br>
你需要负责定义stackView的位置和尺寸(可选的)。stackView会根据内容来对布局和尺寸进行管理

##Stack View and Auto Layout(stackView和自动布局)
stackView使用Auto Layout来对视图的位子和尺寸进行排布。stackView with its edges along the stack’s axis 来对第一个和最后一个视图进行对齐。对于一个水平的stackView，意味着布局中的第一个视图的开始边界(左边界)被钉在了stackView的开始边界(左边界)，和布局中的最后一个视图的结束边界(右边界)被钉在了stackView的结束边界(右边界)。对于一个垂直的stackView，意味着视图的上端和下端分别对应着stackView的上端和下端。如果你设置stackView的layoutMarginsRelativeArrangement的属性为true，stackView将使用相关的边距来替代边界对其内容进行对齐。<br>
<br>
对于除了 UIStackViewDistributionFillEqually 分布以外的分布方式，stackView使用每一个被排布的视图的intrinsicContentSize属性，用来计算尺寸。<br>
UIStackViewDistributionFillEqually重新排布视图，使每个视图拥有相同的尺寸，以便填充stackView。如果可能，stackView会根据被排布的视图的原有尺寸进行拉伸来填充stackView。<br>
<br>
对于除了 UIStackViewAlignmentFill对齐方式以外的对齐方式，stackView使用每一个被排布的视图的intrinsicContentSize属性，用来计算尺寸。<br>
UIStackViewAlignmentFill重新排布视图，使每个视图拥有相同的尺寸，以便填充stackView。如果可能，stackView会根据被排布的视图的原有尺寸进行拉伸来填充stackView(垂直)。<br>

