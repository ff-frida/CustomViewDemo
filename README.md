# CustomViewDemo
这是一个自定义 音频频谱控件、音视频播放进度条控件、伸缩开关控件的demo

年前的聊天室功能今天上线了，忙碌了好一阵子
期间自定义了一些控件，因为需求上要求的效果在网上没有找到，就自己画了，现在写个demo记录一下

老规矩，看看做出来的效果图：
</r/n>
 ![image](https://github.com/weioule/CustomViewDemo/blob/master/app/img/img01.jpg) 　
 
 
  ![image](https://github.com/weioule/CustomViewDemo/blob/master/app/img/img02.jpg) 　
  
  先来说说音频频谱控件，GitHub上是有很多项目，但UI要求不一样，所以得自己画，主要是画的垂直圆角矩形，左上右下的值计算好，还有圆角的半径，带着间隔 依次画上去就行了。
  然后你就还需要采集播放器的声音频率，稍作处理后，再将上面画的矩形的top值进行相应的修改，接着不停的调用绘制的方法绘制就好。还有就是在测量的时候，注意一下布局里设置的模式，根据测量模式去处理。
  
  然后就是进度条，许多进度条的头都是原生设置的点状或者一些图片，我的需求是要在一个横向的圆角矩形里显示总时长和当前所听时长，所以就需要继承SeekBar自定义，矩形背景比较好办，就是布局里设置thumb一张图片或者画的背景，但是中间的文字就的画了。
  思路是通过getThumb()获取到所设置的背景图，在用该背景图的中心点的左边作为文本绘制的中心点去绘制你所需要的文案。我在demo中使用的时候，是打开一个带
  
