RPN的Anchors原理解析：
得到60*40的feature map之后
对于map上的每一个像素，分别由
- 1x1x18(9*2)卷积生成每个像素的9个Anchor的分类信息，即该Anchor是否有目标
- 1x1x36(9*4)卷积生成每个像素的9个Anchot的偏移信息(Dx,Dy,Dw,Dh)，这个信息是用来加到固定的Anchor上的，也就是说，在配置中，我们固定了Anchor有3个大小，3中尺度，共3*3=9个Anchor，但是这种固定大小的肯定是和GroundTruth的大小不能完全匹配，而且负责生成这个Anchor的像素的位置和GroundTruth的中心位置也不能匹配，因此这第二个1x1卷积就是用来尽量的学到固定大小的Anchor和GT之间的大小的位置差距，从而使Proposal更加准确(当然没有Stage 2 的回归更准确，这里只是说相对的准确)。
在给每个像素生成固定Anchor之后，且在固定Anchor加上1x1conv的偏移之前，就要求RPN—_CLS_LOSS和RPN_PRED_LOSS
因此
