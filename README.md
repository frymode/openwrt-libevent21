# openwrt-libevent21
libevent 2.1 package for openwrt

To quickly build package for target platform:
* Get corresponding pre-built OpenWrt SDK from [downloads.openwrt.org](http://downloads.openwrt.org/) (e.g. [this](http://downloads.openwrt.org/barrier_breaker/14.07/ar71xx/generic/OpenWrt-Toolchain-ar71xx-for-mips_34kc-gcc-4.8-linaro_uClibc-0.9.33.2.tar.bz2) one for ar71xx platform)
* In SDK root directory make a directory for package inside `package` (e.g. `package/libevent21`).
* Checkout `Makefile` to package directory
* Run `make package/libevent21/install` from SDK root
