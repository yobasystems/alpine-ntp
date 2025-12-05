# NTP - Chrony Container image running on Alpine Linux

[![Docker Automated build](https://img.shields.io/docker/automated/yobasystems/alpine-ntp.svg?style=for-the-badge&logo=docker)](https://hub.docker.com/r/yobasystems/alpine-ntp/)
[![Docker Pulls](https://img.shields.io/docker/pulls/yobasystems/alpine-ntp.svg?style=for-the-badge&logo=docker)](https://hub.docker.com/r/yobasystems/alpine-ntp/)
[![Docker Stars](https://img.shields.io/docker/stars/yobasystems/alpine-ntp.svg?style=for-the-badge&logo=docker)](https://hub.docker.com/r/yobasystems/alpine-ntp/)

[![Alpine Version](https://img.shields.io/badge/Alpine%20version-v3.23.0-green.svg?style=for-the-badge&logo=alpine-linux)](https://alpinelinux.org/)
[![Chrony Version](https://img.shields.io/badge/Chrony%20version-v4.8.0-green.svg?style=for-the-badge&logo=chrony)](https://chrony.tuxfamily.org/)

This Container image [(yobasystems/alpine-ntp)](https://hub.docker.com/r/yobasystems/alpine-ntp/) is based on the minimal [Alpine Linux](https://alpinelinux.org/) with [Chrony](https://chrony.tuxfamily.org/) (NTP) Network Time Protocol.

### Alpine Version 3.23.0 (Released 2025-12-03)

##### Chrony Version 4.8.0

---

## 🏔️ What is Alpine Linux?

Alpine Linux is a Linux distribution built around musl libc and BusyBox. The image is only 5 MB in size and has access to a package repository that is much more complete than other BusyBox based images. This makes Alpine Linux a great image base for utilities and even production applications. Read more about Alpine Linux here and you can see how their mantra fits in right at home with Container images.

## 🕰️ What is Chrony?

chrony is a versatile implementation of the Network Time Protocol (NTP). It can synchronise the system clock with NTP servers, reference clocks (e.g. GPS receiver), and manual input using wristwatch and keyboard. It can also operate as an NTPv4 (RFC 5905) server and peer to provide a time service to other computers in the network.

It is designed to perform well in a wide range of conditions, including intermittent network connections, heavily congested networks, changing temperatures (ordinary computer clocks are sensitive to temperature), and systems that do not run continuosly, or run on a virtual machine.

Typical accuracy between two machines synchronised over the Internet is within a few milliseconds; on a LAN, accuracy is typically in tens of microseconds. With hardware timestamping, or a hardware reference clock, sub-microsecond accuracy may be possible.

Two programs are included in chrony, chronyd is a daemon that can be started at boot time and chronyc is a command-line interface program which can be used to monitor chronyd's performance and to change various operating parameters whilst it is running.

## ✨ Features

- Minimal size only, minimal layers
- Memory usage is minimal on a simple install.
- Network Time Protocol (NTP) server and client

## 🏗️ Architectures

- `:amd64`, `:x86_64` - 64 bit Intel/AMD (x86_64/amd64)
- `:arm64v8`, `:aarch64` - 64 bit ARM (ARMv8/aarch64)
- `:arm32v7`, `:armhf` - 32 bit ARM (ARMv7/armhf)

#### 📝 PLEASE CHECK TAGS BELOW FOR SUPPORTED ARCHITECTURES, THE ABOVE IS A LIST OF EXPLANATION

## 🏷️ Tags

- `:latest` latest branch based (Automatic Architecture Selection)
- `:master` master branch usually inline with latest
- `:amd64`, `:x86_64` amd64 based on latest tag but amd64 architecture
- `:aarch64`, `:arm64v8` Armv8 based on latest tag but arm64 architecture
- `:armhf`, `:arm32v7` Armv7 based on latest tag but arm32 architecture
- `:version` Version tags e.g `:4`, `4.8.0`

## 📏 Layers & Sizes

![Version](https://img.shields.io/badge/version-amd64-blue.svg?style=for-the-badge)
![Docker Image Size (tag)](https://img.shields.io/docker/image-size/yobasystems/alpine-ntp/amd64.svg?style=for-the-badge)

![Version](https://img.shields.io/badge/version-aarch64-blue.svg?style=for-the-badge)
![Docker Image Size (tag)](https://img.shields.io/docker/image-size/yobasystems/alpine-ntp/aarch64.svg?style=for-the-badge)

![Version](https://img.shields.io/badge/version-armhf-blue.svg?style=for-the-badge)
![Docker Image Size (tag)](https://img.shields.io/docker/image-size/yobasystems/alpine-ntp/armhf.svg?style=for-the-badge)

## 🚀 How to use this image

## Volume structure

### Environment Variables:

### Main Chrony parameters:

- `NTP_SERVERS` : time.cloudflare.com
- `NTP_PORT` : 123
- `NTP_MAXSKEW` : 1000.0
- `NTP_MAXDISTANCE` : 8
- `NTP_MAXPOLL` : 10
- `NTP_MINPOLL` : 6
- `NTP_MAXDELAY` : 0.5
- `NTP_MAXJITTER` : 0.1
- `NTP_MAXWANDER` : 0.001
- `NTP_MAXTRACKING` : 0.5
- `NTP_MAXSOURCES` : 3
- `NTP_MAXAGE` : 0.5
- `NTP_MAXCLOCK` : 0.5
- `NTP_MAXDRIFT` : 0.5
- `NTP_MAXSTEER` : 0.5
- `NTP_MAXSYMMETRY` : 0.5
- `NTP_MAXPENDING` : 0.5
- `NTP_MAXHOLDOFF` : 0.5
- `NTP_MAXJITTER` : 0.5

## Creating an instance

```bash
docker run -d --name=ntp --restart=always --publish=123:123/udp yobasystems/alpine-ntp
```

It will create a new container, and set the time to the default which is time.cloudflare.com.

## Docker Compose example:

```yaml
version: "3.9"

services:
  ntp:
    build: .
    image: yobasystems/alpine-ntp:latest
    container_name: ntp
    restart: always
    ports:
      - 123:123/udp
    environment:
      - NTP_SERVERS=time.cloudflare.com
      - LOG_LEVEL=0
```

## 🔍 Image contents & Vulnerability analysis

| PACKAGE NAME | PACKAGE VERSION | VULNERABILITIES |
| ------------ | --------------- | --------------- |

## 📚 Source Repositories

- [Github - yobasystems/alpine-ntp](https://github.com/yobasystems/alpine-ntp)
- [Gitlab - yobasystems/alpine-ntp](https://gitlab.com/yobasystems/alpine-ntp)

## 🐳 Container Registries

- [Dockerhub - yobasystems/alpine-ntp](https://hub.docker.com/r/yobasystems/alpine-ntp/)
- [Quay.io - yobasystems/alpine-ntp](https://quay.io/repository/yobasystems/alpine-ntp)
- [GHCR - yobasystems/alpine-ntp](https://ghcr.io/yobasystems/alpine-ntp)

## 🔗 Links

- [Yoba Systems](https://www.yobasystems.co.uk/)
- [Github - Yoba Systems](https://github.com/yobasystems/)
- [Dockerhub - Yoba Systems](https://hub.docker.com/u/yobasystems/)
- [Quay.io - Yoba Systems](https://quay.io/organization/yobasystems)
- [GHCR - Yoba Systems](https://ghcr.io/yobasystems)
- [Maintainer - Dominic Taylor](https://github.com/dominictayloruk)
