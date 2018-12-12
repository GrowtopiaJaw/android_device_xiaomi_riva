LineageOS Project (c) 2018

Branch
======

* treble (unmaintained/ unstable/ unbuildable)
* treble-vanilla (stable/ with cherry-pick from treble-vanilla_testing)
* treble-vanilla_testing (unstable)

Build instructions for Xiaomi Redmi 5A (_riva_)
==============================================

1. Make sure all build dependencies are installed and is running Ubuntu 16.04/ 18.04
2. `mkdir lineage151`
3. `cd lineage151`
4. `repo init -u git://github.com/LineageOS/android.git -b lineage-15.1`
5. `repo sync -c -j4 --force-sync --no-tags --no-clone-bundle`
6. `mkdir -p device/xiaomi && mkdir -p kernel/xiaomi && mkdir -p vendor/xiaomi`
7. `git clone https://github.com/GrowtopiaJaw/android_device_xiaomi_riva -b treble-vanilla`
8. `git clone https://github.com/GrowtopiaJaw/riva_kernel_xiaomi_msm8917 -b treble`
9. `git clone https://github.com/GrowtopiaJaw/android_vendor_xiaomi_riva -b treble-vanilla`
10. `export LC_ALL=C && export JACK_SERVER_VM_ARGUMENTS="-Dfile.encoding=UTF-8 -XX:+TieredCompilation -Xmx4g"`
11. `prebuilts/sdk/tools/jack-admin start-server`
12. `source build/envsetup.sh`
13. `lunch lineage_riva-userdebug`
14. `mkdir -p ~/lineage151/out/target/product/riva/obj_arm/ && mkdir -p ~/lineage151/out/target/product/riva/obj/`
15. `cp -r vendor/xiaomi/riva/proprietary/lib ~/lineage151/out/target/product/riva/obj_arm/ && cp -r vendor/xiaomi/riva/proprietary/lib ~/lineage151/out/target/product/riva/obj/`
16. `make -j4`

Device configuration for Xiaomi Redmi 5A  (_riva_)
=====================================================

Basic   | Spec Sheet
-------:|:-------------------------
CPU     | Quad-core 1.4 GHz Cortex-A53
CHIPSET | Qualcomm MSM8917 Snapdragon 425
GPU     | Adreno 308
Memory  | 2 GB
Shipped Android Version | Android 7.1.2 with MIUI 9
Storage | 16 GB
MicroSD | Up to 256 GB (Hybrid in CN variant & dedicated in IN variant)
Battery | 3000 mAh (non-removable)
Dimensions | 140.4 x 70.1 x 8.4 mm
Display | 720 x 1280 pixels, 5.0" IPS
Rear Camera  | 13.0 MP, LED flash
Front Camera | 5.0 MP
Release Date | October 2017

![Xiaomi Redmi 5A](https://cdn2.gsmarena.com/vv/pics/xiaomi/xiaomi-redmi-5a-2.jpg "Xiaomi Redmi 5A")

