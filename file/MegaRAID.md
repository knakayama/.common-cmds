MegaRAID
========

```bash
# Physical drive status
$ MegaCli -PDList -aALL -NoLog
```

```bash
# Logical drive status
$ MegaCli -LDInfo -Lall -aALL -NoLog
```

```bash
# MegaRAID
$ MegaCli -PDList -aALL -NoLog | grep -E '(^Slot Number|^Firmware state|^Inquiry Data|^Media Error|^Other Error)'
$ MegaCli -PDList -aALL -NoLog | grep -E '(Slot|Firm|Inq)'
```

```bash
# Rebuild progress
# static
$ MegaCli -PDRbld -ShowProg -PhysDrv[252:X] -aALL -NoLog
# real time
$ MegaCli -PDRbld -ProgDsply -PhysDrv[252:X] -aALL -NoLog
```

```bash
$ MegaCli adpalilog a0 -NoLog | grep -i 'fatal'
```

```bash
# Display device number
$ MegaCli -PDGetNum -a0 -NoLog
```

```bash
# Display enclosure info
$ MegaCli -EncInfo -a0 -NoLog
```

```bash
# mfiutil
$ mfiutil show drives
$ mfiutil show volumes
```

```bash
$ MegaCli fwtermlog dsply a0 -NoLog | grep -i 'fatal'
```

```bash
# display RAID Controller settings
$ MegaCli -AdpAllInfo -aALL -NoLog
```

```bash
# display Event Log
$ MegaCli -AdpEventLog -GetEvents -f getevent.txt -a0 -NoLog
```

```bash
# Enable Consistency Check
$ MegaCli -AdpCcSched -ModeConc -SetStartTime 20141025 03 -aALL
```

```bash
# View information about the battery backup unit state
$ MegaCli -AdpBbuCmd -aALL -NoLog
```

```bash
# To see information about the patrol read state and the delay between patrol read
$ MegaCli -AdpPR -Info -aALL
```

```bash
# To find out the current patrol read rate
$ MegaCli -AdpGetProp PatrolReadRate -aALL
```

```bash
# To reduce patrol read resource usage to 2% in order to minimize the performance
$ MegaCli -AdpSetProp PatrolReadRate 2 -aALL
```

```bash
# To disable automatic patrol read
$ MegaCli -AdpPR -Dsbl -aALL
```

```bash
# To start a manual patrol read
$ MegaCli -AdpPR -Start -aALL
```

```bash
# To stop a patrol read
$ MegaCli -AdpPR -Stop -aALL
# more http://artipc10.vub.ac.be/wordpress/2011/09/12/megacli-useful-commands/
```

```bash
# smart
$ MegaCli -PDList -aALL -NoLog |awk '/Device Id/ { print $NF }' | xargs -I% smartctl -a -d megaraid,% /dev/sda
```

```bash
# Set WriteBack
$ MegaCli -LDSetProp WB -LALL -aALL -NoLog
$ MegaCli -LDSetProp -CacheBadBBU -Immediate -Lall -aALL -NoLog
$ MegaCli -LDSetProp -RA -Immediate -Lall -aALL
```

```bash
# 仮想ドライブの数を表示
$ MegaCli -LDGetNum -aALL
```

```bash
# storcli
$ storcli /c0/dall show
$ storcli /c0 show
```
