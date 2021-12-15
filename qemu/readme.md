
# 关于平头哥qemu的编译和运行

首先下载qemu

```
git clone git@github.com:T-head-Semi/qemu.git
```

接着开始进行编译

```
../configure --disable-werror --prefix=$CI_PROJECT_DIR/thead_qemu --disable-vnc --disable-sdl --disable-sdl-image --target-list=riscv32-softmmu,riscv64-softmmu && make -j8 && make install
```

编译完成后可以直接看到结果

```
./qemu-system-riscv32 -M ?
Supported machines are:
none                 empty machine
opentitan            RISC-V Board compatible with OpenTitan
sifive_e             RISC-V Board compatible with SiFive E SDK
sifive_u             RISC-V Board compatible with SiFive U SDK
smartl               RISC-V smartl
spike                RISC-V Spike board (default)
virt                 RISC-V VirtIO board
```
可以看到展示的machine.

接着可以查看`cpu`的支持情况。

```
./qemu-system-riscv32 -M opentitan -cpu ?
any
e902
e902m
e902mt
e902t
e906
e906f
e906fd
e906fdp
e906fp
e906p
e907
e907f
e907fd
e907fdp
e907fp
e907p
lowrisc-ibex
rv32
sifive-e31
sifive-e34
sifive-u34
```

在32位的模式下，支持的是e系列的处理器。

```
./qemu-system-riscv64 -M opentitan -cpu ?
any
c906
c906fd
c906fdv
c910
c910v
c920
rv64
shakti-c
sifive-e51
sifive-u54
```
在64位的模式下，有c系列的处理器。


下面是已经自己编译好的linux版本和windows版本的qemu程序

```
链接：https://pan.baidu.com/s/1FrNJNorfn4Z8orowS_hngQ 
提取码：54ol 
```