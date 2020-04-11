# ums-systemd

systemd files for UMS ([Universal Media Server](https://www.universalmediaserver.com)).

## Usage

Clone this repository or download and unzip its contents.

### Create `ums` user

```bash
cp ums.sysusers.conf /usr/lib/sysusers.d/ums.conf
systemd-sysusers
```

### Create home directory for `ums` user

```bash
cp ums.tmpfiles.conf /usr/lib/tmpfiles.d/ums.conf
systemd-tmpfiles --create
```

### Create service unit

```bash
mkdir -p /usr/lib/systemd/system
cp ums.service /usr/lib/systemd/system/ums.service
```

### Enable service unit and start service

```bash
systemctl enable ums.service
systemctl start ums.service
```

## Configuration

The configuration file used by UMS is `/var/lib/ums/UMS.conf`.

### Example configuration files

You can find example files for `UMS.conf` in the [examples](./examples) directory.

### Media folders

The default media folders is `/var/lib/ums/Media Library`, which contains three subfolders:

* `/var/lib/ums/Media Library/Audio`
* `/var/lib/ums/Media Library/Photo`
* `/var/lib/ums/Media Library/Video`

You can configure UMS to use another media folder:

```bash
folders = /home/{put-your-username-here}/ums/Media Library
```

Or even multiple media folders:

```bash
folders = /var/lib/ums/Media Library, /home/{put-your-username-here}/ums/Media Library
```
