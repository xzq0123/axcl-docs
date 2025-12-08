# SDK 编译

1.  进入主控编译目录

   ```bash
   cd axcl/build
   ```

2.  编译

   ```bash
   # 一次全编译
   make clean && make host=x86 clean && make host=arm64 clean
   make all install -j128 && make host=x86 all install -j128 && make host=arm64 all install -j128

   # 或者依次编译各个主控
   make clean && make all install -j128
   make host=x86 clean && make host=x86 all install -j128
   make host=arm64 clean && make host=arm64 all install -j128
   ```

| 编译选项                     | 说明                                            | 编译输出路径                  |
| :-------------------------- | ---------------------------------------------- | ----------------------------- |
| `host=ax650`或者省略`host=`  | 适用于主控芯片是AX650N                            | axcl/out/**axcl_linux_ax650** |
| `host=x86`                  | 适用于主控芯片是X86架构，比如INTEL、AMD64           | axcl/out/**axcl_linux_x86**   |
| `host=arm64`                | 适用于其他ARM64主控芯片，比如RK3588、树莓派5等       | axcl/out/**axcl_linux_arm64** |
