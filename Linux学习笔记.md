## 指令操作

 `ctrl c`：取消命令，并且换行

`ctrl u`：清空本行命令

`tab键`：可以补全命令和文件名，如果补全不了快速按两下tab键，可以显示备选选项

`ls`：列出当前目录下所有文件，蓝色的是文件夹，白色的是普通文件，绿色的是可执行文件

`pwd`：显示当前路径

`cd XXX`：进入`XXX`目录下, 

`cd ../`：返回上层目录

`cp XXX YYY`：将xx文件复制成`YYY`，`XXX`和`YYY`可以是一个路径，比如`../dir_c/a.txt`，表示上层目录下的`dir_c`文件夹下的文件`a.txt`

`mkdir XXX`：创建目录`XXX`

`rm XXX`：删除普通文件：

`rm XXX -r`：删除文件夹

`mv XXX YYY`：将`XXX`文件移动到`YYY`，和`cp`命令一样，`XXX`和`YYY`可以是一个路径﹔重命名也是用这个命令

`touch XXX`：创建一个文件

`cat XXX`：展示文件`XXX`中的内容

### 相关练习

0. 进入homework_0文件夹，分别创建文件夹`dir_a, dir_b,dir_c`

```shell
cd homework_0
mkdir dir_a dir_b dir_c

```

1. 进入homework_1文件夹，将a.txt，b.txt,c.txt分别复制成:`a.txt.bak, b.txt.bak,c.txt.bak`

```shell
cd homework_1
for var in *.txt;
do 
    cp "$var" "${$var%.txt}.txt.bak"
done
```

2. 进入homework 2文件夹，将`a.txt,b.txt,c.txt`分别重命名为:`a_new.txt,b_new.txt,c_new.txt`

```shell
cd homework_2
for var in *.txt;
do 
    cp "$var" "${$var%.txt}.new.txt"
done
```



3. 进入`homework _3`文件夹，将`dir_a`文件夹下的`a.txt,b.txt,c.txt`分别移动到文件夹`dir_b`下

```shell
cd homework_3
mv dir_a/* dir_b
```

4. 进入`homework_4`文件夹，将普通文件`a.txt, b.txt,c.txt`删除

```shell
cd homework_4
rm *
```

5. 进入`homework_5`文件夹，将文件夹`dir_a, dir b, dir_c`删除

```shell
cd homework_5
rm * -r
```

6. 进入`homework_6`文件夹，查看`task.txt`的内容，并按其指示进行操作

```shell
cd homework_6
cat task.txt
// 将task.txt重命名为done.txt，创建目录dir_a，将done.txt移动到目录dir_a下
mkdir dir_a
mv task.txt dir_a/done.txt
```



7. 进入`homework_7`文件夹，创建文件夹`dir_0, dir_1, dir_2`,将`a.txt,b.txt,c.txt`复制到`dir_0`下，重命名为`a0.txt,b0.txt,c0.txt`;将`a.txt,b.txt,c.txt`复制到`dir_1`下，重命名为`a1.txt, b1.txt,c1.txt`;将`a.txt,b.txt,c.txt`复制到`dir_2`下，重命名为`a2.txt,b2.txt,c2.txt`;

```shell
cd homework_7
for i in {0..2}
do 
	mkdir "dir_$i"
	for var in *.txt
	do 
		cp "$var" "dir_$i/${var%.txt}$i.txt"
	done
done
```



8. 进入`homework_8`文件夹，分别在`dir_a, dir_b, dir_c`文件夹下查看`task.txt`的内容，并分别按照指示进行操作

```shell
cd homework_8
cd dir_a
cat task.txt
// 将a.txt删除
rm a.txt
cd ../dir_b
cat task.txt
// 将b.txt重命名为b_new.txt
mv b.txt b_new,txt
cd ../dir_c
cat task.txt
// 将c.txt复制成c.txt.bak
cp c.txt c.txt.bak
```

9. 进入`homework_9`文件夹，将其中所有`txt`类型的文件删除

```shell
cd homework_9
r
```



