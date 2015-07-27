## 游戏 2048 的基本游戏策略是什么？

作者: [chenqin](http://www.zhihu.com/people/chenqin)&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 赞同: 1329


基本的思想就是递归生成<img src="http://zhihu.com/equation?tex=2%5En" alt="2^n" eeimg="1">，要严格按照一定步骤，就像解九连环那样，决不能碰运气。<br><br>一开始的步骤是这样，如果左下角第一个数字是<img src="http://zhihu.com/equation?tex=2%5En" alt="2^n" eeimg="1">，那么就在他的右边放<img src="http://zhihu.com/equation?tex=2%5E%7Bn-1%7D" alt="2^{n-1}" eeimg="1">，依次类推，直到剩下4或者2，此时只要往末尾的数字填一个4或者2，顶端数字就会变成<img src="http://zhihu.com/equation?tex=2%5E%7Bn%2B1%7D" alt="2^{n+1}" eeimg="1">。然后在顶端数字旁边，再用同样的方法构造<img src="http://zhihu.com/equation?tex=2%5En" alt="2^n" eeimg="1">，<img src="http://zhihu.com/equation?tex=2%5E%7Bn-1%7D" alt="2^{n-1}" eeimg="1">……直到逐格降幂后出现4或者2。如果最后一行用完了，就转弯绕上来。<br>下图是一个游戏刚开始的例子，我只要在右下角合并一个2，顶端数字就可以变成32，然后我继续再顶端数字旁构造16、8……<br><img src="http://pic1.zhimg.com/fc740bc3630f46ecbca107495d966cbc_b.jpg" data-rawwidth="531" data-rawheight="527" class="origin_image zh-lightbox-thumb" width="531" data-original="http://pic1.zhimg.com/fc740bc3630f46ecbca107495d966cbc_r.jpg">.严格按照这种方法，最后胜利前的图是这样的：<br><img src="http://pic2.zhimg.com/7ff05230a1fa782255452b9957794b9d_b.jpg" data-rawwidth="380" data-rawheight="480" class="content_image" width="380">此时只要弄一个8出来和第三行第一列的数字合并即可达成2048。<br>这种方法要求你绝对慎用向上键。向右键也需要谨慎使用，只有在数列所在行满行的时候才能使用。否则在左下角可能会出现4或者2，这会将你的数列错行。<br><br>有一个问题是，这种方法做出来的2048，由于最后一个步骤是将等比数列求和，所以屏幕上几乎不剩任何数字，分数较低。但没关系，这个小游戏刚刚取消了只能玩到2048的限制，只要按照这种方法玩，不仅2048几乎可次次达成，然后再keep going，4096都不是梦（需要运气）。<br><img src="http://pic4.zhimg.com/cba155268b1b38100d30f1e97d0b820f_b.jpg" data-rawwidth="580" data-rawheight="803" class="origin_image zh-lightbox-thumb" width="580" data-original="http://pic4.zhimg.com/cba155268b1b38100d30f1e97d0b820f_r.jpg">（败在了追寻8192的路上，顶部空间不够了）



发布于 2014-03-16



---
原问链接: [http://www.zhihu.com/question/23029850](http://www.zhihu.com/question/23029850)