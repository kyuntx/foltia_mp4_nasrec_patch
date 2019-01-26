# foltia_mp4_nasrec_patch
foltia ANIME LOCKER Store MP4 only on NAS Patch

## usage

- create NAS mount point. (e.g. /home/foltia/php/tvnas )
- mount NAS (do not forget edit /etc/fstab)
- store patch files on foltia server. (e.g. /home/foltia/ )
- patching encoding scripts.

```
[foltia@foltia ~]$ cd /home/foltia/
[foltia@foltia ~]$ patch < /home/foltia/foltia_mp4_nasrec.patch
```
- (optional) patching php/css/js files for show NAS disk usage status.
```
[foltia@foltia ~]$ cd /home/foltia/php/
[foltia@foltia php]$ patch < /home/foltia/foltia_mp4_nasrec_shownasrest.patch
```

## note

- change for your nas mount point below

perl/mklocalizeddir.pl
```perl
$recmp4folderpath = "/home/foltia/php/tvnas";
```

php/phpcommon/foltialib.php
```php
        exec ( "df -hP  /home/foltia/php/tvnas", $hdfreearea);
```

- Necessary to re-patch with foltia version upgrade.

