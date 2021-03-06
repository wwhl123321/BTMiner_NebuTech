# BTM GPU挖矿软件（NebuTech BTMiner）

用于Nvidia显卡的BTM（比原链）挖矿软件。

## 下载地址

[从这里下载](https://github.com/NebuTech/BTMiner_NebuTech/releases)

## 特点：

* 支持Windows、Linux（测试过Ubuntu16.04）
* **Windows图形界面操作**
* 支持标准stratum协议的矿池，测试过：[f2pool](https://www.f2pool.com/)、[antpool](https://www.antpool.com/)、[btcc](https://pool.btcc.com/)
* 几乎不占用CPU和PCI-E带宽，现有6卡、8卡矿机适用
* 可选的CPU加速模式，在拥有高端CPU及高PCIE带宽的机器上进一步提升算力

## 使用方法：

1. **更新到最新版本的Nvidia显卡驱动，不支持旧版本驱动。（驱动版本需大于等于396）**
2. **双击`GUI_Wrapper.exe`打开windows图形界面开始挖矿。**
2. 使用记事本打开`Windows.bat`文件(Linux系统修改`Linux.sh`)，修改`-url`后面的矿池地址和`-user`后面的钱包地址或用户名。如果有密码，添加`-p`参数和密码。
3. Windows双击运行`Windows.bat`开始挖矿, Linux通过命令行运行`Linux.sh`开始挖矿。

## 参考显卡性能

![](/performance.png)

## 命令行参数：

BTMiner_NebuTech.exe [参数]

典型用法：BTMiner_NebuTech.exe -url btm.f2pool.com:9221 -user bm1xxxxxxxxxxxx.rigName -p x

参数：

  * -?, -h, --help      显示帮助信息.
  * -v, --version       显示版本号.
  * -u, --url <url>     矿池地址.
  * -U, --user <user>   挖矿使用的用户名或钱包地址.
  * -p, --passwd <password>	挖矿使用的密码.
  * -d, --devices <devices>	指定使用哪些显卡来挖矿. 比如: "-d 0,1,2,3" 使用前4个显卡.
  * **-C, --use-cpu     使用这个选项开启CPU加速模式。如果你有一颗强大的CPU和插在PCI-E x16插槽上的显卡，可以尝试开启这个选项来进一步提升算力.**
  * **-M, --more-gpu      使用这个选项可避免"cuda out of memory error"，可能会有小部分的算力损失.**

## 开发手续费（Dev Fee）

3%

## 故障排查

TODO

## 致谢

@earthGavinLee

## 修改记录：

#### v3.3(2018-06-16)

* GUI界面增加配置自动保存恢复功能
* 修复经常崩溃的bug，提升稳定性。

#### v3.0(2018-06-09)

* 大幅提升算力
* 自动优化选择上个版本的`-i`参数
* 增加`-M`选项，应对多卡时可能出现的`CUDA out of memory error`
* Windows增加图形界面壳程序，便于新手操作
* 图形界面增加公告，获取最新版本通知
* 修复已知BUG，提升稳定性。

#### v2.0(2018-06-04)

* 进一步降低CPU使用率。
* 增加针对高端CPU及高PCIE带宽的加速模式。
* 支持Linux
* 修复已知BUG，提升稳定性。

#### v1.3(2018-06-03)

* 第一版。
* 支持Windows。
* 优化CPU、PCI-E带宽占用。
* 优化挖矿速度。
* 支持标准stratum协议。
