# Opencv 图像处理

## 基础概念：
* 边界填充：cv2.copyMakeBorder(img, up,down,left,right, border_type=(常值， 边缘...))
* 图像融合：两张图片相加(shape相同) cv2.addWeighted(img1,w1,img2,w2)
* 图像平滑：`卷积均值滤波`cv2.blur() `方框滤波：cv2.boxFliter` ``