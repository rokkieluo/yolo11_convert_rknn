# yolo11模型转换工具使用说明(onnx->rknn)

**注：此转换工具需配合仓库中的rk-yolo11([rokkieluo/rk-yolo11](https://github.com/rokkieluo/rk-yolo11))使用，操作系统为ubuntu**

## 一、环境依赖搭建：

进入rk官方github([rknn-toolkit2/rknn-toolkit2/packages/x86_64 at master · airockchip/rknn-toolkit2](https://github.com/airockchip/rknn-toolkit2/tree/master/rknn-toolkit2/packages/x86_64))，下载rknntoolkit2的python包，选择符合自己Python版本的即可，创建虚拟环境也可以

![rknntoolkit2-whl](C:\Users\15346\Desktop\convert_tool\yolo11_convert_rknn\images\rknntoolkit2-whl.png)

**注：此处需先安装requirements.txt的依赖环境后才可安装rknntoolkit2-whl**

搭建好依赖后后续操作才能正常实现

## 二、拉取本工具到本地

创建一个文件夹，进行拉取

```bash
git clone https://github.com/rokkieluo/yolo11_convert_rknn.git
```

## 三、更换自己的测试图片和onnx模型

1.将自己的测试图片放入yolo11_convert_rknn目录和data目录下，并更改dataset.txt的内容

![image1](C:\Users\15346\Desktop\convert_tool\yolo11_convert_rknn\images\image1.png)

2.将经过rk-yolo11转换后的onnx模型放入yolo11_convert_rknn目录下

## 四、更改onnx2rknn.py

1.在onnx2rknn.py做如下修改

![image2](C:\Users\15346\Desktop\convert_tool\yolo11_convert_rknn\images\image2.png)

QUANTIZE_ON为量化选项，根据自己的情况来决定是否量化，一般建议量化提升速度

2.更改测试图片路径

![image3](C:\Users\15346\Desktop\convert_tool\yolo11_convert_rknn\images\image3.png)

## 五、终端运行onnx2rknn.py

```python
python onnx2rknn.py
```

运行后即可得到rknn模型，还会生成一个仿真检测图(test_rknn_result.jpg)，用于判断转换的模型有无问题，无问题则如图，至此转换rknn模型成功

![image4](C:\Users\15346\Desktop\convert_tool\yolo11_convert_rknn\images\image4.png)

