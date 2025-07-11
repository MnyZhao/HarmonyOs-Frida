# HarmonyOS frida hook

> Good News.
> 经过各种努力，终于实现了鸿蒙Next的frida hook。

## 前提条件：

> 在鸿蒙Next进行frida hook，首先要准备root的环境，目前有2种可能，1）openharmony 2）模拟器root

## 简单回顾一下实现过程，希望对大家有帮助

1. 鸿蒙Next系统是基于linux，选定方向就是frida gadget linux版本
2. 对鸿蒙Next有2个问题需要处理，c hook 和 TS hook
3. 先考虑 c hook
   + Frida通过 Hook libc 函数实现动态监控和篡改；在Frida启动后会主动注入zygote进程，并hook一些libc函数，包括exit、_exit、abort等退出相关函数，以及fork等进程操作函数。
     在鸿蒙Next需要对muslc的hook来实现native函数的动态监控和篡改。
4. 修改frida gadget linux，重新编译

测试验证成功~！！
