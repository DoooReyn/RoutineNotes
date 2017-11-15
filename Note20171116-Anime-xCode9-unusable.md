1. 创建了一个用于`Cocos2d-x`的简洁动画库[Anime](https://github.com/DoooReyn/Anime)，以后就可以愉快快速地创建动画了。
2. xCode9 运行 iOS 模拟器奇慢无比的官方解释和临时解决办法：
> Update: This bug is fixed in Xcode 9.1 beta 2.
<br/><br/>
    There is a bug in OpenGLES.framework in the iOS 11/tvOS 11/watchOS 4 Simulators that causes them to skip loading the LLVM JIT and fall back to interpreting shaders. This has a severe performance impact on the Simulator since it is entirely software-rendered OpenGL (this includes CoreAnimation, SceneKit, etc).
<br/><br/>
    As a temporary workaround you can copy libCoreVMClient.dylib from Beta 3 into the Xcode 9 GM and performance should be restored to what it was previously. This must be done for each platform runtime separately. Make sure you do a backup of the old file first, and be aware that each platform has its own unique binary so you cannot copy the same dylib into all three directories (nor can you use the one from macOS).
<br/><br/>
    Did I mention making a backup first?
<br/><br/>
    This is not an officially supported configuration and is only intended as a temporary workaround.
<br/><br/>
    For iOS this is located at:
    `Xcode[-beta].app/Contents/Developer/Platforms/iPhoneOS.platform/Developer/Library/CoreSimulator/Profiles/Runtimes/iOS.simruntime/Contents/Resources/RuntimeRoot/System/Library/Frameworks/OpenGLES.framework/libCoreVMClient.dylib`
<br/><br/>
    For tvOS this is located at:
    `Xcode[-beta].app/Contents/Developer/Platforms/AppleTVOS.platform/Developer/Library/CoreSimulator/Profiles/Runtimes/tvOS.simruntime/Contents/Resources/RuntimeRoot/System/Library/Frameworks/OpenGLES.framework/libCoreVMClient.dylib`
<br/><br/>
    For watchOS this is located at:
    `Xcode[-beta].app/Contents/Developer/Platforms/WatchOS.platform/Developer/Library/CoreSimulator/Profiles/Runtimes/watchOS.simruntime/Contents/Resources/RuntimeRoot/System/Library/Frameworks/OpenGLES.framework/libCoreVMClient.dylib`

    最后智能的网友朝你扔过来一个[libCoreVMClient.dylib](https://www.dropbox.com/s/gxyilamdoa3rs4c/libCoreVMClient.dylib?dl=0)的下载链接。
