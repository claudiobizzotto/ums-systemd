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

### Create default profile in home directory

```bash
cp /opt/ums/UMS.conf /var/lib/ums/UMS.conf
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
