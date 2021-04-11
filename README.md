# zfssnapshot
ZFS snapshot management

## 基本方針
+ Col. Richie さんのutconv (https://gist.github.com/colrichie/8703117) を利用する。
+ 毎日定時にsnapshot作成。
+ snapshotの名前はyyyymmdd
+ snapshotは1週間保存
+ 毎月01日のsnapshotのみ1年間保存
+ /root/binにutconvとzfssnapshotを置く。

crontabで毎日午前3時にsnapshotを撮る場合の記述。
```/etc/crontab
#
# zfssnapshot
#
0       3       *       *       *       root    /root/bin/zfssnapshot
```