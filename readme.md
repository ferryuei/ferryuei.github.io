## 重新编译rv工具链

### 1 安装必要工具

```shell
yum install autoconf automake python3 libmpc-devel mpfr-devel gmp-devel gawk bison flex texinfo patchutils gcc gcc-c++ zlib-devel expat-devel
```



### 2 编译

```shell
./configure --prefix=/newdisk/riscv-gnu-toolchain/tmp --with-arch=rv32imc --with-abi=ilp32
make 
```

默认为imc，可以设置为i/im/imc等，abi选项设置的是浮点数表示方式。



官方步骤参考：

```shell
git clone https://github.com/riscv/riscv-gnu-toolchain riscv-gnu-toolchain-rv32i
cd riscv-gnu-toolchain-rv32i
git checkout 411d134
git submodule update --init --recursive

mkdir build; cd build
../configure --with-arch=rv32i --prefix=/opt/riscv32i
make -j$(nproc)
```
