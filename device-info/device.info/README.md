# 备份方法
cat /proc/cpuinfo  ./cpuinfo.note
cat /proc/meminfo  ./meminfo.note
cat /proc/partition ./partition.note
cat /sys/kernel/debug/gpio ./gpio.note
dmesg > ./startup.note


