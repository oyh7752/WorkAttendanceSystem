# WorkAttendanceSystem    
一个基于opencv人脸识别的员工考勤系统，作者某双一流A类大学里的~~一流~~学生，写于2018/09/，python课设期间。  

 ![](https://img.shields.io/badge/opencv-cv2-green.svg)
 ![](https://img.shields.io/badge/dlib-19.4.0-red.svg)
 
|作者|[inspurer](https://inspurer.github.io/2018/06/07/%E6%9C%88%E5%B0%8F%E6%B0%B4%E9%95%BF%E7%9A%84%E7%94%B1%E6%9D%A5/#more)|
|:---:|:---:|
|QQ|2391527690|
|个人博客|[https://inspurer.github.io/](https://inspurer.github.io/)|



-----------------------------------------------------------------------------------  

# :dolphin:V2.0版本已打包,可直接下载运行,文件过大，只上传百度云  

[链接：https://pan.baidu.com/s/1aIA6AhTB8LVESSAN5jgDjQ 提取码：l7or](https://pan.baidu.com/s/1aIA6AhTB8LVESSAN5jgDjQ) 


------------------------------------------------------------------------------------

# :dolphin:V1.0    
## 项目结构    
mainui.py是主界面，调用face_img_register.py和face_recognize_punchcard.py，其中face_img_register.py主要实现录入人脸信息功能，face_recognize_punchcard.py实现刷脸考勤，face_feature_storage.py是在调试过程中产生的文件，没什么用，可无视。  
face_recognize_punchcard_lib.py和face_recognize_punchcard.py本质上差不多，但是前者是给face_img_register.py专有的依赖。    
防止录入两个同样的人脸建不同数据库的风险。   

## 运行效果   
### 1. 主界面   
![](pictures/1.png)   
### 2. 人脸录入   
![](pictures/2.png)    
### 3. 刷脸考勤    
这是通宵后的我
![](pictures/3.png)

## 更新     
### 2018/9/23更新
mainui.py-->myapp.py   
face_recognize_punchcard_lib.py等鸡肋文件放到useless文件夹里    
运行效率显著提高   

### 2018/9/25更新    
解决同步性问题，新录入的人脸能立即被识别    
代码的运行速度少许下降    

----------------------------------------------------------------------------------------------

# :dolphin:V2.0   
## 重构代码   

老师看了我的V1.0版本后给的建议，第一，不能有太多弹窗界面，一些操作应该放到工具栏中，而不是弹窗实现；第二，数据保存在csv文件容易被窃读，应该保存到数据库熊；第三，显示考勤日志时应该由自己的电子表格实现而不是直接调用excel。基于以上的问题和算法优化的需要，我把代码优化成了V2.0，同时所以的代码合在一个WorkAttwndanceSystem.py文件里，就人脸识别这部分代码而言，提高了代码复用度

## 1. 全新设计的UI,更人性化的操作    
![](pictures/4.png)![](pictures/5.png)
这也是通宵后的我![](pictures/6.png)     
## 2. 数据更加安全，用户不可见
人脸数据和签到日志全部保存在inspurer.db数据库文件里，更加安全；而且对人脸数据进行了压缩，更加小巧。   
## 3. 注意事项   
<ol>
<li>打开摄像头时请左右晃动一下人脸，确保人脸识别开始.</li>
<li>人脸识别时做了拒绝处理，多张人脸时，只取距离屏幕最近的人脸.</li>
<li>`新建录入`时会自动录入十张人脸照片，也可手动点击`完成录入`立即完成，之后就会计算人脸数据并存储到数据库中,左边的信息栏会有相应的信息打印.</li?
<li>`开始签到`后，如不点击`结束签到`,就会一直对屏幕前的人脸进行签到，签到状态分三种,未识别的人脸,签到成功,签到成功但是迟到了(9.00后签到),重复签到(此时签到日志不会写入到数据库.</li>         
<li>为确保程序稳定性，每一个菜单里的按钮尽量成对操作.</li>  
</ol>
-----------------------------------------------------------------------------------

# 后话
## git clone下载仓库速度过慢的问题请参考:[CSDN博客](https://blog.csdn.net/ygdxt/article/details/82825013)

## 有关代码的详细解释和设计实现过程请参考:[微信公众号](https://mp.weixin.qq.com/s?src=11&timestamp=1544280051&ver=1283&signature=WpptKZypviF-i3dIwyhl9MzJeaXDDnmT-uK8R2oo3S-*R0EhjCPa2gKrc*JQYiGwkTh78kWRgwuj-3HLnka6-c07cgdWPVokZZXwnX2pc5nvnsUo9B9Nw7agLQhu-vSB&new=1)  

## 赞善  
![](https://github.com/inspurer/WorkAttendanceSystem/blob/master/pictures/TIM%E5%9B%BE%E7%89%8720181208222337.png)

