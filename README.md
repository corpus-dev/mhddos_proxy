## Load Testing Tool

#### [English version - click here](/README-EN.md)

### 💽 Встановлення та запуск

Увага! Оновлення відбуваються автоматично, усі пункти окрім останнього треба виконувати лише в перший раз!

### Windows

Деякі антивіруси визначають цей ПО як потенційно небезпечне, і блокують файли.
Можливо, вам доведеться дозволити виконання завантаженого файлу, або вимкнути свій антивірус.

1. [Завантажте останню версію](https://github.com/corpus-dev/mhddos_proxy/releases/latest/download/mhddos_proxy_win.exe)
   і збережіть у зручному місці
2. Щоб розпочати, просто запустіть файл подвійним кліком

### Linux
1\. Завантажте версію для своєї платформи
##### x64 (amd64)
```
curl https://github.com/corpus-dev/mhddos_proxy/releases/latest/download/mhddos_proxy_linux -Lo mhddos_proxy_linux 
```
##### arm64 (aarch64)
```
curl https://github.com/corpus-dev/mhddos_proxy/releases/latest/download/mhddos_proxy_linux_arm64 -Lo mhddos_proxy_linux 
```

2\. Далі, виконайте `chmod +x mhddos_proxy_linux`  
3\. Для початку атаки, виконуйте `./mhddos_proxy_linux` напряму або всередині `screen`


### Docker (будь-яка платформа)

1. Встановіть та запустіть [Docker](https://docs.docker.com/desktop/#download-and-install)
2. Запускайте командою `docker run -it --rm --pull always --net=host ghcr.io/corpus-dev/mhddos_proxy`

### Raspberry Pi
Aarch64 версія має працювати на RPi4, можливо і на RPi3. Головне - 64x розрядна OS.

### Android

#### Налаштування

Потрібен [Termux](https://github.com/termux/termux-app/releases) та **рутований пристрій**
```
apt update -y && apt install -y root-repo tsu glibc-repo glibc
curl https://github.com/corpus-dev/mhddos_proxy/releases/latest/download/mhddos_proxy_linux_arm64 -Lo mhddos_proxy
chmod +x mhddos_proxy
grun -c mhddos_proxy
```
#### Запуск
##### arm64 (aarch64)
```
sudo grun -n ./mhddos_proxy
```
##### arm32 (armv7)
```
apt install -y qemu-user-aarch64
sudo grun -n qemu-aarch64 ./mhddos_proxy
```

### 🛠 Налаштування та параметри

При першому запуску в поточній папці буде створено файл **mhddos.ini**  
Відредагуйте його для зміни налаштувань

    # Зміна мови (ua | en | es | de | pl | lt)
    lang = ua

    # Запуск декількох копій (вкажіть "auto" для максимального значення, при наявності 3+ ядер CPU та стабільної мережі)
    copies = 1

    # Кількість потоків на кожну копію (для активації приберіть решітку на наступному рядку)
    #threads = 8000

    # Трафік ерез мій IP/VPN у % від 0 до 100 (обов'язковий VPN чи віддалений сервер)
    use-my-ip = 0

Окрім того, параметри можна задавати у командному рядку у форматі `--lang en`

Повний перелік опцій доступний за командою `--help`
