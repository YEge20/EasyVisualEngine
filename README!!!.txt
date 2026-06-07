欢迎使用EasyVisual!!!
1.EasyVisual是一个快速构建图形场景应用的引擎
2.EasyVisual目前只支持Windows平台，但支持拓展到其他平台。
3.BuildProjects-Win64-VS2022.bat只生成VS2022的工程，如果你的版本太低请自行修改bat文件！

EasyVisual工程初始化步骤：
1.请先运行VulkanSDK安装程序(需要自己上网下载安装包)完成安装！记得在安装时勾选拓展工具！以防缺库(提示：SDL2也不需要因为我们使用GLFW生成窗口，ARM64的那个可以不用因为用不上，glm也可以不用，因为我们的引擎里已经提供，Volk也不需要因为用不上)
2.接着运行BuildProjects-Win64-VS2022.bat开始配置工程文件，全程自动等待终端提示结束即可。

工程文件说明：
1.EasyVisualEngine是引擎，是构建应用程序的核心。属于静态库
2.EasyVisualScriptCore是引擎的嵌入式程序的核心，使用C#语言进行快速编程，是编辑器构建应用程序的核心之一，注意使用的是mono框架，该核心库在vendor/mono中，无需额外安装本地核心库。属于动态链接库
3.EasyVisualEditor是编辑器，用于快速构建2D场景游戏。属于exe启动项目，目前编辑器还没有加入热重载.dll文件，因此当你在EasyVisualScript中完成了脚本编译，请重启编辑器来重新加载新的.dll文件。当前编辑器的功能极其有限，如果时机正确会考虑公开编辑器源代码，供所有人参考、修改和发布！
4.SandBox是沙盒程序，用于测试引擎，也是一个使用引擎的一个最基本的示例。属于exe启动项目

提示：
1.本工程文件使用premake5配置，详细的配置在每个项目的premake5.lua文件里，如有需求可以根据实际情况进行修改。修改后不确保稳定性
2.如果你的VulkanSDK作出修改(比如更新版本或者更改路径等)，请完成后重新再运行一次BuildProjects-Win64-VS2022.bat更新工程配置，以防出问题
3.如果你想要基于该引擎构建一个自定义的程序，可以参考SandBox文件中的premake5.lua文件，作出适当的调整，最后在工程主目录下的premake5.lua中导入它！然后再重新运行BuildProjects-Win64-VS2022.bat就会自动帮你生成工程文件!!!