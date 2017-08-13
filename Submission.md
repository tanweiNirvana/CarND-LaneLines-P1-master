
## Finding Lane Lines on the Road

1.**我的pipeline()分为6个步骤.**

**a.我将图片转换为 grayscale**

**b.将grayscale image 加入 gaussian blur ，这样是为了让我们关注具有强烈对比的图片中的边缘，减弱噪声边缘（noisy boundary）的影响**

**c.通过Canny edge Detection 算法对上面的图片进行边缘识别**

**d.然后通过cv2.fillPoly()划分一个区域，并只显示这个区域的边缘**

**e.通过Hough transform画出车道线**

**f.将车道线与原始图片结合起来，产生了识别车道线的图片**

2.
**为了在左，右通道上画一条线，我通过斜率（（y2-y1）/（x2-x1））修改了draw_lines（）函数，以决定哪些段是左侧线，和右侧线。 然后，我可以平均每条线的位置并推断到车道的顶部和底部.**

3.
**如果在车道上出现其他不明物体，可能导致车道线出现奇怪的变化，无法正常识别车道线**

