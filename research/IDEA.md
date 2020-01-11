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

POINTNET 投影到前视图

stage1 补全上方点云
stage next 还原可见光图像

深度图 用log 近处的差距大 远处的差距小

集成插值+插值速度和精度 二维对比

可微分idw

光流约束

地面不平均阴影

lidar super resolution

通过修改反射率来控制样式

首先先生成有点云的部分 再补全

点云做分割 移除物体验证生成能力

加入原始点云的l w h信息

结果 车道线检测 分割 目标检测

testing比较多 用testing

** 训练前期阴影少；

object-level refine
ground-truth attention 

测评： Object-crop 计算FID；直接在生成图像上做OD/SEGMENTATION；PSNR；SSIM？
FID 全幅+object-level

Feature Loss抖动大 使用不同的学习率

不考虑颜色和材质 只考虑结构 颜色尽量均匀
（同一个patch中 只需要颜色相对亮度一致即可？ 不需要颜色绝对值相等？）
仅使用高层特征来做Feature matching

太阳方位角

prograssive discriminator

stage-2 refine

discriminator 判别调音的音效好坏

图像光流和点云光流一致性 flowmatching

3dconv Temporal domain

手标的 雷达采集的

点云分割某个目标之后再进行重建

做两部分光流的实验

museGAN-emotion

不同深度拼接

mmap分支和previsou图像分支用不同的网络结构

deep feature projection

点云分支数据增强 先random rotation 然后在特征投影之前再旋转回来

直接投影 丢失特征(如高度等)

考虑加入聚类

***2d图像重投影到3d点云 投影误差

相机死角 雷达生成

激光雷达+图像 去阴影

KITTI 过曝

feature matching loss 取不同的gamma值 选loss最小的那个进行判别

稠密投影 目标检测

普通提特征是抓住主要问题 GAN提特征是要抓住细节；使用pointnet更好的提取边界等特征；语义FM loss,是为了保证结构不变 而由于雷达缺少语义信息材质等可以通过生成来更好的表达;通常需要标定 如果发生位移相对 会对安全性造成很大的影响