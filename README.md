# Архитектура ядра [TezenRT] от Samsung

https://drive.google.com/drive/folders/1VYuaYKkbBFACNjZhE82jOKziJvamFrce

![Image alt](https://i.ytimg.com/vi/-nBfYb29HJ8/maxresdefault.jpg)

![Image alt](http://www.geek.com/wp-content/uploads/2012/07/Samsung-ES9000.jpg)

![Image alt](http://cdn.gadgetreview.com/wp-content/uploads/2015/05/LG-Wallpaper-Display.jpg)

![Image alt](http://europe-tc.ru/gallery/big/in_1686.jpg)

![Image alt](https://images.samsung.com/is/image/samsung/p5/sg/business/solutions/industry-solutions/hospitality-solutions/feature-images/hospitality-solutions-feature-images-4-3-magic-info-large.jpg)


# Разработка модулей ядра Linux

https://www.youtube.com/playlist?list=PLrTrFnOkIFb0712dNSb-_E0hJsjUZQVIo


# Разум создавший Linux [ted.com]

https://www.ted.com/talks/linus_torvalds_the_mind_behind_linux?language=ru

# Архитектура [Geode] Реверс инжениринг движка обработки финансовых транзакций в торговых платформах различных компаний на Уолл-стрит.
Geode был создан компанией Gemstone Systems в 2002 году и применяется в качестве высокопроизводительного движка обработки финансовых транзакций в торговых платформах различных компаний на Уолл-стрит.

В качестве примера внедрения Geode это Национальная железная дорога Китая, в которой кластер из 20 узлов (10 основных и 10 запасных) обеспечивает хранение 2 Тб оперативной информации о билетах. 
![Image alt](http://chinalogist.ru/sites/default/files/speed-railwas-of-china4.png)
![Image alt](https://i0.wp.com/www.wilowallstreet.com/wp-content/uploads/2015/11/100914_wall_street_605.jpg)

Архитектура [Geode] & Реверс инжениринг движка обработки финансовых транзакций
https://drive.google.com/drive/folders/1tetUejh8WzscoCbCHPsdILM6desm5GzX

# Архитектура [Voltdb]  хранение данных в памяти с концепцией распределенной 
https://github.com/gridgentoo/voltdb
https://drive.google.com/drive/folders/1YqYZIwWFvy1lP1NMOxrhZrMX7xZj-628

СУБД VoltDB 3.0, развиваемой под руководством Майкла Стоунбрейкера (Mike Stonebraker), одного из основателей проектов Ingres и PostgreSQL. СУБД VoltDB поддерживает горизонтальное масштабирование и ориентирована на обработку транзакций в реальном времени (OLTP). На недорогом кластере, собранном своими силами из обычных серверов, СУБД способна обрабатывать миллионы транзакций в секунду.

# Apache Hadoop Big Data with VoltDB
![Image alt](https://www.voltdb.com/wp-content/uploads/2017/03/Apache-Hadoop-Big-Data-VoltDB.gif)

Идея VoltDB заключается в том, что все транзакции выполняются с помощью предварительно скомпилированных хранимых процедур, реализованных на Java, и все хранимые процедуры сериализуются, что позволяет VoltDB достичь самого высокого уровня изоляции и устранения блокировок. Использование устройства очень хорошее. В официальных результатах испытаний VoltDB может легко масштабироваться до 39 серверов (300 ядер), 120 разделов, обрабатывающих 1,6 миллиона сложных транзакций в секунду.

# Архитектура [deeplearning4j] фреймворка для глубокого обучения. 
Обучение в Deeplearning4j осуществляется через кластеры. Нейронные сети обучаются параллельно по итерациям, процесс поддерживается архитектурами Hadoop-YARN и Spark. Deeplearning4j осуществляет также интеграцию с ядром архитектуры CUDA для осуществления чистых операций с GPU и распределения операций на графических процессорах.

https://github.com/gridgentoo/deeplearning4j

![Image alt](https://i2.wp.com/mesutpiskin.com/blog/wp-content/uploads/2017/09/dl4j-eco-tr.jpg.jpg)

Deep Learning with DeepLearning4J and Spring Boot - Artur Garcia & Dimas Cabré @ Spring I/O

https://www.youtube.com/watch?v=RlL9MNT-R3k

# TizenRT

[![License](https://img.shields.io/badge/licence-Apache%202.0-brightgreen.svg?style=flat)](LICENSE)
[![Build Status](https://travis-ci.org/Samsung/TizenRT.svg?branch=master)](https://travis-ci.org/Samsung/TizenRT)

TizenRT is lightweight RTOS-based platform to support low-end IoT devices.  
Please find project details at [Wiki](https://github.com/Samsung/TizenRT/wiki) especially **[documentations page](https://github.com/Samsung/TizenRT/wiki/Documentations)**.

## Contents

> [Quick Start](#quick-start)  
> [Supported Board / Emulator](#supported-board--emulator)  
> [Configuration Sets](#configuration-sets)

## Quick Start
### Getting the toolchain

Install the OS specific toolchain. Supported OS Type's are "linux" and "mac".  
Get the build in binaries and libraries, [gcc-arm-none-eabi-6-2017-q1-update-*OS Type*.tar.bz2](https://developer.arm.com/open-source/gnu-toolchain/gnu-rm/downloads/6-2017-q1-update)  
Untar the gcc-arm-none-eabi-6-2017-q1-update-*OS Type*.tar.bz2 and export the path like

```bash
tar xvjf gcc-arm-none-eabi-6-2017-q1-update-[OS Type].tar.bz2
export PATH=<Your Toolchain PATH>:$PATH
```
Be aware that recommanded toolchain is fully working on 64bits machine.

### Getting the sources

```bash
git clone https://github.com/Samsung/TizenRT.git
cd TizenRT
TIZENRT_BASEDIR="$PWD"
```

### How to Build

Configure the build from *$TIZENRT_BASEDIR/os/tools* directory
```bash
cd os/tools
./configure.sh <board>/<configuration_set>
```
The configuration file is named *defconfig*,  
and resides under the relative path \<board\>/\<configuration_set\> rooted at *build/configs*.  
To check the different \<board\>/\<configuration_set\> combinations supported, type below:
```bash
./configure.sh --help
```

After configuring above, configuration can be modified through *make menuconfig* from *$TIZENRT_BASEDIR/os*.
```bash
cd ..
make menuconfig
```

Refer [kconfig-frontend installation](docs/HowtoInstallKconfigFrontend.md) to use *menuconfig*.

Finally, initiate build by make from *$TIZENRT_BASEDIR/os*.
```bash
make
```

Built binaries are in *$TIZENRT_BASEDIR/build/output/bin*.

See [Clean commands](docs/HowtoClean.md) to clean built files.  
See [Trouble Shooting](docs/TroubleShooting.md) to resolve any issue on TizenRT usages.

## Supported Board / Emulator
Here are supported boards and emulator list.  
Refer belows to know board-specific environments, programming method and board information.

ARTIK053 [[details]](build/configs/artik053/README.md)

ARTIK053S [[details]](build/configs/artik053s/README.md)

ARTIK055S [[details]](build/configs/artik055s/README.md)

CY4390X [[details]](build/configs/cy4390x/README.txt)

SIDK_S5JT200 [[details]](build/configs/sidk_s5jt200/README.md)

QEMU [[details]](build/configs/qemu/README.md)

## Configuration Sets

To build a TizenRT application, use the default configuration files named *defconfig* under *build/configs/\<board\>/\<configuration_set\>* folder.  
To customize your application with specific configuration settings, using the menuconfig tool is recommended at *os* folder as shown:
```bash
make menuconfig
```
Please keep in mind that we are actively working on board configurations, and will be posting our updates on the README files under each config.
