题干：给了我们一个ssh的地址

拿到这类题目一般先去分析它的进程目录、启动命令还有一些关键的包名比如说/proc下的一些文件内容之类的，再去查看内容展示进程用到的内存如/proc/maps之类的文件内容

进程中一些task子线程之类的也是关注的重点，或者在查一下maps中的内存使用概况，最后就是查看envion环境变量和相应配置

题目分析 既然给到了我们ssh的地址，我们直接连接xshell cat一下它的根目录查看有无线索

![image-20230527170129900](C:\Users\hxd\AppData\Roaming\Typora\typora-user-images\image-20230527170129900.png)

再使用ll查看命令查看有无flag的信息

查看proc进程

cd进proc进程的目录ll一下

![image-20230527170137096](C:\Users\hxd\AppData\Roaming\Typora\typora-user-images\image-20230527170137096.png)

ls查看进程

cat进程目录中的查看环境变量配置

![image-20230527170149391](C:\Users\hxd\AppData\Roaming\Typora\typora-user-images\image-20230527170149391.png)



这里我们想先查看一下环境变量，再分析线程之类的信息，这里用*代替中间变量，task下直接找到环境变量，意外发现flag就在环境变量中

在环境变量配置中找到flag

![image-20230527170205076](C:\Users\hxd\AppData\Roaming\Typora\typora-user-images\image-20230527170205076.png)