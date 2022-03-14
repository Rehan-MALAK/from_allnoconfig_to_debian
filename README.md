# from_allnoconfig_to_debian

Five kconfig configurations, from allnoconfig to minimal debian/systemd, I use a lot :

 - allnoconfig.config : 64 bits allnoconfig
 - allnoconfig.debug.qemu.config : printk/tty/serial/debug/gdb
 - allnoconfig.debug.qemu.busybox.config : keyboard/initrd/console/elf/proc/sysfs
 - allnoconfig.debug.qemu.busybox.cfs.acpi.ftrace.config : smp/no_hz_common/cfs/cgroups/numa/acpi/cpu_freq/ftrace
 - allnoconfig.debug.qemu.busybox.cfs.acpi.ftrace.module.ext4.systemd.e1000tcp.cgroupsethtoolautomount.filelock.timersshmemtmpfsfull.ext4fssecurity.config : module, ext4, network and tools, lots of systems calls needed for a minimal Debian

Use ''confdiff'' to compare them

```shell
$ confdiff allnoconfig.debug.qemu.config allnoconfig.debug.qemu.busybox.config
76a77,78
> CONFIG_BLK_DEV_INITRD=y
> CONFIG_INITRAMFS_SOURCE=""
78a81
> CONFIG_SYSCTL=y
86a90
> CONFIG_SLUB_DEBUG=y
113a118
> CONFIG_X86_FEATURE_NAMES=y
124a130
> CONFIG_X86_VMX_FEATURE_NAMES=y
260a267,269
> CONFIG_BINFMT_ELF=y
> CONFIG_ELFCORE=y
> CONFIG_BINFMT_SCRIPT=y
294a304,307
> CONFIG_INPUT=y
> CONFIG_INPUT_KEYBOARD=y
> CONFIG_KEYBOARD_ATKBD=y
> CONFIG_SERIO=y
295a309,311
> CONFIG_SERIO_I8042=y
> CONFIG_SERIO_SERPORT=y
> CONFIG_SERIO_LIBPS2=y
296a313,320
> CONFIG_VT=y
> CONFIG_CONSOLE_TRANSLATIONS=y
> CONFIG_VT_CONSOLE=y
> CONFIG_HW_CONSOLE=y
> CONFIG_UNIX98_PTYS=y
> CONFIG_LEGACY_PTYS=y
> CONFIG_LEGACY_PTY_COUNT=256
> CONFIG_LDISC_AUTOLOAD=y
298a323
> CONFIG_SERIAL_8250_DEPRECATED_OPTIONS=y
306a332,337
> CONFIG_VGA_CONSOLE=y
> CONFIG_DUMMY_CONSOLE=y
> CONFIG_DUMMY_CONSOLE_COLUMNS=320
> CONFIG_DUMMY_CONSOLE_ROWS=100
> CONFIG_HID=y
> CONFIG_HID_GENERIC=y
314a346,351
> CONFIG_PROC_FS=y
> CONFIG_PROC_SYSCTL=y
> CONFIG_PROC_PAGE_MONITOR=y
> CONFIG_PROC_PID_ARCH_STATUS=y
> CONFIG_KERNFS=y
> CONFIG_SYSFS=y
372a410
> CONFIG_SCHED_DEBUG=y
```
