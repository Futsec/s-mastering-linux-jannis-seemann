<div align="center">                                                                                                    
    <h3>Linux File System</h3>                                                                                       
    <p>                                                                                                                 
        <em>A Cheatsheet for understanding the Linux file system.</em>                                                                 
    </p>                                                                                                                
</div>                                                                                                                  

<br>                                                                                                                    
<br>

### Table of Contents
- [Essential User & System Binaries](#essential-user--system-binaries)
- [Device & Virtual Filesystems](#device--virtual-filesystems)
- [Boot & Configuration](#boot--configuration)
- [User & Variable Data](#user--variable-data)
- [Mount Points & Runtime](#mount-points--runtime)

<br>
<br>

##### Essential User & System Binaries
|Path|Name|Description|
|:---|:---|:---|
|/bin|Essential User Binaries|Commands needed for single-user mode and basic operation, e.g., `ls`, `cp`, `mv`.|
|/sbin|Essential System Binaries|System administration commands, e.g., `mount`, `shutdown`, typically for root.|
|/usr/bin|Unix System Resources – User Binaries|Most user commands not required for boot, e.g., `python`, `vim`.|
|/usr/sbin|Unix System Resources – System Binaries|System management commands and network daemons not required at boot.|
|/usr/local/bin|Locally Installed User Binaries|Custom or locally compiled binaries, outside the package manager.|
|/usr/local/sbin|Locally Installed System Binaries|Custom system/admin binaries, outside the package manager.|

<br>

##### Device & Virtual Filesystems
|Path|Name|Description|
|:---|:---|:---|
|/dev|Device Files|Interface to hardware and pseudo devices, e.g., `/dev/sda`, `/dev/null`.|
|/proc|Process & Kernel Info|Virtual filesystem exposing process and kernel info, e.g., `/proc/cpuinfo`.|
|/sys|Kernel & Hardware Info|Kernel interface for hardware and system configuration.|

<br>

##### Boot & Configuration
|Path|Name|Description|
|:---|:---|:---|
|/boot|Boot Files|Contains bootloader files and kernel images, e.g., `vmlinuz`, `initrd`.|
|/etc|Configuration Files|System-wide configuration files, e.g., `passwd`, `fstab`.|
|/lib|Essential Shared Libraries|Libraries required by binaries in `/bin` and `/sbin`.|
|/lib64|Essential Shared Libraries (64-bit)|64-bit versions of essential shared libraries.|
|/usr/lib|Unix System Resources – Libraries|Libraries for binaries in `/usr/bin` and `/usr/sbin`.|

<br>

##### User & Variable Data
|Path|Name|Description|
|:---|:---|:---|
|/home|User Home Directories|Home directories for regular users.|
|/root|Root User Home Directory|Home directory for the root user.|
|/var|Variable Data|Variable files such as logs, spool, caches.|
|/tmp|Temporary Files|Temporary files, usually cleared on reboot.|

<br>

##### Mount Points & Runtime
|Path|Name|Description|
|:---|:---|:---|
|/mnt|Temporary Mount Point|Generic mount point for manually mounting filesystems.|
|/media|Removable Media Mounts|Default mount point for removable devices like USB drives and CDs.|
|/run|Runtime Data|Contains runtime data like PID files, sockets, and temporary system info.|

