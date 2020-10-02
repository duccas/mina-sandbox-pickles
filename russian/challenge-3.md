---
description: 'Опрос по оборудованию сервера. (Награда 1,000 бонусных pts)'
---

# Challenge \#3

### Характеристики оборудования

Команда Mina хочет узнать больше об оборудовании, которое вы собираетесь использовать для предстоящей версии Mina testnet 3.3. Предоставленная вами информация поможет внести улучшения в будущие выпуски.

Заполните форму по [этой ссылке](https://forms.gle/Qft3VquQ5Nobgetb7).

В форме есть пункт CPU Platform. Что узнать какая у вас платформа, воспользуйтесь инструкцией ниже и внесите ответ в форму.

### На Linux:

Установим GCC:

```text
sudo apt install build-essential curl -y
sudo apt-get install manpages-dev
```

```text
gcc -march=native -Q --help=target | sed -ne 's/^  -march=\W*\(.*\)$/\1/p'
```

В ответ вы получите:

{% code title="\#ПРИМЕР ОТВЕТА" %}
```text
broadwell или knl
```
{% endcode %}

![](../.gitbook/assets/image%20%285%29.png)

### На Windows:

1. Установите [Windows Subsystem for Linux](https://docs.microsoft.com/en-us/windows/wsl/install-win10).
2. Дальше следуйте инструкциям для Linux, описанные выше.

### На Mac OSX:

1. Откройте терминал
2. Введите команду:

```text
sysctl -n machdep.cpu.brand_string
```

В ответ вы получите:

{% code title="\#ПРИМЕР ОТВЕТА" %}
```text
Intel(R) Core(TM) i5-8257U CPU @ 1.40GHz
```
{% endcode %}

