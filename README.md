# zfssnapshot
ZFS snapshot management

# 基本方針
+ 毎日定時にsnapshot作成。
+ snapshotの名前はyyyymmdd
+ snapshotは1週間保存
+ 毎月01日のsnapshotのみ1年間保存

crontabで毎日午前3時にsnapshotを撮る場合の記述。
```/etc/crontab
#
# zfssnapshot
#
0       3       *       *       *       root    /root/bin/zfssnapshot
```