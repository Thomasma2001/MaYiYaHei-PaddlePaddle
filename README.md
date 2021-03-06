本地安装个人版蚂蚁呀嘿步骤：

1.从github上克隆PaddleGAN代码

$ git clone https://gitee.com/paddlepaddle/PaddleGAN

2.安装所需安装包

$ cd PaddleGAN

$ pip install -r requirements.txt

3.创建一个输出文件的存放目录

$ cd applications

$ mkdir output

4.安装cmake程序包

$ pip install cmake

5.安装ppgan程序包（注意版本号）

$ pip install ppgan==0.1.2

6.大家可以上传自己准备的视频和图片，并在如下命令中的source_image参数和driving_video参数分别换成自己的图片和视频路径，
然后运行如下命令，就可以完成动作表情迁移，程序运行成功后，会在ouput文件夹生成名为result.mp4的视频文件，该文件即为动作迁移后的视频。

$ python -u /c/exercise/PaddleGAN/applications/tools/first-order-demo.py  --driving_video /c/exercise/work/fullbody.MP4  --source_image /c/exercise/work/MXC2.png --relative --adapt_scale

7.安装moviepy包

$ pip install moviepy

8.为生成的视频加上音乐

from moviepy.editor import *

videoclip_1 = VideoFileClip("./work/fullbody.MP4")
videoclip_2 = VideoFileClip("./output/result.mp4")

audio_1 = videoclip_1.audio

videoclip_3 = videoclip_2.set_audio(audio_1)
videoclip_3.write_videofile("./output/mxc.mp4", audio_codec="aac")


到这里，本地安装个人版蚂蚁呀嘿就完成啦

*** 安装环境：Windows 10, Python 3.7.5, Git Bash 2.23.0 ***

！！！飞桨环境需要预先安装： pip install paddlepaddle

---------------------------------------------------------------------
---------------------------------------------------------------------
本地安装多人版蚂蚁呀嘿步骤：

1.# 从github上克隆PaddleGAN代码

$ git clone https://gitee.com/paddlepaddle/PaddleGAN.git

2. 切换到分支'develop'

$ cd PaddleGAN

$ /c/exercise/PaddleGAN (master)

$ git checkout develop

Switched to a new branch 'develop'
Branch 'develop' set up to track remote branch 'develop' from 'origin'.

$ /c/exercise/PaddleGAN (develop)

3. 安装所需安装包

$ cd PaddleGAN/

$ pip install -r requirements.txt

$ pip install imageio-ffmpeg

4.安装ppgan程序包（注意版本号）

$ pip install ppgan

用pip list 查看 确认ppgan==0.1.3

5.上传自己准备的视频和多人图片，并在如下命令中的source_image参数和driving_video参数分别换成自己的图片和视频路径，然后运行如下命令，就可以完成动作表情迁移，程序运行成功后，会在ouput文件夹生成名为result.mp4的视频文件，该文件即为动作迁移后的视频。

具体的各参数使用说明如下：

driving_video: 驱动视频，视频中人物的表情动作作为待迁移的对象

source_image: 原始图片，视频中人物的表情动作将迁移到该原始图片中的人物上

relative: 指示程序中使用视频和图片中人物关键点的相对坐标还是绝对坐标，建议使用相对坐标，若使用绝对坐标，会导致迁移后人物扭曲变形

adapt_scale: 根据关键点凸包自适应运动尺度

ratio：将框出来的人脸贴回原图时的区域占宽高的比例，默认为0.4，范围为【0.4，0.5】

$ python -u /c/exercise/PaddleGAN/applications/tools/first-order-demo.py  --driving_video /c/exercise/work/fullbody.MP4  --source_image /c/exercise/three.jpg --ratio 0.4 --relative --adapt_scale

6.安装moviepy包
$ pip install moviepy

7.为生成的视频加上音乐
from moviepy.editor import *

videoclip_1 = VideoFileClip("./work/fullbody.MP4")
videoclip_2 = VideoFileClip("./output/result.mp4")

audio_1 = videoclip_1.audio

videoclip_3 = videoclip_2.set_audio(audio_1)
videoclip_3.write_videofile("./output/mxc-m.mp4", audio_codec="aac")

到这里，本地安装多人版蚂蚁呀嘿就完成啦！
