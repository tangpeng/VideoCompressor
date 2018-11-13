# 如果您觉得本项目对你有用，请随手star，谢谢
个人主页：https://www.jianshu.com/u/521b2b15caba

Android 视频压缩常见3种方案：(1)FFmpeg,(2)mp4praser,(3)MediaCodec.
本demo是用android 自带的MediaCodec 框架

本人试了一下，一个大小为656M的视频，压缩只要3分钟，可以通过改变分辨率和码率来进行压缩，有进度条提示。如果使用ffmpeg需要大概10分钟左右，而且因为包会比较大。

如果说只要使用视频压缩的功能的话，使用本项目是最适合不过了，如果还需要裁切，拼接，音频相关的处理还会建议使用ffmpeg，它的功能才叫做强大，而且网上有很多教程和开源的代码

如果压缩后觉得视频不够清楚，可以参考本人的另一个demo使用ffmpeg做的视频压缩demo，效果会好很多，demo地址：https://github.com/tangpeng/FFmpegDemo

##如果您觉得本项目对你有用，请随手star，谢谢

## Demo
![Demo](/pic/Demo.gif)

###一句代码搞定 可以修改分辨率或者码率
```
VideoCompressTask task = VideoCompress.compressVideoLow(tv_input.getText().toString(), destPath, new VideoCompress.CompressListener() {
                    @Override
                    public void onStart() {
                        //Start Compress
                    }

                    @Override
                    public void onSuccess() {
                        //Finish successfully
                    }

                    @Override
                    public void onFail() {
                        //Failed
                    }

                    @Override
                    public void onProgress(float percent) {
                        //Progress
                    }
                });
```

硬件解码跟软件解码我们通常称为硬解跟软解，是通过移动设备观看视频时会碰到的一个概念。
首先来说下两者的区别：
硬件解码：硬件解码从字面意思很容易理解，就是通过硬件进行视频的解码工作，其中硬件解码是由GPU来进行的，使用GPU解码能够降低CPU的工作负荷，降低功耗。
软件解码：软件解码则是通过软件本身占用的CPU进行解码，所以会增加CPU工作负荷，提升功耗，
硬解及软解的优点跟缺点：
硬解优点：播放出来的视频较为流畅，并且能够延长移动设备播放视频的时间；
硬解缺点：所解码视频格式收到GPU影响，无法部分全部视频，画质也不够清晰。
软解优点：软解能够解码所有视频格式文件，且画质更加清晰；
软解缺点：由于软解加大CPU工作负荷，会占用过多的移动CPU资源，如果CPU能力不足，则软件也将受到影响。
