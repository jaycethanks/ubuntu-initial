https://blog.csdn.net/weixin_38111667/article/details/115358689



1. 操作前，先全部 unmount 所有 LDM 盘符

2. ```bash
   sudo apt-get install ldmtool
   ```

3. ```bash
   sudo ldmtool create all
   ```

会自动临时创建磁盘，到 `/dev/mapper/` 但是还没有挂载，需要手动在 Files GUI 程序中 [Other Locations] 点击访问，一次之后才会自动挂载。 



相关命令

```bash
sudo ldmtool scan
[
  "21401402-f1e4-11ec-99fd-244bfe959239"
]
 sudo ldmtool show diskgroup 21401402-f1e4-11ec-99fd-244bfe959239
 {
  "name" : "JAYCE123-Dg0",
  "guid" : "21401402-f1e4-11ec-99fd-244bfe959239",
  "volumes" : [
    "Volume1",
    "Volume2",
    "Volume3"
  ],
  "disks" : [
    "Disk1"
  ]
}

```



查看挂载

```bash
lsblk -f
```







```bash
#查看 UUID
lsblk -f
sda                                                                                                               
├─sda1                         vfat     FAT32                 B0ED-016D                                           
├─sda2                                                                                                            
├─sda3                                                                                                            
├─sda4                         ntfs                           98EC02B6EC028EA6                                    
├─sda5                         ntfs           Softwares       F724C147A584A11D                                    
├─ldm_vol_JAYCE123-Dg0_Volume1 ntfs                           98EC02B6EC028EA6                                    
├─ldm_vol_JAYCE123-Dg0_Volume2 ntfs           Softwares       F724C147A584A11D                                    
└─ldm_vol_JAYCE123-Dg0_Volume3 ntfs           desktop         2C7B1BE13FFA7565 
```

