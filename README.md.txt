medoudaniel
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

172.28.128.7 IP Address

C:\Program Files\PostgreSQL\14

C:\Program Files\PostgreSQL\14\data

mot de passe: password

https://www.youtube.com/watch?v=H_TFWZo-I5w

DanielMagloire
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

Container ID 172.28.128.8

ContaineriZation Commands with docker

vagrant@docker:~$ 
```
docker ps
```
```
docker images
```

```
docker pull postgres
```
```
docker images
```
```
docker pull dpage/pgadmin4
```
```
docker images
```
```
docker network ls
```
```
docker network create postgres-network
```
```
docker network ls
```

```
docker rm -f $(docker ps -aq)
```

## start postgres

```
docker run -d \
--name postgresdb \
-p 5432:5432 \
--network postgres-network \
-e POSTGRES_PASSWORD=password \
-e POSTGRES_USER=postgres \
-e POSTGRES_DB=bmconso \
postgres
```
```
docker logs d3176b30d21243a446db38bd42e984e6e2e7b3ece63b42a8bef1bb4a84fe5211
```

## start pgadmin4

```
docker run -d \
-p 5050:80 \
--name pgadmin4 \
--network postgres-network \
-e 'PGADMIN_DEFAULT_EMAIL=grand_dan2@yahoo.fr' \
-e 'PGADMIN_DEFAULT_PASSWORD=SuperSecret' \
-e 'PGADMIN_DEFAULT_ENHANCED_COOKIE_PROTECTION=True' \
-e 'PGADMIN_CONFIG_CONSOLE_LOG_LEVEL=10' \
dpage/pgadmin4
```

docker logs 816fc13919a52852121eb538614c530729e16c8beb281c3ac72314c463e0d5f8

Pour configurer **pgAdmin** conteneurisé, on procède comme suite:
 **Clic droit sur Server** + **Registry** + **Server** + **name: mypgbmconso/PostgreSQL4** + **connection** + **Host: ip container docker postgres: 172.18.0.2**

