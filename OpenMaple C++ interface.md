#Ubantu下OpenMaple的C++调用

---

首先，在官方文档[ProgrammingGuide.pdf](https://www.maplesoft.com/documentation_center/maple2019/ProgrammingGuide.pdf)中存在对于OpenMaple的使用描述，本文只是针对C++调用进行总结。

##环境配置##

配置**动态链接库路径**以及**头文件路径**。

具体是在/home/xxx/.bashrc里添加：

`export CPLUS_INCLUDE_PATH=/.../maple2018/extern/include:$CPLUS_INCLUDE_PATH`

`export CPLUS_INCLUDE_PATH=/.../maple2018/bin.X86_64_LINUX:$CPLUS_INCLUDE_PATH`

`export LD_LIBRARY_PATH=/.../maple2018/bin.X86_64_LINUX:$LD_LIBRARY_PATH`

`export LIBRARY_PATH=/.../maple2018/bin.X86_64_LINUX:$LIBRARY_PATH`

另外，还需要配置MAPLE路径(即安装路径)：

`export MAPLE="/.../maple2018"`

`. $MAPLE/bin/maple -norun`

---

##编译##

先建立test.cpp，并编写代码（这里使用/maple2018/samples/OpenMaple/simple/simple.c中的示例代码）。

然后进行编译，**编译命令**为：
`g++ -I $MAPLE/extern/include test.cpp -o test -L $MAPLE/bin.X86_64_LINUX -lmaplec -lmaple -lhf -lprocessor`

编译成功后，运行：
`./test`

运行成功。
