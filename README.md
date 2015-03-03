# MultiROM
MultiROM is a one-of-a-kind multi-boot solution. It can boot android ROM while
keeping the one in internal memory intact or boot Ubuntu without formating
the whole device. MultiROM can boot either from internal memory of the device
or from USB flash drive.

###Sources
MultiROM uses git submodules, so you need to clone them as well:

    git clone https://github.com/multirom-titan/multirom.git system/extras/multirom
    cd system/extras/multirom
    git submodule update --init
    cd ../../../

It also needs libbootimg:

    git clone https://github.com/Tasssadar/libbootimg.git system/extras/libbootimg
    
MuiltiRom TWRP:

    rm -rf bootable/recovery
    git clone https://github.com/Tasssadar/Team-Win-Recovery-Project.git bootable/recovery
    
Device Specific MultiRom Config

    git clone https://github.com/multirom-titan/android_device_motorola_titan device/motorola/titan

###Build
To build installation/unistaller ZIP file, use `multirom_zip multirom_uninstaller` target:

    . build/envsetup.sh
    breakfast titan
    make -j5 multirom_zip multirom_uninstaller
To Build MultiRom Recovery, use `recoryimage` target:

    . build/envsetup.sh
    breakfast titan
    make -j5 recoveryimage
