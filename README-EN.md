#### See [Configuration and options](#-configuration-and-options) on how to change the interface language

### 💽 Install and run 

Attention! Updates happen automatically, all steps except the last one need to be done only at the first time!

### Windows

Our software does not contain viruses, but some antiviruses identify such software as potentially dangerous and block the files.
You may need to allow running the downloaded file, or disable your antivirus.

1. [Download the latest version](https://github.com/corpus-dev/mhddos_proxy/releases/latest/download/mhddos_proxy_win.exe)
   and save to a convenient location
2. To start, simply launch the file by double-click

### Linux
1\. Download the appropriate version for your platform
##### x64 (amd64)
```
curl https://github.com/corpus-dev/mhddos_proxy/releases/latest/download/mhddos_proxy_linux -Lo mhddos_proxy_linux 
```
##### arm64 (aarch64)
```
curl https://github.com/corpus-dev/mhddos_proxy/releases/latest/download/mhddos_proxy_linux_arm64 -Lo mhddos_proxy_linux 
```

2\. Next, run `chmod +x mhddos_proxy_linux`
3\. To start, run `./mhddos_proxy_linux` directly or inside `screen`


### Docker (any platform)

1. Install and launch [Docker](https://docs.docker.com/desktop/#download-and-install)
2. Run with the command `docker run -it --rm --pull always --net=host ghcr.io/corpus-dev/mhddos_proxy`

### Raspberry Pi
Aarch64 version should work on RPi4, probably on RPi3 too. The main thing is to have 64x OS.

### Android

#### Setup

Requies [Termux](https://github.com/termux/termux-app/releases) and **rooted device**
```
apt update -y && apt install -y root-repo tsu glibc-repo glibc
curl https://github.com/corpus-dev/mhddos_proxy/releases/latest/download/mhddos_proxy_linux_arm64 -Lo mhddos_proxy
chmod +x mhddos_proxy
grun -c mhddos_proxy
```
#### Run
##### arm64 (aarch64)
```
sudo grun -n ./mhddos_proxy
```
##### arm32 (armv7)
```
apt install -y qemu-user-aarch64
sudo grun -n qemu-aarch64 ./mhddos_proxy
```

### 🛠 Configuration and options

An **mhddos.ini** file will be created in the current directory on the first launch  
You may edit it to change configuration

    # Change language (ua | en | es | de | pl | lt)
    lang = ua

    # Run multiple copies (set "auto" for max value, requires 3+ core CPU and stable network)
    copies = 1

    # Number of threads per copy (to enable, remove the hashtag symbol on the next line)
    #threads = 8000

    # Use my IP/VPN in % from 0 to 100 (requires VPN or remote server)
    use-my-ip = 0

You can also specify options via command line in `--lang en`  format

Full list of options is available by `--help` command
