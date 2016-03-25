----Thanks for xen0n, who are contributing to the working CyanogenMod of MTK hardware.---
# CyanogenMod 13.0

This is a device tree for huawei g750t01 which is based on MT6592 SoC. Powered by ferhung.
# Build

* init
  Sync CyanogenMod source:

        # repo init -u git://github.com/ferhung-mtk/android.git -b cm-13.0        
        # repo sync

* full build
        
        # source build/envsetup.sh

        # brunch cm_g750t01-userdebug

# Limitations

Services requires root:

`system/core/rootdir/init.rc`

  * surfaceflinger depends on sched_setscheduler calls, unable to change process priority from 'system' user (default user 'system')

  * mediaserver depends on /data/nvram folder access, unable to do voice calls from 'media' user (default user 'media')

# In China, we must skip to get 204 from Google server.
  * Change of Android 5.1 source to skip network validation in some environment like China can't connect to http://clients3.google.com/generate_204. 

  To see: 
    [Skip_network_validation](http://github.com/ferhung/Skip_network_validation)
