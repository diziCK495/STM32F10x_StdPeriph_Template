# STM32F103C8Tx 模板工程
本工程使用stm32标准外设驱动库(SPL)作为片上外设驱动库.作为模板参考用
## 前置依赖
### 软件:
- vs code
- stm32cubeCLT

安装过程不在此赘述,可参考st官方在bilibili的视频[`安装STM32 VS CODE扩展`](https://www.bilibili.com/video/BV1Um421g7hM)和[`使用STM32 VS CODE扩展创建项目`](https://www.bilibili.com/video/BV19f421q7RZ)
### 版本要求:
- CubeCLT:最低`1.15.0`
- STM32 VS Code扩展:`2.x.x`
## 如何使用
满足依赖条件.用vscode打开工程文件夹,在下方工具栏找到`构建`即可(目前版本为齿轮形状图标).

正常情况可以看到编译时日志如下(最后几行)
```bash
[build] Memory region         Used Size  Region Size  %age Used
[build]              RAM:        1976 B        20 KB      9.65%
[build]            FLASH:         772 B        64 KB      1.18%
[build]    text	   data	    bss	    dec	    hex	filename
[build]     768	      4	   1972	   2744	    ab8	[工程所在目录]STM32F10x_StdPeriph_Template/STM32F10x_StdPeriph_Template/build/debug/STM32F10x_StdPeriph_Template.elf
[driver] 生成完毕: 00:00:01.678
[build] 生成已完成，退出代码为 0
```
这标志着配置无问题且可以正常生成目标文件

关于烧录下载则可参考st扩展中的`User guide`选项中的内容,这里也不多赘述.

## 一些可能遇到的问题
### 没有烧录选项
如果发现没有烧录的选项,则可尝试通过st扩展下的`Import CMake project`选项手动导入工程
### 复制文件夹过后发现编译失败
可能是没清理编译缓存导致的,可以删除工程目录下`/build`文件夹,或者在上菜单栏`终端->运行任务`选择`CMake:clean rebuild`