```
docker ps
```
```
docker inspect [Container ID postgres]
```
```
vagrant@docker:~$ docker inspect d3176b30d212
[
    {
        "Id": "d3176b30d21243a446db38bd42e984e6e2e7b3ece63b42a8bef1bb4a84fe5211",
        "Created": "2022-09-24T11:32:32.55478242Z",
        "Path": "docker-entrypoint.sh",
        "Args": [
            "postgres"
        ],
        "State": {
            "Status": "running",
            "Running": true,
            "Paused": false,
            "Restarting": false,
            "OOMKilled": false,
            "Dead": false,
            "Pid": 11846,
            "ExitCode": 0,
            "Error": "",
            "StartedAt": "2022-09-24T11:32:32.9486597Z",
            "FinishedAt": "0001-01-01T00:00:00Z"
        },
        "Image": "sha256:75993dd36176c7d4be8c1e6d88a115f1fb35a85451088699dbdc80659ad688ed",
        "ResolvConfPath": "/var/lib/docker/containers/d3176b30d21243a446db38bd42e984e6e2e7b3ece63b42a8bef1bb4a84fe5211/resolv.conf",
        "HostnamePath": "/var/lib/docker/containers/d3176b30d21243a446db38bd42e984e6e2e7b3ece63b42a8bef1bb4a84fe5211/hostname",
        "HostsPath": "/var/lib/docker/containers/d3176b30d21243a446db38bd42e984e6e2e7b3ece63b42a8bef1bb4a84fe5211/hosts",
        "LogPath": "/var/lib/docker/containers/d3176b30d21243a446db38bd42e984e6e2e7b3ece63b42a8bef1bb4a84fe5211/d3176b30d21243a446db38bd42e984e6e2e7b3ece63b42a8bef1bb4a84fe5211-json.log",
        "Name": "/postgresdb",
        "RestartCount": 0,
        "Driver": "overlay2",
        "Platform": "linux",
        "MountLabel": "",
        "ProcessLabel": "",
        "AppArmorProfile": "docker-default",
        "ExecIDs": null,
        "HostConfig": {
            "Binds": null,
            "ContainerIDFile": "",
            "LogConfig": {
                "Type": "json-file",
                "Config": {}
            },
            "NetworkMode": "postgres-network",
            "PortBindings": {
                "5432/tcp": [
                    {
                        "HostIp": "",
                        "HostPort": "5432"
                    }
                ]
            },
            "RestartPolicy": {
                "Name": "no",
                "MaximumRetryCount": 0
            },
            "AutoRemove": false,
            "VolumeDriver": "",
            "VolumesFrom": null,
            "CapAdd": null,
            "CapDrop": null,
            "CgroupnsMode": "host",
            "Dns": [],
            "DnsOptions": [],
            "DnsSearch": [],
            "ExtraHosts": null,
            "GroupAdd": null,
            "IpcMode": "private",
            "Cgroup": "",
            "Links": null,
            "OomScoreAdj": 0,
            "PidMode": "",
            "Privileged": false,
            "PublishAllPorts": false,
            "ReadonlyRootfs": false,
            "SecurityOpt": null,
            "UTSMode": "",
            "UsernsMode": "",
            "ShmSize": 67108864,
            "Runtime": "runc",
            "ConsoleSize": [
                0,
                0
            ],
            "Isolation": "",
            "CpuShares": 0,
            "Memory": 0,
            "NanoCpus": 0,
            "CgroupParent": "",
            "BlkioWeight": 0,
            "BlkioWeightDevice": [],
            "BlkioDeviceReadBps": null,
            "BlkioDeviceWriteBps": null,
            "BlkioDeviceReadIOps": null,
            "BlkioDeviceWriteIOps": null,
            "CpuPeriod": 0,
            "CpuQuota": 0,
            "CpuRealtimePeriod": 0,
            "CpuRealtimeRuntime": 0,
            "CpusetCpus": "",
            "CpusetMems": "",
            "Devices": [],
            "DeviceCgroupRules": null,
            "DeviceRequests": null,
            "KernelMemory": 0,
            "KernelMemoryTCP": 0,
            "MemoryReservation": 0,
            "MemorySwap": 0,
            "MemorySwappiness": null,
            "OomKillDisable": false,
            "PidsLimit": null,
            "Ulimits": null,
            "CpuCount": 0,
            "CpuPercent": 0,
            "IOMaximumIOps": 0,
            "IOMaximumBandwidth": 0,
            "MaskedPaths": [
                "/proc/asound",
                "/proc/acpi",
                "/proc/kcore",
                "/proc/keys",
                "/proc/latency_stats",
                "/proc/timer_list",
                "/proc/timer_stats",
                "/proc/sched_debug",
                "/proc/scsi",
                "/sys/firmware"
            ],
            "ReadonlyPaths": [
                "/proc/bus",
                "/proc/fs",
                "/proc/irq",
                "/proc/sys",
                "/proc/sysrq-trigger"
            ]
        },
        "GraphDriver": {
            "Data": {
                "LowerDir": "/var/lib/docker/overlay2/7d3ad7d21adee162f778564bbc32703b391055624bf66cb28879a354e0c4f68c-init/diff:/var/lib/docker/overlay2/47ccbe4e065dc3bc02809c86309909c2a4f80117791f4698e453055c2c1efeee/diff:/var/lib/docker/overlay2/6b3a149d98d6abc02736772230fd8b196631af6b52e358028c87561d3b479bf8/diff:/var/lib/docker/overlay2/cd5642c707a69a3caf7eaf48d72fd274d802f11889279403ca4343b77449dd29/diff:/var/lib/docker/overlay2/0f4c37b5b56c068fb0e606e885dd81ae905f0a2a03752d5fd0eb3a1604f5d72b/diff:/var/lib/docker/overlay2/6a197239888ea19c2d3e054c09787ba5da3e439b0e78eb9a2316c70f9a5ceff9/diff:/var/lib/docker/overlay2/74cad9d82c793eeffa4b1bcc66a2ab25b6cc710ac2e7c2ef0ed71c4a6b65da55/diff:/var/lib/docker/overlay2/3519ddde5449419716380f4873db61daee077f7916dd3b165ce1f646e86bb9fc/diff:/var/lib/docker/overlay2/f08e3e1b46e343c022f053ee4dbf69dc6983a7f394c11d8549e6fca201a9b31f/diff:/var/lib/docker/overlay2/e610ebfac406be49aa486217d11d4cfe6e12d48dd3dd13d72d412c0f2fb6cde8/diff:/var/lib/docker/overlay2/d561b2ec25a631f7a52e995606074a6b709fef07d6a61023ad361e9bd4ca5c9e/diff:/var/lib/docker/overlay2/58653deb2eb9532b87a458edfd968da0ab3d9468a17fd11006acf9dde19dcca5/diff:/var/lib/docker/overlay2/1d6bebd155435142aa325933ff544d45d7e99dd35101a7cdd9db68dddbfa79cf/diff:/var/lib/docker/overlay2/e5ccba786767ea40aca576d1f4b1addeb6cd70a0a69c7dc437c141a9b060836c/diff",
                "MergedDir": "/var/lib/docker/overlay2/7d3ad7d21adee162f778564bbc32703b391055624bf66cb28879a354e0c4f68c/merged",
                "UpperDir": "/var/lib/docker/overlay2/7d3ad7d21adee162f778564bbc32703b391055624bf66cb28879a354e0c4f68c/diff",
                "WorkDir": "/var/lib/docker/overlay2/7d3ad7d21adee162f778564bbc32703b391055624bf66cb28879a354e0c4f68c/work"
            },
            "Name": "overlay2"
        },
        "Mounts": [
            {
                "Type": "volume",
                "Name": "3f90ba487408c570b17259e398945f01444da6f6ea634f5aff534e963a1b2c2e",
                "Source": "/var/lib/docker/volumes/3f90ba487408c570b17259e398945f01444da6f6ea634f5aff534e963a1b2c2e/_data",
                "Destination": "/var/lib/postgresql/data",
                "Driver": "local",
                "Mode": "",
                "RW": true,
                "Propagation": ""
            }
        ],
        "Config": {
            "Hostname": "d3176b30d212",
            "Domainname": "",
            "User": "",
            "AttachStdin": false,
            "AttachStdout": false,
            "AttachStderr": false,
            "ExposedPorts": {
                "5432/tcp": {}
            },
            "Tty": false,
            "OpenStdin": false,
            "StdinOnce": false,
            "Env": [
                "POSTGRES_PASSWORD=password",
                "POSTGRES_USER=postgres",
                "POSTGRES_DB=bmconso",
                "PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/lib/postgresql/14/bin",
                "GOSU_VERSION=1.14",
                "LANG=en_US.utf8",
                "PG_MAJOR=14",
                "PG_VERSION=14.5-1.pgdg110+1",
                "PGDATA=/var/lib/postgresql/data"
            ],
            "Cmd": [
                "postgres"
            ],
            "Image": "postgres",
            "Volumes": {
                "/var/lib/postgresql/data": {}
            },
            "WorkingDir": "",
            "Entrypoint": [
                "docker-entrypoint.sh"
            ],
            "OnBuild": null,
            "Labels": {},
            "StopSignal": "SIGINT"
        },
        "NetworkSettings": {
            "Bridge": "",
            "SandboxID": "27ae9b0dd953351644fe87389aa5bd336f460b0d524aa9e9d68f4719bcd3d074",
            "HairpinMode": false,
            "LinkLocalIPv6Address": "",
            "LinkLocalIPv6PrefixLen": 0,
            "Ports": {
                "5432/tcp": [
                    {
                        "HostIp": "0.0.0.0",
                        "HostPort": "5432"
                    },
                    {
                        "HostIp": "::",
                        "HostPort": "5432"
                    }
                ]
            },
            "SandboxKey": "/var/run/docker/netns/27ae9b0dd953",
            "SecondaryIPAddresses": null,
            "SecondaryIPv6Addresses": null,
            "EndpointID": "",
            "Gateway": "",
            "GlobalIPv6Address": "",
            "GlobalIPv6PrefixLen": 0,
            "IPAddress": "",
            "IPPrefixLen": 0,
            "IPv6Gateway": "",
            "MacAddress": "",
            "Networks": {
                "postgres-network": {
                    "IPAMConfig": null,
                    "Links": null,
                    "Aliases": [
                        "d3176b30d212"
                    ],
                    "NetworkID": "ce46f5802fc33b04b9f64359112acce0b18160ed39d7887727fa1c60d5d26197",
                    "EndpointID": "107d9c68027d9578fe69b44d0f2a244bf42e67815057b283b329acfa16dfda66",
                    "Gateway": "172.18.0.1",
                    "IPAddress": "172.18.0.2",
                    "IPPrefixLen": 16,
                    "IPv6Gateway": "",
                    "GlobalIPv6Address": "",
                    "GlobalIPv6PrefixLen": 0,
                    "MacAddress": "02:42:ac:12:00:02",
                    "DriverOpts": null
                }
            }
        }
    }
]
vagrant@docker:~$
```
puis,

Username: postgres

password: password

Et je coche **password save** + **save**

# Connect Node Server With PostGreSQL Container


