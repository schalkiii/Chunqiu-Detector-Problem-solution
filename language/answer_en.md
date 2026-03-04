# Chunqiu Detector Solutions (Following the Latest Version) English Version

>Organized by: mingzun09(SuXiaoMing) | For reference only, specific results may vary by device/environment
Document Link: Github

## SU binary detected

>SU binary file detected (ROOT detected)

## Miscellaneous Check（a)

>dex2at detected (Usually an LSP issue, replace the LSP module)

## Mount loophole

>Mount loop detected
Older versions of the KSU manager might have this issue, certain modules can also cause it
Can use SUSFS to hide or uninstall the module causing the environment problem

## Magic Mount

>Magic Mount detected
Please try to exclude certain modules that modify the system
Use certain modules to hide this issue (e.g., the exclusion strategy in zygisk next)

## SU list

>Detected a ROOT permission exclusion list like ksu's
This detection item is unstable and appears occasionally (usually more common with KSU LKM mode)

## Abormal Environment

>KSU/APatch/Magisk detected
Side-channel detection, update your manager and re-patch

## KnelsU Loop Fevice

>KSU detected
Update your manager and re-patch

## Suspicious Surroundings

>APatch detected
Update APatch and load the KPM hiding module to resolve (e.g., Nohello.kpm)

## Device is emulator

>Currently on an emulator device

## avb verification avb=2.0

>avb version异常
Certain modules can cause this issue, such as device model modification modules

## Found LSPHook Framework

>LSPhook Framework detected
Caused by some Xposed modules, can also uninstall and replace the LSP module

## Scene Detected

>Scene software, you can try to hide it
Ignore this detection item, or uninstall scene

## Zygisk Detected

>Zygisk detected, usually caused by magisk's built-in zygisk (resolve by turning it off) or other reasons
Update the zygisk next module

## Tempered Kernel

>Kernel information verification (kernel character version, kernel build time)
Try using SUSFS to hide or restore the unmodified boot.img

## [hook]Resetprop Modified

>resetprop has been modified
Try to investigate modules that modify the system

## Suspicious Surroundings (a)

>Path /data/local/tmp
The tmp folder is set to root user and all groups, change it to shell

## Suspicious Surroundings (b)

>Path /data/local/tmp
tmp's inode value is higher than 10000 (has been deleted)
Format the system or use SUSFS to the path's inode value to be 1000

## Suspicious Surroundings (b)

>/data/local/tmp
The permissions of the tmp folder have been modified (default 771)

## Futile Hide

>The time of the /data/local/tmp folder has been modified
Format the system or delete the tmp folder, reboot to revert to the state in abc above, then use Kstat in sukisu (requires kernel integrated with susfs) to add the /data/local/tmp directory, only modifying the ino value, e.g., 7365 (tmp directory permissions remain 771, owner is shell).

## Miscellaneous Check(2)

>Detects device tampering
Caused by device model modification modules?

## Miscellaneous Check(3)

>Device modification detection

## Inconsistent mount /debug_ramdisk

>umount /debug_ramdisk

## Netlink Socket Anomaly

>Currently unknown

## /data/local/tmp Denied

>Directory /data/local/tmp access denied, folder permission issue? Folder does not exist?

## Spoofed Kernel

>Invalid use of susfs to kernel
Select post-fs-data in the kernel startup phase

## Futile Hide (04)

>Principle - Mount namespace?
Detects mount
Try replacing the "meta module" to resolve

## Mount Gap

>Detects mount异常
Try replacing the "meta module" to resolve

## 2222

>Detects mount异常

## Third-party Kernel

>Kernel information matches preset information list
Resolve by kernel information

## Third-party Rom / Self-compiled Kernel

>Kernel version suffix contains -Dirty
Resolve by伪装 kernel information

## ROM Detected

>Third-party ROM detected
Some third-party ROM characteristics match
Can try to伪装 manually

## SUspicious Terminal Environment

>Detects Pty

## Environment Fake

>Fake environment detected
Characteristic of some hiding methods

## ROOT process

>Detects Zygote environment?
Read via audit log vulnerability (avc)
Can use SUSFS functionality or the ZN-AuditPatch module
Android security update 25/09/01 has fixed this (inaccurate but the result is like this)

## Abnormal Process

>Detects hidden process groups

## MT Manager (MT2 folder) / Abnormal files

>MT Manager by default creates an "mt2" folder feature in the root directory
Can be resolved by customizing the MT2 path in MT Manager settings

## Risk apps

>Detects risky applications
Can try using HMA-OSS to hide risky applications

## Thanox Service Detected

>2333333

## TEE damaged

>Try using the Tricky Store module to resolve

>Key attestation incomplete or chain inconsistent

>Update Tricky Store module?

## AosP Key

>Replace keybox.xml

## Boot Hash Mismatch

>boot image hash mismatch
Usually, after BL is unlocked, the hash becomes 0000. Use the Tricky Store module to resolve.

## Bootloader Unlocked

>BL已解锁, use the Tricky Store module to hide

## Boot Status Abnormal

>BL已解锁, use the Tricky Store module to hide

## Key Tempered (128)

>Tricky Store uses "key chain generation mode" (forced mode) by default on OnePlus Qualcomm devices
Manually add a ? symbol to the package name in the module's target.txt file

## Key Tempered (q)

>Unknown

## Key Tempered (b)

>Unknown

## Trusted Certificate Tempered

>Unknown

## TrickyStore Found

>Wait for module updates

## Something wrong

>Unknown

## Miscellaneous Check(4/5/6/7)

>Some detections related to emulators/virtual machines.
This detection item hasn't been added/updated yet.

## Miscellaneous Check (Inconsistent mount)

>Usually triggered by using the Magic mount meta module?

## Magic-Bind Structure

>Usually triggered by using the Magic mount meta module?
Magic mount significantly increases the number of mounts, making detection possible xD

## Abnormal Files

>· Detection paths: /dev and /data/local/tmp
  1. Rename/delete related directory files
  2. Investigate and remove the following high-risk paths:
     ```
     /data/local/stryker
     /data/system/AppRetention
     /data/local/tmp/luckys
     /data/local/tmp/input_devices
     /data/local/tmp/HyperCeiler
     /data/local/tmp/simpleHook
     /data/local/tmp/DisabledAllGoogleServices
     /data/local/MIO
     /data/DNA
     /data/local/tmp/cleaner_starter
     /data/local/tmp/byyang
     /data/local/tmp/mount_mask
     /data/local/tmp/mount_mark
     /data/local/tmp/scriptTMP
     /data/local/luckys
     /data/local/tmp/horae_control.log
     /data/gpu_freq_table.conf
     /storage/emulated/0/Download/advanced
     /storage/emulated/0/Documents/advanced
     /data/system/NoActive
     /data/system/Freezer
     /storage/emulated/0/Android/naki
     /data/swap_config.conf
     /data/local/tmp/resetprop
     ```

## Mount Loophole

>Magic Mount takes effect for modules modifying the system
But the mounting requires other modules to hide (you can choose susfs/zygisk next)
Use zygisk next's exclusion strategy > Unmount only
And configure the exclusion list / enable default module unmounting
Hide it

## Magic Mount

>Use zygisk next's exclusion strategy > Unmount only
And configure the exclusion list / enable default module unmounting
Hide it