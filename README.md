# linux

Linux: Most useful commands for Full Stack developers

## 1. Remove `PPA`

When you are updating Ubuntu, sometimes appear errors like this:

```bash
E: The repository 'http://ppa.launchpad.net/armagetronad-dev/ppa/ubuntu bionic Release' does not have a Release file.
```

You can solve with this:

```bash
sudo apt-add-repository -r ppa:armagetronad-dev/ppa
sudo apt update
```

## 2. Listening ports and applications using `lsof` command

```bash
❯ sudo lsof -i -P -n | grep LISTEN
[sudo] password for herles:
systemd       1            root   57u  IPv6  27176      0t0  TCP *:6600 (LISTEN)
systemd-r   741 systemd-resolve   13u  IPv4  25968      0t0  TCP 127.0.0.53:53 (LISTEN)
cupsd       935            root    6u  IPv6  26486      0t0  TCP [::1]:631 (LISTEN)
cupsd       935            root    7u  IPv4  26487      0t0  TCP 127.0.0.1:631 (LISTEN)
mpd         971             mpd    4u  IPv6  27176      0t0  TCP *:6600 (LISTEN)
anydesk     974            root   32u  IPv4  36321      0t0  TCP *:7071 (LISTEN)
container  1020            root    7u  IPv4  35414      0t0  TCP 127.0.0.1:36085 (LISTEN)
postgres   1058        postgres    3u  IPv4  32197      0t0  TCP *:5432 (LISTEN)
postgres   1058        postgres    4u  IPv6  32198      0t0  TCP *:5432 (LISTEN)
docker-pr  1647            root    4u  IPv6  38758      0t0  TCP *:9069 (LISTEN)
docker-pr  1648            root    4u  IPv6  32540      0t0  TCP *:6069 (LISTEN)
docker-pr  1677            root    4u  IPv6  33571      0t0  TCP *:9068 (LISTEN)
docker-pr  1678            root    4u  IPv6  37604      0t0  TCP *:6068 (LISTEN)
docker-pr  1697            root    4u  IPv4  35808      0t0  TCP 127.0.0.1:3306 (LISTEN)
docker-pr  1710            root    4u  IPv6  39282      0t0  TCP *:443 (LISTEN)
docker-pr  1725            root    4u  IPv6  32583      0t0  TCP *:80 (LISTEN)
java       3606          herles   50u  IPv6  48389      0t0  TCP 127.0.0.1:6942 (LISTEN)
java       3606          herles  319u  IPv6  44815      0t0  TCP 127.0.0.1:39871 (LISTEN)
java       3606          herles  567u  IPv6  51409      0t0  TCP 127.0.0.1:63342 (LISTEN)
java       3606          herles  664u  IPv6  56459      0t0  TCP 127.0.0.1:42507 (LISTEN)
java      13283          herles   64u  IPv6 172245      0t0  TCP 127.0.0.1:60199 (LISTEN)
java      13283          herles   66u  IPv6 172246      0t0  TCP 127.0.0.1:37903 (LISTEN)
java      26840          herles  104u  IPv6 314069      0t0  TCP 127.0.0.1:39421 (LISTEN)

⬢  ~
❯
```

## 3. Using `netstat` to list open ports

```bash
❯ sudo netstat -tulpn | grep LISTEN
tcp        0      0 127.0.0.1:36085         0.0.0.0:*               LISTEN      1020/containerd
tcp        0      0 127.0.0.53:53           0.0.0.0:*               LISTEN      741/systemd-resolve
tcp        0      0 127.0.0.1:631           0.0.0.0:*               LISTEN      935/cupsd
tcp        0      0 0.0.0.0:5432            0.0.0.0:*               LISTEN      1058/postgres
tcp        0      0 0.0.0.0:7071            0.0.0.0:*               LISTEN      974/anydesk
tcp        0      0 127.0.0.1:3306          0.0.0.0:*               LISTEN      1697/docker-proxy
tcp6       0      0 :::9068                 :::*                    LISTEN      1677/docker-proxy
tcp6       0      0 :::9069                 :::*                    LISTEN      1647/docker-proxy
tcp6       0      0 127.0.0.1:63342         :::*                    LISTEN      3606/java
tcp6       0      0 127.0.0.1:37903         :::*                    LISTEN      13283/java
tcp6       0      0 :::80                   :::*                    LISTEN      1725/docker-proxy
tcp6       0      0 :::6068                 :::*                    LISTEN      1678/docker-proxy
tcp6       0      0 :::6069                 :::*                    LISTEN      1648/docker-proxy
tcp6       0      0 ::1:631                 :::*                    LISTEN      935/cupsd
tcp6       0      0 :::5432                 :::*                    LISTEN      1058/postgres
tcp6       0      0 :::443                  :::*                    LISTEN      1710/docker-proxy
tcp6       0      0 127.0.0.1:39421         :::*                    LISTEN      26840/java
tcp6       0      0 127.0.0.1:6942          :::*                    LISTEN      3606/java
tcp6       0      0 127.0.0.1:39871         :::*                    LISTEN      3606/java
tcp6       0      0 127.0.0.1:60199         :::*                    LISTEN      13283/java
tcp6       0      0 :::6600                 :::*                    LISTEN      1/init
tcp6       0      0 127.0.0.1:42507         :::*                    LISTEN      3606/java

⬢  ~
❯
```
