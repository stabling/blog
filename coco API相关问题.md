COCO API 的使用：  

Windows 版本：  

cmd 指令：git clone https://github.com/cocodataset/cocoapi.git  

cd D:\API\cocoapi\PythonAPI  

直接运行 python setup.py build_ext --inplace  

如果报错，则修改setup.py文件中的  

extra_compile_args = ['Wno-cpp', 'Wno-unused-function', '-std=c99']  

改为：  

extra_compile_args = ['-std=c99']  

如果要调用pycocotools 需要先载入局部环境：  

import sys  
sys.path.append('D:\API\cocoapi\PythonAPI')   # 将你的 `pycocotools` 所在路径添加到系统环境  


如果不想这么麻烦，可以直接将 pycocotools 安装在主环境下：  

python setup.py build_ext install  
rd build   # 删除  



