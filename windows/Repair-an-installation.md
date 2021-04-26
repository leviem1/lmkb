# Repairing a Windows Installation
Sometimes, sectors go bad on a hard drive which can cause corruption of data
files. If the data files are important Windows files, then your installation
may not boot or have other issues.

## Repair using `chkdsk`
One way to repair your installation is to scan for bad sectors and data, and
repair it using `chkdsk` as follows as an administrator:
```batch
chkdsk C: /r /x
```

## Repair using `sfc`
Another way to repair the installation is to try to recreate any corrupt
files using `sfc` as follows as an administrator:
```batch
sfc /SCANNOW
```

## Repair using `DISM`
If `sfc` cannot repair the installation, you can try to repair them from
downloading them online using `DISM` as follows as an administrator:
```batch
DISM.exe /Online /Cleanup-image /Restorehealth
```
