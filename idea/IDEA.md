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


训练1HZ, 测试10Hz
夜景+路口

可微分上采样

FOV

对不同雷达的intensity分布进行重新调整

着重上采样层设计 可微分的上采样层

前视训练 全视角生成 说明具有泛化性能

利用点云分割结果 

点云特征？

解决图像截断的问题

Unet 感受野小的问题 加入膨胀卷积 和更多的skip connection

训练local和global 效率低 local无法直接使用global的结果 相当于重新训练