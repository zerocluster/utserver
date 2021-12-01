# Resources

Ports:

-   8080 - web UI port, TCP;
-   6881 - communication port, TCP, UDP;

Volumes:

-   /var/local/utserver/data - data folder;
-   /var/local/utserver/autoload - autoload torrent files;
-   /var/local/utserver/settings - settings;

# How to create .torrent

Copy data to `/var/local/utserver/data`.

Create .torrent file:

```sh
cd /var/local/utserver/data && mktorrent -a http://localhost/ <RELATIVE_PATH_TO_DATA_FILE_OR_DIR>
```

After torrent created, move it to `/var/local/utserver/autoload`.

# Install

```sh
dnf -y install mktorrent

mkdir /var/local/utserver

cd /var/local/utserver

curl -fsSLO https://bitbucket.org/softvisio/utserver/raw/master/utserver.sh && chmod +x utserver.sh

/var/local/utserver/utserver.sh

echo Connect to webui: http://admin@$(hostname):6880/gui/
```
