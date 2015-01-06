alljoyn-for-openwrt [![Build Status](https://travis-ci.org/probonopd/alljoyn-for-openwrt.svg)](https://travis-ci.org/probonopd/alljoyn-for-openwrt)
===================
Trying to build
https://git.allseenalliance.org/cgit/core/openwrt_feed.git on travis-ci following the instructions on https://allseenalliance.org/developers/develop/building/linux/openwrt.

The ultimate goal is to get https://git.allseenalliance.org/cgit/multimedia/audio.git/ going on OpenWrt, as it seemingly is the basis for the allegedly open source [Qualcomm® AllPlay™](https://www.qualcomm.com/products/allplay/platform) (seemingly based on: [doubleTwist MagicPlay](http://magicplay.com)) multi-room streaming service (and Sonos, AirPlay competitor).

Also see this patch by "DVD" Jon Lech Johansen: http://nanocr.eu/2013/07/02/amplify-your-music-with-magicplay/

Apparently the sound receiving hardware currently contains a "Qualcomm AllPlay Smart Audio Module", but if the whole thing is supposed to be open source then it should be possible to have an OpenWrt-based device to replace the "Smart Audio Module". However, Qualcomm support so far seems to be mainly concerned with the client (app) side, as there is a "Qualcomm AllPlay Click SDK" support forum: https://developer.qualcomm.com/forums/qdevnet-forums/wireless-home-audio-qualcomm-allplay-click-sdk

Currently compilation of the alljoyn Barrier Breaker feed on travis-ci fails because

```
https://git.allseenalliance.org/gerrit/core/openwrt_feed;barrier_breaker
```
appears to be gone.

See the travis-ci logs for more details.

Pull requests are highly welcome.
