# from_allnoconfig_to_debian

Five kconfig configurations, from allnoconfig to minimal debian/systemd, I use a lot :

 - allnoconfig.config : 64 bits allnoconfig
 - allnoconfig.debug.qemu.config : printk/tty/serial/debug/gdb
 - allnoconfig.debug.qemu.busybox.config : keyboard/initrd/console/elf/proc/sysfs
 - allnoconfig.debug.qemu.busybox.cfs.acpi.ftrace.config : smp/no_hz_common/cfs/cgroups/numa/acpi/cpu_freq/ftrace
 - allnoconfig.debug.qemu.busybox.cfs.acpi.ftrace.module.ext4.systemd.e1000tcp.cgroupsethtoolautomount.filelock.timersshmemtmpfsfull.ext4fssecurity.config : module, ext4, network and tools, lots of systems calls needed for a minimal Debian
