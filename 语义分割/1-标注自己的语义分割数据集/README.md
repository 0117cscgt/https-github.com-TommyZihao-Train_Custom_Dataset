# Labelme标注语义分割、实例分割注意事项

同济子豪兄 2023-6-8 7-26

## 下载安装Labelme

Labelme主页：https://github.com/wkentaro/labelme

## 标注前

1. 标注前，需左上角`File`开启`Save Automatically`自动保存

2. 标注前，需左上角`File`关闭`Save With Image Data`，不把图像本身保存至标签文件中

3. 应提前把所有图像放到同一个文件夹中，再用labelme打开这个文件夹标注

## 标注中

4. 应使标注文件保存至图像相同目录下，标注过程中，不要切换图像和标注文件的目录

5. 多段线（polygon）应尽可能精细，紧密贴合物体的真实边缘轮廓。

6. 如果使用AI-Polygon辅助标注，每张图片需先等待SAM分割一切大模型处理几秒钟，才能开始标注。

7. 如果是实例分割标注：标目标检测框时，画物体的外接矩形框。框的两个点，必须分别是左上角和右下角，顺序不能错。

8. 如果是目标检测+关键点检测标注：多段线（polygon）的第一个点`必须且只能落入一个框中`。见视频教程：https://www.bilibili.com/video/BV19g4y1777q

## 标注后确认

9. Labelme标注的json文件最后`imagePath`图像路径，**只能**是图像名字本身，**不能**有其它的路径和符号（例如`../`、`\\`之类的）

## 扩展阅读

Label Studio + Segment Anything Model 半自动化标注：https://space.bilibili.com/1293512903/channel/collectiondetail?sid=1389681
