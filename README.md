alljoyn-for-openwrt
===================
Trying to build
https://git.allseenalliance.org/cgit/core/openwrt_feed.git on travis-ci.

The ultimate goal is to get https://git.allseenalliance.org/cgit/multimedia/audio.git/ going on OpenWrt, as it seemingly is the basis for the allegedly open source [Qualcomm® AllPlay™](https://www.qualcomm.com/products/allplay/platform) (seemingly based on: [doubleTwist MagicPlay](http://magicplay.com)) multi-room streaming service (and Sonos, AirPlay competitor).

Apparently the sound receiving hardware currently contains a "Qualcomm AllPlay Smart Audio Module", but if the whole thing is supposed to be open source then it should be possible to have an OpenWrt-based device to replace the "Smart Audio Module". However, Qualcomm support so far seems to be mainly concerned with the client (app) side, as there is a "Qualcomm AllPlay Click SDK" support forum: https://developer.qualcomm.com/forums/qdevnet-forums/wireless-home-audio-qualcomm-allplay-click-sdk

Currently compilation of the alljoyn Barrier Breaker feed on travis-ci fails with:

```
cc1: note: someone does not honour COPTS correctly, passed 0 times
libnetlink.c: In function 'rtnl_open_byproto':
libnetlink.c:45:23: error: argument to 'sizeof' in 'memset' call is the same expression as the destination; did you mean to dereference it? [-Werror=sizeof-pointer-memaccess]
  memset(rth, 0, sizeof(rth));
                       ^
cc1: all warnings being treated as errors
make[4]: *** [libnetlink.o] Error 1
make[4]: Leaving directory `/home/travis/build/probonopd/alljoyn-for-openwrt/sdk/OpenWrt-SDK-ar71xx-for-linux-x86_64-gcc-4.8-linaro_uClibc-0.9.33.2/build_dir/target-mips_34kc_uClibc-0.9.33.2/acpid-2.0.10'
make[3]: *** [/home/travis/build/probonopd/alljoyn-for-openwrt/sdk/OpenWrt-SDK-ar71xx-for-linux-x86_64-gcc-4.8-linaro_uClibc-0.9.33.2/build_dir/target-mips_34kc_uClibc-0.9.33.2/acpid-2.0.10/.built] Error 2
make[3]: Leaving directory `/home/travis/build/probonopd/alljoyn-for-openwrt/sdk/OpenWrt-SDK-ar71xx-for-linux-x86_64-gcc-4.8-linaro_uClibc-0.9.33.2/feeds/oldpackages/utils/acpid'
make[2]: *** [package/feeds/oldpackages/acpid/compile] Error 2
make[2]: Leaving directory `/home/travis/build/probonopd/alljoyn-for-openwrt/sdk/OpenWrt-SDK-ar71xx-for-linux-x86_64-gcc-4.8-linaro_uClibc-0.9.33.2'
make[1]: *** [/home/travis/build/probonopd/alljoyn-for-openwrt/sdk/OpenWrt-SDK-ar71xx-for-linux-x86_64-gcc-4.8-linaro_uClibc-0.9.33.2/staging_dir/target-mips_34kc_uClibc-0.9.33.2/stamp/.package_compile] Error 2
make[1]: Leaving directory `/home/travis/build/probonopd/alljoyn-for-openwrt/sdk/OpenWrt-SDK-ar71xx-for-linux-x86_64-gcc-4.8-linaro_uClibc-0.9.33.2'
make: *** [world] Error 2
```
See the travis-ci logs for more details.

Pull requests are highly welcome.
