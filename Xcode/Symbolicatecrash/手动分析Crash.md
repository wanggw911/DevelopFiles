# 手动进行崩溃分析

## 一、崩溃分析文件获取

### 1、symbolicatecrash 工具的获取

```
/应用程序/Xcode.app/Contents/SharedFrameworks/DVTFoundation.framework/Versions/A/Resources/
```

### 2、crash log的获取

### 3、dSYM 符号集的获取


## 二、把上述文件放在一个文件夹中，使用命令解析

### 1、解析命令

```
./symbolicatecrash ./xxx.crash ./xxx.app.dSYM > symbol.crash
```

```
./symbolicatecrash ./Amy.crash ./Amy.app.dSYM > AmySymbol.crash
./symbolicatecrash ./Amy-8Plus.crash ./Amy.app.dSYM > Amy-8PlusSymbol.crash
```

### 2、环境变量检查

* 执行：`xcode-select -print-path`
* 看是否打印：`/Applications/Xcode.app/Contents/Developer`
* 如果不是，则需要执行以下：`export DEVELOPER_DIR=/Applications/XCode.app/Contents/Developer`，再来重新解析

### 3、解析报错

```
Error: "DEVELOPER_DIR" is not defined at ./symbolicatecrash line 69.
```

**解决报错临时解决办法**
需要执行：`export DEVELOPER_DIR=/Applications/XCode.app/Contents/Developer`


## 三、一些参考
 
* 还不错的一篇文章：[iOS崩溃堆栈信息的符号化解析](https://www.jianshu.com/p/953f0961157a)


