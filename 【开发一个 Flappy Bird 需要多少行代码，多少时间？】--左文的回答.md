## 开发一个 Flappy Bird 需要多少行代码，多少时间？

作者: [左文](http://www.zhihu.com/people/zuo-wen)&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 赞同: 2288


<p><b>网上找到一篇文章，主场景300左右行代码，一天时间做出来，你信么？</b></p><p><b>原文链接： <a href="http://blog.csdn.net/touchsnow/article/details/19071961" class=" wrap external" target="_blank" rel="nofollow noreferrer">flappy bird游戏源代码揭秘和下载<i class="icon-external"></i></a></b></p><br><p><b>————————————————————————————————————</b></p><p><b>背景：</b></p><p>最近火爆全球的游戏flappy bird让笔者叹为观止，于是花了一天的时间山寨了一个一模一样的游戏，现在把游戏的思路和源码分享出来，代码是基于javascript语言，cocos2d-x游戏引擎，cocos2d-x editor手游开发工具完成的，请读者轻砸；</p><p>ps：运行demo必须配置好cocos2d-x editor，暂不支持其他工具；<u>还有demo是跨平台的，可移植运行android，ios，html5移动系统等，csdn博客里会介绍代码如何移植，请持续关注；</u><br></p><br><p><b>Android Apk下载演示：</b></p><p>暂时先移植到android平台</p><p>下载地址： <a href="http://share.weiyun.com/cac18d8c58d40bf2401b3fdeeb6bcb2f" class=" external" target="_blank" rel="nofollow noreferrer"><span class="invisible">http://</span><span class="visible">share.weiyun.com/cac18d</span><span class="invisible">8c58d40bf2401b3fdeeb6bcb2f</span><span class="ellipsis"></span><i class="icon-external"></i></a></p><br><p><b>代码下载：</b></p><p>  csdn下载：<a href="http://download.csdn.net/detail/touchsnow/6912707" class=" external" target="_blank" rel="nofollow noreferrer"><span class="invisible">http://</span><span class="visible">download.csdn.net/detai</span><span class="invisible">l/touchsnow/6912707</span><span class="ellipsis"></span><i class="icon-external"></i></a></p><p>  百度云盘：<a href="http://pan.baidu.com/s/1pJnWDb9" class=" external" target="_blank" rel="nofollow noreferrer"><span class="invisible">http://</span><span class="visible">pan.baidu.com/s/1pJnWDb</span><span class="invisible">9</span><span class="ellipsis"></span><i class="icon-external"></i></a></p><p>  金山快盘 ：<a href="http://www.kuaipan.cn/file/id_25348935635745384.htm?source=1" class=" external" target="_blank" rel="nofollow noreferrer"><span class="invisible">http://www.</span><span class="visible">kuaipan.cn/file/id_2534</span><span class="invisible">8935635745384.htm?source=1</span><span class="ellipsis"></span><i class="icon-external"></i></a></p><br><br><p><b>代码如何移植到各平台：</b></p><p>Android：<a href="http://blog.csdn.net/touchsnow/article/details/19176091" class=" external" target="_blank" rel="nofollow noreferrer"><span class="invisible">http://</span><span class="visible">blog.csdn.net/touchsnow</span><span class="invisible">/article/details/19176091</span><span class="ellipsis"></span><i class="icon-external"></i></a></p><p>html5:       <a href="http://blog.makeapp.co/?p=245" class=" external" target="_blank" rel="nofollow noreferrer"><span class="invisible">http://</span><span class="visible">blog.makeapp.co/?</span><span class="invisible">p=245</span><span class="ellipsis"></span><i class="icon-external"></i></a></p><br><p><b>效果图：</b></p><br><img src="http://pic3.zhimg.com/765282dd955615781212934f058aba5a_b.jpg" data-rawwidth="1355" data-rawheight="706" class="origin_image zh-lightbox-thumb" width="1355" data-original="http://pic3.zhimg.com/765282dd955615781212934f058aba5a_r.jpg"><img src="http://pic1.zhimg.com/2684b9be0357c9fec79833c280c72294_b.jpg" data-rawwidth="1352" data-rawheight="712" class="origin_image zh-lightbox-thumb" width="1352" data-original="http://pic1.zhimg.com/2684b9be0357c9fec79833c280c72294_r.jpg"><br><p><b>开发工具：</b></p><p>   cocos2dx editor，它是开发跨平台的手机游戏工具，运行window/mac系统上，javascript脚本语言，基于cocos2d-x跨平台游戏引擎, 集合代码编辑，场景设计，动画制作，字体设计，还有粒子，物理系统，地图等等的，而且调试方便，和实时模拟；</p><p>cocos2dx editor下载，介绍和教程：<a href="http://blog.csdn.net/touchsnow/article/details/19070665" class=" external" target="_blank" rel="nofollow noreferrer"><span class="invisible">http://</span><span class="visible">blog.csdn.net/touchsnow</span><span class="invisible">/article/details/19070665</span><span class="ellipsis"></span><i class="icon-external"></i></a>；</p><p>cocos2dx editor官方博客：<a href="http://blog.makeapp.co/?cat=8" class=" external" target="_blank" rel="nofollow noreferrer"><span class="invisible">http://</span><span class="visible">blog.makeapp.co/?</span><span class="invisible">cat=8</span><span class="ellipsis"></span><i class="icon-external"></i></a>；</p><br><p><b>思路和源码：</b></p><br><p>  1 场景设计MainLayer.ccbx，如下图；主要分三层，开始场景、主场景、游戏结束场景，通过显示隐藏控制三个场景的切换。</p><p>   MainLayer.ccbx代码</p><div class="highlight"><pre><code class="language-text">&lt;?xml version="1.0" encoding="UTF-8"?&gt;

&lt;Document
        jsControlled="true"
        jsController="MainLayer"
        resolution="default"
        &gt;

    &lt;Resolutions&gt;
        &lt;Resolution centeredOrigin="false" ext="iphone" height="1280" width="720" name="default" scale="1"/&gt;
        &lt;Resolution centeredOrigin="false" ext="iphone" height="720" width="1280" name="default1" scale="1"/&gt;
    &lt;/Resolutions&gt;

    &lt;Animations&gt;
        &lt;Animation autoPlay="true"
                   id="0"
                   name="Default Timeline"
                   length="10"
                   chainedId="0"
                   offset="0.0"
                   position="0.0"
                   resolution="30"
                   scale="128"&gt;
            &lt;CallbackChannel&gt;
            &lt;/CallbackChannel&gt;
            &lt;SoundChannel&gt;
            &lt;/SoundChannel&gt;
        &lt;/Animation&gt;

    &lt;/Animations&gt;
    &lt;Layer
            positionX="0" positionY="0.0"
            sizeType="Percent"
            width="100" height="100"
            anchorPointX="0.5" anchorPointY="0.5" ignoreAnchorPoint="true"
            scaleX="1" scaleY="1"
            &gt;

      &lt;Sprite positionType="LeftBottom" width="720.0" height="1280.0" positionX="0" positionY="0" anchorPointX="0"
                                         anchorPointY="0" src="Resources/bg.png" name="" var="" target="None" scaleX="1" scaleY="1" visible="true"/&gt;
      &lt;LayerColor positionType="LeftBottom" width="720" height="1280" positionX="0" positionY="0" anchorPointX="0"
                  anchorPointY="0" color="#fff2e8ff" visible="false"/&gt;
      &lt;Menu positionType="LeftBottom" width="40" height="40" positionX="356.0" positionY="237.0" anchorPointX="0.5"
              anchorPointY="0.5" scaleX="2.4" scaleY="1.725"&gt;
      &lt;/Menu&gt;
      &lt;Sprite positionType="LeftBottom" width="840.0" height="281.0" positionX="0" positionY="0" anchorPointX="0"
                                         anchorPointY="0" src="Resources/ground.png" var="ground" target="Doc"/&gt;
      &lt;Node positionType="LeftBottom" width="40" height="40" positionX="800" positionY="250" anchorPointX="0"
            anchorPointY="0" var="hoseNode" target="Doc"&gt;
        &lt;Sprite positionType="LeftBottom" width="86.0" height="60.0" positionX="-500" positionY="400" anchorPointX="0.5"
                                         anchorPointY="0.5" src="Resources/flappy_packer.plist/bird3.png" var="test" target="Doc" visible="false"/&gt;
        &lt;Sprite positionType="LeftBottom" width="86.0" height="60.0" positionX="-550" positionY="500" anchorPointX="0.5"
                anchorPointY="0.5" src="Resources/flappy_packer.plist/bird1.png" var="bird" target="Doc" scaleX="1" scaleY="1" rotation="0" visible="true"/&gt;
      &lt;/Node&gt;
      &lt;Node positionType="LeftBottom" width="40" height="40" positionX="303.0" positionY="500" anchorPointX="0.5"
            anchorPointY="0.5" var="readyNode" target="Doc" visible="true"&gt;
        &lt;Sprite positionType="LeftBottom" width="508.0" height="158.0" positionX="95.0" positionY="584.0" anchorPointX="0.5"
                                         anchorPointY="0.5" src="Resources/flappy_packer.plist/getready.png"/&gt;
        &lt;Sprite positionType="LeftBottom" width="286.0" height="246.0" positionX="73.0" positionY="236.0" anchorPointX="0.5"
                                         anchorPointY="0.5" src="Resources/flappy_packer.plist/click.png"/&gt;
      &lt;/Node&gt;
      &lt;Node positionType="LeftBottom" width="40" height="40" positionX="300" positionY="500" anchorPointX="0.5"
            anchorPointY="0.5" var="overNode" target="Doc" visible="true"&gt;
        &lt;Sprite positionType="LeftBottom" width="590.0" height="298.0" positionX="72.0" positionY="219.0" anchorPointX="0.5"
                                         anchorPointY="0.5" src="Resources/flappy_packer.plist/base.png"&gt;
          &lt;Sprite positionType="LeftBottom" width="508.0" height="158.0" positionX="286.0" positionY="458.0" anchorPointX="0.5"
                                         anchorPointY="0.5" src="Resources/flappy_packer.plist/gameover.png"/&gt;
        &lt;/Sprite&gt;
        &lt;Menu positionType="LeftBottom" width="40" height="40" positionX="0" positionY="0" anchorPointX="0.5"
              anchorPointY="0.5"&gt;
          &lt;MenuItem positionType="LeftBottom" width="290" height="176" positionX="-65.0" positionY="-92.0" anchorPointX="0.5"
                    anchorPointY="0.5" normalImage="Resources/flappy_packer.plist/start.png" target="Doc" onClick="onStartClicked"/&gt;
          &lt;MenuItem positionType="LeftBottom" width="290" height="176" positionX="230.0" positionY="-92.0" anchorPointX="0.5"
                    anchorPointY="0.5" target="Doc" normalImage="Resources/flappy_packer.plist/grade.png" onClick="onGradeClicked"/&gt;
        &lt;/Menu&gt;
      &lt;/Node&gt;
    &lt;/Layer&gt;


&lt;/Document&gt;
</code></pre></div><br><p>2 代码编写MainLayer.js</p><p>   首先，小鸟在向前飞，其实是底部的路和水管在向左移动，相对的你就感觉小鸟在向右飞了；路循环移动代码：</p><div class="highlight"><pre><code class="language-text">MainLayer.prototype.groundRun = function ()
{
    var action1 = cc.MoveTo.create(0.5, cc.p(-120, 0));
    var action2 = cc.MoveTo.create(0, cc.p(0, 0));
    var action = cc.Sequence.create(action1, action2);
    this.ground.runAction(cc.RepeatForever.create(action));
}
</code></pre></div><br>   初始化高低不同的水管，每一关卡都由上下两水管和空隙组成。总长度相同，空隙也一定，随机取下面水管的长度，就形成错落有致的水管关卡；<div class="highlight"><pre><code class="language-text">MainLayer.prototype.newHose = function (num)
{
    var hoseHeight = 830;
    var acrossHeight = 300;
    var downHeight = 100 + getRandom(400);
    var upHeight = 1100 - downHeight - acrossHeight;

    var hoseX = 400 * num;

    var HoseName = FP_MAIN_TEXTURE.HOSE;
    var ccSpriteDown = cc.Sprite.createWithSpriteFrameName(HoseName[0]);
    ccSpriteDown.setZOrder(1);
    ccSpriteDown.setAnchorPoint(cc.p(0, 0));
    ccSpriteDown.setPosition(cc.p(hoseX, 0));
    ccSpriteDown.setScaleY(downHeight / hoseHeight);

    var ccSpriteUp = cc.Sprite.createWithSpriteFrameName(HoseName[1]);
    ccSpriteUp.setZOrder(1);
    ccSpriteUp.setAnchorPoint(cc.p(0, 0));
    ccSpriteUp.setPosition(cc.p(hoseX, downHeight + acrossHeight));
    ccSpriteUp.setScaleY(upHeight / hoseHeight);

    this.hoseNode.addChild(ccSpriteDown);
    this.hoseNode.addChild(ccSpriteUp);
    this.hoseSpriteList.push(ccSpriteDown);
    this.hoseSpriteList.push(ccSpriteUp);
    return null;
}
</code></pre></div><br>  一开始进入游戏让底部路不断移动，初始化水管，显示准备游戏场景；<div class="highlight"><pre><code class="language-text">MainLayer.prototype.onEnter = function ()
{
    cc.AnimationCache.getInstance().addAnimations("Resources/flappy_frame.plist");
    this.groundRun();
    this.ground.setZOrder(10);
    this.birdReadyAction();
    this.bird.setZOrder(20);
    this.readyNode.setVisible(true);
    this.overNode.setVisible(false);

    for (var i = 0; i &lt; 30; i++) {
        this.newHose(i);
    }
}
</code></pre></div><br> 点击屏幕，小鸟向上飞60dp,然后更快的速度下落（移动动画），同时闪动翅膀（帧动画）；<div class="highlight"><pre><code class="language-text">MainLayer.prototype.birdRiseAction = function ()
{
    var riseHeight = 60;
    var birdX = this.bird.getPositionX();
    var birdY = this.bird.getPositionY();
    var time = birdY / 600;

    var actionFrame = cc.Animate.create(cc.AnimationCache.getInstance().getAnimation("fly"));
    var flyAction = cc.Repeat.create(actionFrame, 90000);
    var riseAction1 = cc.MoveTo.create(0.2, cc.p(birdX, birdY + riseHeight));
    var riseAction2 = cc.RotateTo.create(0, -30);
    var riseAction = cc.Spawn.create(riseAction1, riseAction2);
    var fallAction1 = cc.MoveTo.create(time, cc.p(birdX, 50));
    var fallAction2 = cc.Sequence.create(cc.DelayTime.create(time / 6), cc.RotateTo.create(0, 30));
    var fallAction = cc.Spawn.create(fallAction1, fallAction2);

    this.bird.stopAllActions();
    this.bird.runAction(cc.Spawn.create(
            cc.Sequence.create(riseAction, cc.DelayTime.create(0.1), fallAction),
            flyAction)
    );
}
</code></pre></div><br> 检测碰撞，如果小鸟碰到地面和水管，发生碰撞，这里碰撞直接用cocos2d-x 里面的图片和图片交叉函数 cc.rectIntersectsRect；<div class="highlight"><pre><code class="language-text">MainLayer.prototype.checkCollision = function ()
{
    if (this.bird.getPositionY() &lt; 60) {
        cc.log("floor");
        this.birdFallAction();
        return;
    }
    for (var i = 0; i &lt; this.hoseSpriteList.length; i++) {
        var hose = this.hoseSpriteList[i];
        if (!this.isInScreen(hose)) {
            // continue;
        }

        if (cc.rectIntersectsRect(hose.getBoundingBox(), this.bird.getBoundingBox())) {
            cc.log("hose positionX==" + hose.getBoundingBox().x);
            cc.log("this.bird positionX==" + this.bird.getBoundingBox().x);
            cc.log("i==" + i);
            cc.log("birdFallAction");
            this.birdFallAction();
            return;
        }
    }
}
</code></pre></div><br>碰撞后，小鸟先下落，游戏结束场景显示；<div class="highlight"><pre><code class="language-text">MainLayer.prototype.birdFallAction = function ()
{
    this.gameMode = OVER;
    this.bird.stopAllActions();
    this.ground.stopAllActions();
    var birdX = this.bird.getPositionX();
    var birdY = this.bird.getPositionY();
    var time = birdY / 2000;
    this.bird.runAction(cc.Sequence.create(
            cc.DelayTime.create(0.1),
            cc.Spawn.create(cc.RotateTo.create(time, 90), cc.MoveTo.create(time, cc.p(birdX, 50))))
    );
    this.overNode.setVisible(true);
}
</code></pre></div><br>游戏的难度主要在于多个水管的移动，小鸟触摸动画，检测碰撞;<br><br><p>再次提示代码下载地址：</p><p>  csdn下载：<a href="http://download.csdn.net/detail/touchsnow/6912707" class=" external" target="_blank" rel="nofollow noreferrer"><span class="invisible">http://</span><span class="visible">download.csdn.net/detai</span><span class="invisible">l/touchsnow/6912707</span><span class="ellipsis"></span><i class="icon-external"></i></a></p><p>  百度云盘：<a href="http://pan.baidu.com/s/1pJnWDb9" class=" external" target="_blank" rel="nofollow noreferrer"><span class="invisible">http://</span><span class="visible">pan.baidu.com/s/1pJnWDb</span><span class="invisible">9</span><span class="ellipsis"></span><i class="icon-external"></i></a></p><p>  金山快盘 ：<a href="http://www.kuaipan.cn/file/id_25348935635745384.htm?source=1" class=" external" target="_blank" rel="nofollow noreferrer"><span class="invisible">http://www.</span><span class="visible">kuaipan.cn/file/id_2534</span><span class="invisible">8935635745384.htm?source=1</span><span class="ellipsis"></span><i class="icon-external"></i></a></p><br><p>楼下有求图片的，地址：<a href="http://share.weiyun.com/d73228232bc0b1ff99f553afff58b7a2" class=" external" target="_blank" rel="nofollow noreferrer"><span class="invisible">http://</span><span class="visible">share.weiyun.com/d73228</span><span class="invisible">232bc0b1ff99f553afff58b7a2</span><span class="ellipsis"></span><i class="icon-external"></i></a></p><br><p><b>更多内容：</b><a href="http://blog.csdn.net/touchsnow/article/details/19071961" class=" external" target="_blank" rel="nofollow noreferrer"><span class="invisible">http://</span><span class="visible">blog.csdn.net/touchsnow</span><span class="invisible">/article/details/19071961</span><span class="ellipsis"></span><i class="icon-external"></i></a></p><p><b>官方博客：</b><a href="http://blog.makeapp.co/" class=" external" target="_blank" rel="nofollow noreferrer"><span class="invisible">http://</span><span class="visible">blog.makeapp.co/</span><span class="invisible"></span><i class="icon-external"></i></a></p><p><b>联系笔者：</b>zuowen@makeapp.co （邮箱）</p><br><p><b>想了解其他游戏开发可关注：</b><a href="http://www.zhihu.com/question/23038067" class="internal">消灭星星（Popstar）游戏是怎么开发实现的？难不难？经常看到有人玩这个，很好奇里面的逻辑，拜求高手解答！</a></p><br><br><p>附录：其他游戏例子学习 <a href="http://blog.csdn.net/touchsnow/article/details/19070665" class=" external" target="_blank" rel="nofollow noreferrer"><span class="invisible">http://</span><span class="visible">blog.csdn.net/touchsnow</span><span class="invisible">/article/details/19070665</span><span class="ellipsis"></span><i class="icon-external"></i></a>；</p><br><img src="http://pic3.zhimg.com/baf8423a2d074f5475639ad92b4b4ee6_b.jpg" data-rawwidth="1364" data-rawheight="738" class="origin_image zh-lightbox-thumb" width="1364" data-original="http://pic3.zhimg.com/baf8423a2d074f5475639ad92b4b4ee6_r.jpg"><br><br><img src="http://pic3.zhimg.com/0ab40199df16155dee739e43d9b366f2_b.jpg" data-rawwidth="1360" data-rawheight="726" class="origin_image zh-lightbox-thumb" width="1360" data-original="http://pic3.zhimg.com/0ab40199df16155dee739e43d9b366f2_r.jpg"><br><img src="http://pic4.zhimg.com/5994e6b7a39277102b4afb9304252733_b.jpg" data-rawwidth="1358" data-rawheight="728" class="origin_image zh-lightbox-thumb" width="1358" data-original="http://pic4.zhimg.com/5994e6b7a39277102b4afb9304252733_r.jpg"><br><img src="http://pic1.zhimg.com/abdee6f10d30cda1edb6aff4c8d07b10_b.jpg" data-rawwidth="1361" data-rawheight="727" class="origin_image zh-lightbox-thumb" width="1361" data-original="http://pic1.zhimg.com/abdee6f10d30cda1edb6aff4c8d07b10_r.jpg"><br><img src="http://pic2.zhimg.com/6fd502bb7517157be3293f9417c10785_b.jpg" data-rawwidth="1358" data-rawheight="728" class="origin_image zh-lightbox-thumb" width="1358" data-original="http://pic2.zhimg.com/6fd502bb7517157be3293f9417c10785_r.jpg">



编辑于 2014-04-01



---
原问链接: [http://www.zhihu.com/question/22715390](http://www.zhihu.com/question/22715390)