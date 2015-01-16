# openwrt-libevent21
libevent 2.1 package for openwrt

To quickly build package for target platform:
* Get corresponding pre-built OpenWrt SDK from [downloads.openwrt.org](http://downloads.openwrt.org/) (e.g. [this](http://downloads.openwrt.org/barrier_breaker/14.07/ar71xx/generic/OpenWrt-Toolchain-ar71xx-for-mips_34kc-gcc-4.8-linaro_uClibc-0.9.33.2.tar.bz2) one for ar71xx platform)
* [Set up environment](http://wiki.openwrt.org/doc/devel/crosscompile) for cross compilation - need to add toolchain binaries to `PATH` environment variable and define `STAGING_DIR`.
* In SDK root directory make a directory for package inside `package` (e.g. `package/libevent21`).
* Checkout `Makefile` to package directory
* Run `make package/libevent21/install V=s` from SDK root
* When built succesfully packages are placed in `bin/${PLATFORM}/packages` directory:
  - bin/ar71xx/packages/base/libevent2-pthreads_2.1.5-1_ar71xx.ipk
  - bin/ar71xx/packages/base/libevent2-openssl_2.1.5-1_ar71xx.ipk
  - bin/ar71xx/packages/base/libevent2-core_2.1.5-1_ar71xx.ipk
  - bin/ar71xx/packages/base/libevent2-extra_2.1.5-1_ar71xx.ipk
  - bin/ar71xx/packages/base/libevent2_2.1.5-1_ar71xx.ipk
* Generate package index:
  - `staging_dir/host/bin/ipkg-make-index bin/ar71xx/packages/base > bin/ar71xx/packages/base/Packages`
  - `gzip -c bin/ar71xx/packages/base/Packages > bin/ar71xx/packages/base/Packages.gz`
* `opkg` feeds need to be [confgiured](http://wiki.openwrt.org/doc/techref/opkg#configuration) either to use local http server or install packages from filesystem (via `file:///` url schema)
