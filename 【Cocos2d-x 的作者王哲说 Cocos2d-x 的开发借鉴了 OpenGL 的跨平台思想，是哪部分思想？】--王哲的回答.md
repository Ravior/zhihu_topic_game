## Cocos2d-x 的作者王哲说 Cocos2d-x 的开发借鉴了 OpenGL 的跨平台思想，是哪部分思想？

作者: [王哲](http://www.zhihu.com/people/walzer)&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 赞同: 2144


楼主，我没说过这句话。<br><br>——————<br>2015-03-25更新：<br>这个回答得到的赞数，居然远远超过我在技术问题下面花几个小时的回答。杯具啊。<br><br>有个晚上我做梦，梦到了这个问题的正确回答，然后第二天醒来只记得我梦到了这件事，却不记得正确答案是什么了。今天下午翻知乎，努力回忆了一下。我应该是讲过这样的话：<br><br><b>『Cocos2d-x的开发借力了OpenGL ES的跨平台性』</b>。<br><br>可能是采访录音或者速记的错误，导致以讹传讹，到楼主看到的时候就已经走样了。<br><br>也就是说，Cocos2d-x的跨平台层，很大程度得益于OpenGL ES标准在不同手机平台上都可以运行，即使在wp8上也有Angel Project把OpenGL ES调用转换到DirectX，所以我们一套OpenGL ES调用可以横跨iOS, Android, WP8三个主要平台。如果像以前主机平台那样，各平台有各平台自己的渲染API，相互不兼容、没有工业标准，那么Cocos2d-x跨平台做起来就相当苦逼了。<br><br>当然好日子也差不多到头了，苹果极力推他们的Metal，所以在Cocos2d-x v4.0里面我们开始做GPU抽象层，也就是无法再借力OpenGL ES的跨平台性了。现在感觉还好，但回过头去看，这样重的研发成本在早期我们还是小团队的时候是无法承受的。



编辑于 2015-03-25



---
原问链接: [http://www.zhihu.com/question/20892640](http://www.zhihu.com/question/20892640)