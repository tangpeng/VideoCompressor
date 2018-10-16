本人试了一下，一个大小为656M的视频，压缩只要3分钟，可以通过改变分辨率和码率来进行压缩，有进度条提示。如果使用ffmpeg需要大概10分钟左右，而且因为包会比较大。

如果说只要使用视频压缩的功能的话，使用本项目是最适合不过了，如果还需要裁切，拼接，音频相关的处理还会建议使用ffmpeg，它的功能才叫做强大，而且网上有很多教程和开源的代码

##如果您觉得本项目对你有用，请随手star，谢谢

## Demo
![Demo](/pic/Demo.gif)

###一句代码搞定 可以修改分辨率或者码率
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


