# Injection 使用

参考自 https://mp.weixin.qq.com/s/hFnHdOP6pmIwzZck-zXE8g

## 1.在Mac App Store 中下载InjectionIII 安装

在Xcode中打开项目，在appdelegate中 方法- (BOOL)application:(UIApplication *)application didFinishLaunchingWithOptions:(NSDictionary *)launchOptions   加入以下代码：


```
#if DEBUG
    // iOS
    [[NSBundle bundleWithPath:@"/Applications/InjectionIII.app/Contents/Resources/iOSInjection.bundle"] load];
    // tvOS
    //    [[NSBundle bundleWithPath:@"/Applications/InjectionIII.app/Contents/Resources/tvOSInjection.bundle"] load];
    // macOS
    //    [[NSBundle bundleWithPath:@"/Applications/InjectionIII.app/Contents/Resources/macOSInjection.bundle"] load];
#endif
```

## 2.在需要修改的类中加入injected方法


```
- (void)injected
{
    //TODO reload UI
    //[self buildConstraints];
}

```
在我们修改了对应文件按下COMMAND + S后，Injjection就开始编译修改过的文件为动态库,并且重绘UI，
***必须在模拟器中运行***

    

