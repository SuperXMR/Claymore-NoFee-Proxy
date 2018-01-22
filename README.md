# Claymore-NoFee-Proxy

## What's this? How it works?

Please refer to [JuicyPasta/Claymore-No-Fee-Proxy](https://github.com/JuicyPasta/Claymore-No-Fee-Proxy/blob/master/README.md)


    Запустить ncpa.cpl
    Щелкните правой кнопкой мыши на сетевом адаптере -> Свойства
    Выберите IPv4 (TCP / IPV4) -> Свойства
    Установите свой LAN-адрес в статическом режиме (с маской, шлюзом и DNS)
    Нажмите кнопку « Дополнительно».
    Нажмите на кнопку добавления ниже IP-адреса
    Введите некоторый публичный IP-адрес (например, 194.12.12.2). Этот реальный адрес будет недоступен.
    Маска: 255.255.255.255
    У вас должен быть один шлюз (LAN)
    Если в прошлом была установлена некоторая запись localhost, измените ее для нового фальшивого IP-адреса WAN
    В нашем случае 127.0.0.1 становится 194.12.12.2
    Вы должны изменить его в скрипте скрипта python и, в конечном итоге, в свой файл хоста.


## Why do you rewrite this tool?

The old one([JuicyPasta/Claymore-No-Fee-Proxy](https://github.com/JuicyPasta/Claymore-No-Fee-Proxy/blob/master/README.md)) is buggy.
1. It was wrote with python 2.7.
2. If someone connect to the proxy, but do nothing and close the socket, it may add one thread permanently.
3. It will cause CPU usage becomes very high.

## Setup

### Python
Python 3 is required

## RUN
Run the proxy daemon first and pay attention to change the pool you use, you must specify here your real pool (here nanopool):
```
./stratum_proxy.py 8008 eth-eu2.nanopool.org 9999 0xB7716d5A768Bc0d5bc5c216cF2d85023a697D04D
```
