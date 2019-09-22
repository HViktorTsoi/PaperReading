1. 结合大量信息 补全点云数据(3d GAN?)
2. 1 在object区域加attention，专注refine这些区域
夜间 过曝光 相机镜头污染

WGAN的loss无法直接优化，只能先转化为sup形式，这样必须满足1-李普希兹连续约束

discriminator 加attention

测试时 不同的前视投影生成不同的视角的图像

structure loss， 保留结构

可见光场景重建

texture loss 反射率和颜色的对应关系

related works 可行性说明

扩张视角

query x key
第i个点 最应该关注第j个点
value j个点的值(关注度是多少)

![title](https://raw.githubusercontent.com/HViktorTsoi/gitnote-image/master/gitnote/2019/09/22/1569160167727-1569160167740.png)
