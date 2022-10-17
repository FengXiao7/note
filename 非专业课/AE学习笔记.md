(学习视频来自李兴兴老师3合1教程https://www.bilibili.com/cheese/play/ss821?bsource=link_copy)36集开始



# 教训和疑问

## 0.要经常保存

血的教训！

## 1.学AE，电脑空间必须足

我用的是笔记本，推荐买个移动固态硬盘。内存要够，

## 2.混音

老师自己合成音乐，有点好奇是怎么做的。

## 3.两种预合成的区别

37集还是有点小懵

## 4.AE中形状选择工具没有圆形工具

[我的ae中怎么没有圆形工具_百度知道 (baidu.com)](https://zhidao.baidu.com/question/98102735.html)

可以按Q切换，也可以长按

## 5.照片自动铺满屏幕

![image-20221016172401453](https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/image-20221016172401453.png)

![image-20221016172524431](https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/image-20221016172524431.png)

## 6.输出太慢请用Media Encoder

## 7.删除图层

选中图层，按delete键即可

## 8.时间轴标记快速定位

<span style="color: red">**37集第8点**</span>

可以按数字1-9快速切换时间轴上的标记

下图我打了个31号标记。有个小问题怎样通过数字键快速定位两位数的标记呢？

譬如我想去15号标记，先后按下数字1和5。这样的结果却是先到标记1再去标记5。

![](https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/226.gif)

## 9.复制图层

<span style="color: red">**37集第8点**</span>

这个很复杂，我想复制两个独立的图层。这就是一个深拷贝的问题

老师的方案就是先浅拷贝两个图层。详见37集第9点

# 艺术

## 1.油管博主

这是来真的，老师教我们来假的

![image-20221017145909784](C:\Users\FengXiao7\AppData\Roaming\Typora\typora-user-images\image-20221017145909784.png)

## 2.贝塞尔曲线

建议学透，计算机视觉有讲过。有余力可以玩玩

# 36.赛博朋克案例，快速上手AE特效

## 1.新建合成

类似PR的序列

<span style="color: red">竖版素材，把1920和1080调换就行</span>

![image-20221015132849053](https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/image-20221015132849053.png)

## 2.把素材拖入合成

![](https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/210.gif)

## 3.裁剪相关

前4秒是废片

### 法一：鼠标拖动

同样的道理，也可以用鼠标拖动裁剪后面的废片

![](https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/211.gif)

### 法二：快捷键

时间刻度放在4秒时，按下快捷键alt+[

这个快捷键挺奇葩的……

同样的道理，也可以用alt+]快捷键裁剪后面的废片

![image-20221015133830613](https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/image-20221015133830613.png)

### 吸附前方空格

直接鼠标拖动

![](https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/212.gif)

或者选中素材，按快捷键[

(我的不行，不知道为啥)

### 素材分段

![image-20221015135146086](https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/image-20221015135146086.png)

## 4.时间面板

### 眼睛

![image-20221015135455023](https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/image-20221015135455023.png)

### 喇叭，小圆圈，锁

![image-20221015140338162](https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/image-20221015140338162.png)

## 5.节目面板

### 缩放

alt+鼠标滚轮

![](https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/213.gif)

## 6.创建跟踪摄像机

![image-20221015141230126](https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/image-20221015141230126.png)

![image-20221015141340062](https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/image-20221015141340062.png)

### 出现问题：

暂时没有解决

![image-20221015141511493](https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/image-20221015141511493.png)

### 分析完毕有很多小点：

这些是AE智能分析的追踪点，我们可以根据这些点来制作追踪动画

![](https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE(47).png)

## 7.制作精灵球特效

- 找几个牢靠的追踪点。不断拖拽时间轴发现有几个点固定不动，就选那几个点。
- 点第二个点，第三个点时，按住shift键。
- 右击创建实地和摄像机，创建好了后适当缩放摄像机，不要太大了。

![](https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/214.gif)

- 替换素材

一定要按住alt键选中素材，然后拖到跟踪实底上就行~

![](https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/215.gif)

### 调整模式：

文字素材背景是黑的，把后面的精灵球遮住了……

选择模式-->屏幕即可。有点像PR和PS里的**混合模式**

<span style="color: red">找不到模式的，点左小角。多开几个面板信息</span>

![](https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/216.gif)

### 调整位置和方向：

直接在节目面板里拖动也行喔~

其实可以调整的，世界坐标系啥的，计算机视觉课老师有讲过

![image-20221015151604160](https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/image-20221015151604160.png)

### 旋转：

就是打关键帧~

和PR差不多啦~

往右一帧是按PgDn，往左一帧是PgUp。和PR有所不同

![image-20221015153117556](https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/image-20221015153117556.png)

![image-20221015153251005](https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/image-20221015153251005.png)

配合透明度和旋转做关键帧动画即可

![](https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/217.gif)

## 8.跟踪屏幕特效

### 选一片跟踪点

再次创造摄像机，不过这次选点的时候，大多数都挺牢固，直接按住左键画个圈就行

![](https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/218.gif)

### 细调参数

调整参数的时候，按住ctrl键再去调整，变化幅度会比较小

![](https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/219.gif)

### 复制粘贴关键帧

下图演示的是把文字特效的透明度关键帧，复制粘贴给粒子流特效。

就是把不透明度的4个点复制，然后选择粒子流粘贴即可

![](https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/220.gif)

## 9.科技界面特效

### 预合成

相当于新建一个合成，类似PR的嵌套序列

![image-20221015164345742](https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/image-20221015164345742.png)

[李兴兴：三合一剪辑训练营_哔哩哔哩_bilibili](https://www.bilibili.com/cheese/play/ep32592?csource=Hp_searchresult&spm_id_from=333.337.0.0)27:27

创建好以后，双击进入。开始填充科幻界面。

### 改模板

第一节课就不要这么拘谨啦，以后再仔细研究如何改模板，如何自己制作特效

主要流程就是把别人的模板拖进来，注意把跟踪实底关了

![image-20221015180542495](C:\Users\FengXiao7\AppData\Roaming\Typora\typora-user-images\image-20221015180542495.png)

其实就是不断改图层就行了，不难的

## 10.音乐

我们把老师做好的音乐拖过来就行啦~我想学这个

![image-20221015175943214](https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/image-20221015175943214.png)

## 11.导出视频

[李兴兴：三合一剪辑训练营_哔哩哔哩_bilibili](https://www.bilibili.com/cheese/play/ep32592?csource=Hp_searchresult&spm_id_from=333.337.0.0)36m

![image-20221015200312073](https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/image-20221015200312073.png)



![image-20221015200812886](https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/image-20221015200812886.png)

最后点击渲染即可。

但是AE自带的渲染器不是很好，推荐使用Media Encoder

![image-20221015201305234](https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/image-20221015201305234.png)

![image-20221015201843872](https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/image-20221015201843872.png)

# 37.动态电子相册

把原视频的照片替换为其他照片。

<span style="color: red">这个案例非常重要，理解合成之间的嵌套关系很有必要</span>

我的建议是多去点灭或点亮小眼睛，必须理清楚嵌套关系！！！

## 1.两种预合成的差别

### 预合成1：

![image-20221015210808633](https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/image-20221015210808633.png)

![image-20221015210925975](https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/image-20221015210925975.png)



![image-20221015211643825](https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/image-20221015211643825.png)



![image-20221015211319758](https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/image-20221015211319758.png)

### 预合成2：

![image-20221015212546722](https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/image-20221015212546722.png)

![image-20221015212146231](https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/image-20221015212146231.png)

## 2.跟踪运动

我们选择**第二种预设**

这里不能用跟踪摄像机，因为画面运动幅度太小，AE智能分析不出来……

<span style="color: red">记得先点进去预设，然后再选中素材。不然跟踪器面板不会亮的~</span>

![image-20221015214723667](https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/image-20221015214723667.png)

### 4点追踪

- 每一个跟踪点都是由两个框组成的。
- 里面的框是目标框，用来锁定目标。
- 外面的框就是一个判断范围，在接下来的每一帧，搜索框就会看目标在搜索框的哪个范围。

![image-20221015215824158](https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/image-20221015215824158.png)

目标选择

![image-20221015220056522](https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/image-20221015220056522.png)

搜索框也不要画的太大，运算量会增加很多的

![image-20221015220237689](https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/image-20221015220237689.png)

跟踪失败的情况[李兴兴：三合一剪辑训练营_哔哩哔哩_bilibili](https://www.bilibili.com/cheese/play/ep32593?csource=Hp_searchresult&spm_id_from=333.337.0.0)13:20左右，了解下解决方法即可

## 3.替换照片

[李兴兴：三合一剪辑训练营_哔哩哔哩_bilibili](https://www.bilibili.com/cheese/play/ep32593?csource=Hp_searchresult&spm_id_from=333.337.0.0)14:10处，讲的有点快

把照片拖过来

选中素材，然后选择运动源

![image-20221015222054932](https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/image-20221015222054932.png)

编辑目标应用即可

![](https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/221.gif)

## 4.照片尺寸不一样的情况

![image-20221016132413042](https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/image-20221016132413042.png)

老师讲了个把横版照片变竖版的方法，用AE做的，用其他工具也行，只要达到一样的效果就行。

记录下AE的做法

[李兴兴：三合一剪辑训练营_哔哩哔哩_bilibili](https://www.bilibili.com/cheese/play/ep32593?csource=Hp_searchresult&spm_id_from=333.337.0.0)15:30开始

![image-20221016133157910](https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/image-20221016133157910.png)

把宽图放过来，按住shift键等比例缩放即可

![](https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/222.gif)

## 5.小总结一下

![image-20221016134702961](https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/image-20221016134702961.png)

![image-20221016135607381](https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/image-20221016135607381.png)

动图展示：

![](https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/223.gif)

## 6.最简单的AE模板

我们实际上已经做了一个简易的AE模板了，用合成来代替素材位置。

这个模板就是照片替换01了……非常简单，只需要把照片替换上去就行了。

![image-20221016142147501](https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/image-20221016142147501.png)

## 7.单点跟踪

老师用了个案例，在画框上绑定一个我们自己画的小圆

[李兴兴：三合一剪辑训练营_哔哩哔哩_bilibili](https://www.bilibili.com/cheese/play/ep32593?csource=Hp_searchresult&spm_id_from=333.337.0.0)18分开始

![image-20221016151433175](https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/image-20221016151433175.png)

### 画圆

长按形状工具，可以选择椭圆工具，按住shift可以画出正圆。注意画的这个圆在镜头1上画

![image-20221016152336427](https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/image-20221016152336427.png)

### 绑定圆

不能直接把圆绑定目标的，需要建立空对象

![image-20221016152627994](https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/image-20221016152627994.png)

新建好了后，我们绑定这个空对象

![image-20221016153546828](https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/image-20221016153546828.png)

![image-20221016153742846](https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/image-20221016153742846.png)

### 父级连接

我们使用父级连接，把空对象和红色正圆结合起来。

就是把那个蚊香一样的东西，链接到空对象就行。

这个时候呢，空对象成了父亲，红色正圆是儿子。红色正圆继承了空对象的位置属性。

![](https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/224.gif)

我们改变父亲的属性，儿子也会跟着改变。反过来单独改变儿子的属性，不影响父亲

## 8.AE模板初应用

后面的操作都是一样的，一个一个切镜头，一个一个改属性就行。

但是我们这里直接套模板了，先模仿再自己学习即可~



### 照片自动铺满屏幕：

![image-20221016172401453](https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/image-20221016172401453.png)

### 音频和画面对齐：

https://www.bilibili.com/cheese/play/ss821?bsource=link_copy 33分处

我的案例是捷径版，都打好标记了。演示下如何打标记

![image-20221017133056901](https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/image-20221017133056901.png)

快捷键是小键盘上的*号，由于我的笔记本键盘上没有。只能将就了……

![](https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/225.gif)

### 时间轴标记快速切换：

可以按数字1-9快速切换时间轴上的标记

下图我打了个31号标记。有个小问题怎样通过数字键快速定位两位数的标记呢？

譬如我想去15号标记，先后按下数字1和5。这样的结果却是先到标记1再去标记5.

![](https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/226.gif)

### 复制图层：

[李兴兴：三合一剪辑训练营_哔哩哔哩_bilibili](https://www.bilibili.com/cheese/play/ep32593?csource=Hp_searchresult&spm_id_from=333.337.0.0)33:50

ctrl+D复制图层后，两个图层一体双生。改一个另一个也会改变，就是浅拷贝啦~

[李兴兴：三合一剪辑训练营_哔哩哔哩_bilibili](https://www.bilibili.com/cheese/play/ep32593?csource=Hp_searchresult&spm_id_from=333.337.0.0)34：30秒有解决方案，非常麻烦

记录下老师的解决办法：

#### 1.浅拷贝

![image-20221017135905247](https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/image-20221017135905247.png)

#### 2.在项目中显示图层源

![image-20221017140046895](https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/image-20221017140046895.png)

#### 3.在项目中复制合成

快捷键也是ctrl+D，我还改了名字。

![](https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/227.gif)

#### 4.把复制好的合成拖过来

<span style="color: red">一定要按住alt再拖动</span>

![](https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/228.gif)

#### 5.有两种情况

如果这个合成里面没有额外的子合成，可以不用管了。如果有，就属于嵌套合成的情况，按照1-4的步骤不断迭代即可。退出条件就是没有嵌套合成了。

<span style="color: red">注意</span>

经过我的测试，如果一个嵌套合成里面有其他非合成素材，改变那些素材没有影响，类似JS里的原始类型

## 9.部分导出

快捷键B设立起始位置，快捷键N设立结束位置。ctrl+M通过Media Encoder导出即可

36集就讲过

我的作业：【学习AE的第二天】 https://www.bilibili.com/video/BV1KR4y197WT?share_source=copy_web&vd_source=cdf0752a2120c79bb83ec7f8f959aaaf

# 38.AE魔术

视频内容个人不是很喜欢，但是掌握制作方法还是很有必要的

## 1.前期准备

老师是把笔筒黏在桌子上的……

### 修改合成信息

在时间轴面板ctrl+k即可

![](https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/229.gif)

### 时间轴面板

[李兴兴：三合一剪辑训练营_哔哩哔哩_bilibili](https://www.bilibili.com/cheese/play/ep32594?csource=Hp_searchresult&spm_id_from=333.337.0.0)7分26处讲的很多时间轴面板的干货。简单记录下

#### 预览视频

![](https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/230.gif)

#### 工作区

之前讲导出视频时（37第9点）记录过快捷键B和N。本质其实是改变工作区

![](https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/231.gif)

### 时间轴吸附

按住shift键移动即可

![](https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/232.gif)

## 2.蒙版法

### 拼接吸附

就是拍的两端素材。简单拼接下即可

![](https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/233.gif)

![](https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/232.gif)

### 画蒙版

![image-20221017153738374](https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/image-20221017153738374.png)

### 加点音效

用原视频的音效，只截取笔落入笔筒的音效即可。

因为AE不能操作音频，我们耍个花招。

![image-20221017155033951](https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/image-20221017155033951.png)

### 蒙版细节

为了不穿帮，给蒙版加一个蒙版羽化使其光照过渡更自然。

![image-20221017155307998](https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/image-20221017155307998.png)

下面详细讲讲蒙版，我们建一个草稿合成玩玩

#### 4个基本参数

很简单自己玩玩就清楚了~

![](https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/234.gif)

![](https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/235.gif)

#### 关键帧

可以玩些花活~

![](https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/236.gif)

#### 集合

我又画了几个蒙版，没有仔细研究过。就是数学上集合的概念。

![](C:\Users\FengXiao7\Pictures\GIF\237.gif)

#### 钢笔工具

**添加和删除定点**

长按钢笔图标即可切换工具

![](https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/238.gif)

**切换定点**

应该是弄成贝塞尔曲线，可以使边缘更圆滑

下图单改一边的轨迹是按住alt键再修改

![](https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/239.gif)

## 3.补帧法

前期把一些对话镜头衔接上

重点处理5和6号镜头

![](https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/240.gif)

我们还是先吸附

![image-20221017162350379](https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/image-20221017162350379.png)

### 画蒙版

和之前的蒙版法一模一样

![image-20221017162900691](https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/image-20221017162900691.png)

这里我先只画一个蒙版。正常速度看不出问题，但是如果一帧一帧看就有问题了。

不同于之前的绿衣小伙，他抛的轨迹出了屏幕外，找不到漏洞。

![](https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/241.gif)

### 发现问题

但是李老师抛的轨迹有问题，一帧一帧慢放，有个瞬移。

![](https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/242.gif)

精益求精，我们还是要做到最好。

这个时候就需要用补帧法了~

### 补帧动画

拿一个笔的照片，只需要4帧的时间即可

#### 4个常用快捷键

位置快捷键：P （postion）
缩放快捷键：S  （Scale）
旋转快捷键：R   （rotation）
透明度快捷键：T  （ransparency）

下图中的效果唤出位置后，还想继续唤出缩放就按shift+S，旋转就按shift+R

![](https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/243.gif)

#### 大体步骤

- 做一个关键帧动画
- 加上点运动模糊
- 把运动轨迹做一下
- 把原来的轨迹掩盖掉即可

#### 起始位置

老师的参数。4个参数都打关键点

![image-20221017171938212](https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/image-20221017171938212.png)

#### 定向模糊

![image-20221017172719534](https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/image-20221017172719534.png)

#### 结束位置

定向模糊也打个关键帧

![image-20221017173431700](https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/image-20221017173431700.png)

#### 抛物线运动轨迹

关键帧动画的直线运动很假诶~

![image-20221017173619400](https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/image-20221017173619400.png)

选中位置，出现两个小点。调整贝塞尔曲线即可

![](https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/244.gif)

#### 掩盖原来的运动轨迹

需要一张干净的天花板素材，PR里面用的是导出帧。AE也有不过更麻烦，需要自己输出图片序列。

可以看老师的操作步骤[李兴兴：三合一剪辑训练营_哔哩哔哩_bilibili](https://www.bilibili.com/cheese/play/ep32594?csource=Hp_searchresult&spm_id_from=333.337.0.0)27:45

![](https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE(50).png)

不知道为啥我导出来的图片太小了……

![image-20221017180722000](https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/image-20221017180722000.png)

后面两个重复即可



## 4.RGB分离效果

我称之为抖音效果

![image-20221017220742899](https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/image-20221017220742899.png)



![image-20221017221150931](https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/image-20221017221150931.png)

![image-20221017221600245](https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/image-20221017221600245.png)

注意点亮一个素材的音效就可以了

### 摇晃效果

AE里面也有表达式，我们利用表达式达到摇晃的效果，不是很难。后续老师会详细讲解

切割要点是根据音效来的。

![image-20221017230638538](https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/image-20221017230638538.png)

后面的尾巴少了一两帧，只保留最后一段尾巴。然后把颜色通道改为正常颜色就行啦
