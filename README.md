# libnfc-unofficial-x64-windows-build

[English](#English) | [Chinese](#Chinese)

# Chinese

这是一个[libnfc](https://github.com/nfc-tools/libnfc)的非官方构造，来源于[分支df0a3beca901b734c6e9037334feaffe604f99b0](https://github.com/nfc-tools/libnfc/tree/df0a3beca901b734c6e9037334feaffe604f99b0).

`Mingw32 Makefile`生成器无法生成x64二进制文件，所以这个项目由[Visual Studio 17 2022](https://visualstudio.microsoft.com/)构建. 源代码几乎没有修改（唯一改了的地方在`pcsc.h`里，加入`MAX_ATR_SIZE`的定义，除此之外源代码完全没动）。

[build-src](./build-src/)文件夹包含构建文件，对最终用户来说完全没用。

[Release](./Release/)文件夹包含启用了PCSC的发布版本。另一个没有启用PCSC的版本位于[Release_without_PCSC](./Release_without_PRSCS/)文件夹中。

要include的必要文件位于[includes](./includes/)文件夹中。记得将文件夹添加到项目的包含路径中。

## 用法
1. 下载这个repo
2. 打开文件夹`Release`
3. 将`nfc.lib`放入项目的依赖库
4. 将`includes`文件夹复制到项目中，并将其添加到项目的包含路径中
6. 在代码中`#include <nfc/nfc.h>`，然后使用
7. 最后别忘了将`Release/nfc.dll`和`Release/libusb0.dll`添加到发行版中

（**不建议**使用未启用PCSC的版本，据说ACR122U需要PCSC）

## LICENSE
同libnfc，（LGPL3.0）。

# English

This is an unofficial build of [libnfc](https://github.com/nfc-tools/libnfc), a library allowing applications to access NFC devices.

The source is from [branch df0a3beca901b734c6e9037334feaffe604f99b0](https://github.com/nfc-tools/libnfc/tree/df0a3beca901b734c6e9037334feaffe604f99b0).

The `Mingw32 Makefile` generator cannot generate x64 binaries, so the project is built by [Visual Studio 17 2022](https://visualstudio.microsoft.com/). The source code is almost original, excepting some small fixes on Windows. (In fact the only different is in the `pcsc.h`: added the define of `MAX_ATR_SIZE`)

The [build-src](./build-src/) folder contains building files, which is useless for the end user.

The [Release](./Release/) folder contains the final release, with PCSC enabled. Another version disabled PCSC is in [Release_without_PCSC](./Release_without_PCSC/) folder.

The necessary files to be included is in the [includes](./includes/) folder. Remember to add the folder to your project's include path.

## To use it...
1. Download the repo
2. Open the folder `Release`
3. Put the `nfc.lib` to your project libraries
4. Copy to the `includes` folder to your project
5. Add it to your include path of your project
6. `#include <nfc/nfc.h>` in your code and use it
7. Don't forget to put `Release/nfc.dll` and `Release/libusb0.dll` to your distribution!

(**NOT recommended** to use the version without PCSC, it is said that ACR122U requires PCSC)

## LICENSE
LGPL-3.0 (same as libnfc).

