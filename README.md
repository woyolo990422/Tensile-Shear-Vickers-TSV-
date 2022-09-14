# Tensile-Shear-Vickers-TSV-

通过第一性原理计算结构的拉伸，剪切，以及维氏压头侵入时的剪切响应

需要使用到VESTA和VASP，以及一点linux下Shell的命令

目前为测试版，功能较为简单。


###########################################
使用方法
###########################################

1.以金刚石为例，优化结构后将POSCAR INCAR POTCAR Tensile Shear Vickers(取决于算哪一个)

2.通过VESTA改变结构的方向，XX为拉伸方向，XZ为剪切方向，如要在111 11-2方向则需要在Unit Cell Transformation里更改Rotation matrix P 为：

1 1 1

1 -1 1

1 0 -2

3.对方向的优化选择后进行计算，结果在KB里，顺序为XX YY ZZ XY YZ XZ 最后为结构位移

4.对于Vickers的计算，需要考虑σzz，具体请看“Large indentation strain stiffening in nanotwinned
cubic boron nitride”这篇文章，通过一定的角度比例可以将结构按照指定方向压缩，这里需要参考VASP_OPT_AXIS的方法，具体编译请从网上查找


