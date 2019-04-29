## 蜂鸣器

**问题1：**

DGUS屏如果关闭某个触控，让其点击的时候没有声音。

**解决方法：**

DGUS屏的触控勾选右上角语音，让其设置一个语音段数，这是利用DGUS语音播放的原理，由于不是外接喇叭的语音屏，按键就会没有声音。

串口指令屏，不能关闭某个触控的声音，如果关闭蜂鸣器就是整体都关闭。

 

**问题2：**

DGUS 屏如何关闭所有触控的声音?

**解决方法：**

DGUS屏配置CONFIG.TXT ,RC=20即可。

Mini DGUS 和标准DGUS屏不同，没有RC的选项，配置R2.1=1则为关闭。

 

**问题3：**

DGUS屏能否通过发指令实现蜂鸣器用指令打开和关闭，即静音功能？

**解决方法：**

最新的V71内核可以通过1D寄存器写入5A或者A5配置11~1C寄存器映射系统配置config.txt文件的R1-RC，进行修改，

5A A5 03 80 1C 20  5A A5 03 80 1D 5A 触摸屏按钮声音关闭 静音

5A A5 03 80 1C 00  5A A5 03 80 1D 5A 触摸屏按钮声音开启

注意：对于已经开启了DWIN_OS的屏，在串口进行修改了RC的时候，不要忘记连带RC=40开启。当然，用OS的程序控制屏的蜂鸣器开启和关闭同样非常方便。

 

**问题4：**

DGUS屏的蜂鸣器怎么没有声音了？（系统配置正常，怀疑硬件的原因）

**解决方法：**

1、把[万用表](https://www.baidu.com/s?wd=%E4%B8%87%E7%94%A8%E8%A1%A8&tn=SE_PcZhidaonwhc_ngpagmjz&rsv_dl=gh_pc_zhidao)打到“通断档”，把两表笔连续接触[蜂鸣器](https://www.baidu.com/s?wd=%E8%9C%82%E9%B8%A3%E5%99%A8&tn=SE_PcZhidaonwhc_ngpagmjz&rsv_dl=gh_pc_zhidao)两只脚，好的蜂鸣器会发出微小的[滴滴](https://www.baidu.com/s?wd=%E6%BB%B4%E6%BB%B4&tn=SE_PcZhidaonwhc_ngpagmjz&rsv_dl=gh_pc_zhidao)声，没有响声就是可能蜂鸣器坏了。

2、检查蜂鸣器附近的一颗电阻是否虚焊等。

