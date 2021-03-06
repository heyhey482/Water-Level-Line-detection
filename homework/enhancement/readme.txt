Histogram Equalization Practice

运行环境：matlab

实现内容：直方图均衡化以增强图像对比度

HE algorithm原理：
设图像对应灰度直方图用离散函数 h 表示，n为图像总的像素数目，可求得概率密度函数和对应累计分布函数c。根据直方图均衡的基本原理，原图像灰度值f到g的映射函数为：g=fmin+(fmax一fmin)*c。
缺陷：因为直方图均衡化后，不论原图像的均值是多少，处理后的图像均值均在灰度最大值和灰度最小值的中间值附近。而且由于原图像中各灰度级的概率密度不同，在均衡化后会出现灰度简并的现象，导致部分细节信息丢失和过增强现象的出现。

改进：双直方图均衡
保持亮度均值的双直方图均衡是以平均亮度fm为门限，将原图像分解为两个子图像f1与f2，即原图像中所有灰度值小于均值fm的像素形成子图f1，所有灰度值大于均值的像素形成子图f2，对两个子图像f1和f2分别统计直方图，对f1在灰度范围 [fmin，fm]上进行均衡，对f2在灰度范围 [fm，fmax]上进行均衡，得到处理后的子图像为g1与 g2。
