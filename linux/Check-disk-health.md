# Checking disk health

## SMART
Hard drives continually run self tests (SMART) on themselves to ensure errors are detected and corrected
before data is lost. We can see the latest status of these self tests by using the following command.

```bash
sudo smartctl -a <device>
```

## Badblocks
The `badblocks` utility will help you find the location and amount of bad sectors on your disk. This can
be used to tell if a hard drive is close to failing.

```bash
sudo badblocks -v <device>
```

## FSCK
Sometimes, the self tests aren't sufficient for finding and correcting all errors. To run a more
thorough set of tests and correct errors, we can use the `fsck` command in the following way.

```bash
sudo fsck -y <device>
```
