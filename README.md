# Android 屏幕适配

px/dp/sp 之间的换算关系：

- px 平常所说的1920×1080只是像素数量，也就是1920px×1080px，代表手机高度上有1920个像素点，宽度上有1080个像素点。
- dpi 要想判别手机屏幕的显示好坏，还要考虑屏幕的宽高(英寸)，也就是用dpi即每英寸多少像素来评价屏幕的显示效果。
（不然假如手机分辨率是1920×1080，但是屏幕是几十寸的，那显示效果将不会很好，甚至你有可能看到小的像素块，那将更影响视觉效果。）

- dp 其实dp就是为了使得开发者设置的长度能够根据不同屏幕(分辨率/尺寸也就是dpi)获得不同的像素(px)数量。比如：我将一个控件设置长度为1dp，那么在160dpi上该控件长度为1px，在240dpi的屏幕上该控件的长度为1*240/160=1.5个像素点。
     也就是dp会随着不同屏幕而改变控件长度的像素数量。
     关于dp的官方叙述为当屏幕每英寸有160个像素时(也就是160dpi)，dp与px等价的。那如果每英寸240个像素呢？1dp—>1*240/160=1.5px，即1dp与1.5px等价了。
     其实记住一点，dp最终都要化为像素数量来衡量大小的，因为只有像素数量最直观
     
- dp px 转换：前面已经看到一个例子了如下(注：等号都是等价，是理解上的等于，不是直接的等于的)：安卓中如果手机每英寸有160px，
即手机是160dpi，那么此时1dp就可以理解为1px，假如现在手机是240dpi，那么1dp=240/160 px=1.5px，  从上可以看出dp转px只与屏幕的dpi有关。
对于android 来说，最终我们能读懂或者衡量的都是px，所以最后我们都将dp化为px好理解一点。我总结了dp转px的公式如下：
公式：dp值×（当前dpi/160dpi）=>得出当前的像素数目

- 手机屏幕最大的dp是多少 所以要得到全屏最长的的dp，就等于160*宽(或者高英寸长) 如第三个1080*1920例子，160*3=480dp，
所以0-480dp就是宽的dp范围。因为480*360/160=1080个像素，正好等于宽的最大像素数量

- sp 与缩放无关的抽象像素（Scale-independent Pixel）。sp和dp很类似但唯一的区别是，Android系统允许用户自定义文字尺寸大小
（小、正常、大、超大等等），当文字尺寸是“正常”时1sp=1dp=0.00625英寸，而当文字尺寸是“大”或“超大”时，1sp>1dp=0.00625英寸
。类似我们在windows里调整字体尺寸以后的效果——窗口大小不变，只有文字大小改变


引用:

[https://www.cnblogs.com/JLZT1223/p/6784449.html]
