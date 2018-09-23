这是windows下的独立caffe工程模板。你可以使用这个工程来构建自己的caffe程序，而不需要自己去编译caffe框架。			

### 使用说明			

#### 1、文件夹目录			

下面列出的是此工程的主要文件，请注意：				
CaffeTemplateWin			

---->CaffeTemplate.sln			

---->CaffeTemplate			

---->CaffeDependencies			

---->---->CaffeInclude			

---->---->CaffeRelease				

---->---->NugetPackages				

---->---->CaffeCommonSettings.props		

&emsp;&emsp;1、CaffeTemplate.sln是vs2013的启动文件。								

&emsp;&emsp;2、CaffeTemplate文件夹是vs2013的工程目录，这个不用做修改。		

&emsp;&emsp;3、CaffeDependencies下存放的是所有的caffe相关的依赖包，由于文件比较大，我单独上传到了百度网盘，请从[这里](https://pan.baidu.com/s/12lff-Mn8Jja1d1CMUkvtXA)下载。CaffeInclude文件夹存放所有的caffe的头文件，把下载到的CaffeInclude.zip文件解压，并将文件夹内所有文件复制到CaffeInclude下。CaffeRelease文件夹存放caffe编译出来的文件，从上面给出的链接里下载Release.zip文件，解压后将里面所有的文件复制到CaffeRelease下面（Release.zip里面的pycaffe文件夹可以不复制，它是caffe的python接口）。NugetPackges文件夹存放的是caffe的windows依赖包，同样可以从的链接下载。CaffeCommonSettings.props是vs的配置文件，在主文件夹下，相信你已经看到了，把它复制到这里即可。			

&emsp;&emsp;4、***一定要严格按照我给出的文件夹目录放置文件，因为工程里设置的路径都是相对路径，文件放错了位置后编译会出错。***			

#### 编译工程			

&emsp;&emsp;文件都下载好之后，打开CaffeTemplate.sln（我用的是vs2013）。在配置管理器选择x64，配置属性里，VC++包含目录添加cuda头文件目录。其他路径都是都是相对路径，可以不用修改。如果你要编写自己的程序，可以参考caffe的classification.cpp文件，此工程下的CaffePredict文件就是参照该文件写的。接下来就可以编译了。			

***说明：win版的caffe使用的是opencv2.4，所以此工程使用的也是opencv2.4.如果你电脑里已经编译了其他版本的opencv，请不要加入到工程中来，否则编译会出错。如果你确实想使用其他版本的opencv，请自己尝试修改工程，尤其是CaffeTemplate.vcxproj文件***。