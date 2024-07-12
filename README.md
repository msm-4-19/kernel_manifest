# Building

Make a new folder  
```mkdir android-msm-spes-4.19 && cd android-msm-4.19```

Init the repo with  
```repo init -u https://github.com/msm-4-19/kernel_manifest -b android-msm-spes-4.19```

Sync the build system  
```repo sync --force-sync -j$(nproc --all)```

Build the kernel  
```BUILD_BOOT_IMG=true SKIP_MRPROPER=1 ./build_spes.sh```

Images will be located in ```out/android-4.19-stable/dist```  

# ROM Developers

For this kernel to work on ROMs you need to add wlan.ko to your tree, compiling qcacld-3.0 breaks the build system.  

# Module Support
1. Build the kernel
2. Grab the prebuilts from dist/android-4.19-stable/dist
3. Add output prebuilts to device/xiaomi/sm6225-kernel (example here: https://android.googlesource.com/device/google/redbull-kernel/+/refs/tags/android-14.0.0_r45)
4. Add wlan.ko to your tree
