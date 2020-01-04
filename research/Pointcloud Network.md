PointNet
http://openaccess.thecvf.com/content_cvpr_2017/papers/Qi_PointNet_Deep_Learning_CVPR_2017_paper.pdf

PointNet++
http://papers.nips.cc/paper/7095-pointnet-deep-hierarchical-feature-learning-on-point-sets-in-a-metric-space.pdf
MSG：取不同半径的点的特征拼接在一起
MRG：高层少数点特征pool+低层对应这些少数点的多数点特征拼接

SehllNet
http://openaccess.thecvf.com/content_ICCV_2019/papers/Zhang_ShellNet_Efficient_Point_Cloud_Convolutional_Neural_Networks_Using_Concentric_Shells_ICCV_2019_paper.pdf

Octree guided CNN with Spherical Kernels for 3D Point Clouds
https://arxiv.org/pdf/1903.00343.pdf

PointCNN
邻居点feature和邻居点xyz提取的feature拼接，由于不同邻居点的顺序对生成不同的点集，学习一个排列矩阵，将邻居点顺序进行重新排列，从而实现点顺序的无关性质