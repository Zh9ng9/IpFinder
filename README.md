# IpFinder
使用右键菜单进行快速的txt按行查询。配合各种扫描器使用，提升打工速度。



如果扫描器的扫描结果按照ip分组，看起来会很乱，想从大段txt里面找到某一个ip结果，最常用的命令是

```
type result.txt | find "xxxxxx"
```

为了提高连续查多个ip的效率，将此bat放在文件的右键菜单，方便查找结果，相当于连续type+find。

**最终结果：**

右键txt文件，选中IpFinder，打开cmd框：

![image.png](https://s2.loli.net/2022/07/12/I12KHgomNOFC76s.png)

![H40QHII8@1AX_S_O3X6U2_T.png](https://s2.loli.net/2022/07/12/sRAUewOBQGydzmS.png)

**Step 1：**

某个不会变动的目录下写一个IpFinder.bat

```
@echo off
echo   __  ____    ____  __  __ _  ____  ____  ____ 
echo (  )(  _ \  (  __)(  )(  ( \(    \(  __)(  _ \
echo  )(  ) __/   ) _)  )( /    / ) D ( ) _)  )   /
echo (__)(__)    (__)  (__)\_)__)(____/(____)(__\_)
echo=
echo 当前打开的文件：%1
set x = 1
:label
echo ---------------------------------------------------------------------------------------
set /p x="请输入需要查询的内容："
type %1 | find "%x%"
goto :label
pause
```

**Step 2：**

win+r regedit 

/HKEY_CLASSES_ROOT/*/shell 按图增加一个IpFinder，内部加command，数据改为bat路径以及%l（小写L）

![V3PQ_AI_P_`F5GJ_670PR_V.png](https://s2.loli.net/2022/07/12/2MOVmf86DYlvHNb.png)

**step 3:**

完成
