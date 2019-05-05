RPN的Anchors原理解析：
得到60*40的feature map之后
对于map上的每一个像素，分别由
- 1x1x18(9*2)卷积生成每个像素的9个Anchor的分类信息，即该Anchor是否有目标
- 1x1x36(9*4)卷积生成每个像素的9个Anchot的偏移信息(Dx,Dy,Dw,Dh)，这个信息是用来加到固定的Anchor上的，也就是说，在配置中，我们固定了Anchor有3个大小，3中尺度，共3*3=9个Anchor，但是这种固定大小的肯定是和GroundTruth