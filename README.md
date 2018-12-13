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
5. `mkdir -p .repo/local_manifests`
6. `wget https://gist.github.com/GrowtopiaJaw/95f5471d11d0b8e428e31c7158a497c4/raw/8503f2e0e84998df30d4cdf810be4787fc7b4882/roomservice.xml -O .repo/local_manifests/roomservice.xml`
7. `repo sync -c -j4 --force-sync --no-tags --no-clone-bundle`
8. `cd build/core && git fetch https://github.com/GrowtopiaJaw/android_build_core && git cherry-pick 928ef1c7d6ba092c1279fe6aa2d5ab2a3683cde8 && cd ../..`
9. `export LC_ALL=C && export JACK_SERVER_VM_ARGUMENTS="-Dfile.encoding=UTF-8 -XX:+TieredCompilation -Xmx4g"`
10. `prebuilts/sdk/tools/jack-admin start-server`
11. `source build/envsetup.sh`
12. `mkdir -p ~/lineage151/out/target/product/riva/obj_arm/ && mkdir -p ~/lineage151/out/target/product/riva/obj/`
13. `cp -r vendor/xiaomi/riva/proprietary/lib ~/lineage151/out/target/product/riva/obj_arm/ && cp -r vendor/xiaomi/riva/proprietary/lib ~/lineage151/out/target/product/riva/obj/`
14. `brunch riva`

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
