---
description: 'Создание и отправка Fun токенов (Награда до 1,500 pts)'
---

# Challenge \#2

### **Новая функция: Fun токены на Mina.**

Теперь пользователи могут создавать свои собственные \(слой 2\) токены по протоколу Mina, например, для будущего Snapp \(приложения на основе SNARK\), которое будет построено на основе Coda.

{% hint style="info" %}
1. Награда за задание по минту 500 pts.
2. Дополнительная награда 1,000 pts за отправку токенов на следующий адрес: **B62qoDWfBZUxKpaoQCoFqr12wkaY84FrhxXNXzgBkMUi2Tz4K8kBDiv**
{% endhint %}

### 1. Создадим токены

Для доступа к любым командам [Mina CLI](https://minaprotocol.com/docs/cli-reference):

```text
sudo docker exec -it mina bash
```

Для начала нужно разблокировать аккаунт:

```text
coda accounts unlock -public-key B62qrPN5Y5yq8kGE3FbVKbGTdTAJNdtNtB5sNVpxyRwWGcDEhpMzc8g
```

В поле ввода пароля ничего не пишем и жмем ENTER.

Теперь создадим токены:

```text
coda client create-token -sender B62qrPN5Y5yq8kGE3FbVKbGTdTAJNdtNtB5sNVpxyRwWGcDEhpMzc8g
```

В ответ мы получим следующее:

{% code title="\#ПРИМЕР ОТВЕТА " %}
```text
Dispatched create new token command with ID 2cUDm3QoJ14znWj5LxN8hjwwuvtwi9FGXcy56i4dPvYizPNwr3V9c9ePYxy3pJKjgogNx28jwHhqupi6wHFgXBmU5iX27iK1zUvJarj6wJsUG8segWXc4LGPed66YbYk3u9HiWw4v8cYYEqcy1mU6hqfj5JPMPthEBifxUMHZTqCwZmYWSdiERxB6PtPEdXVraWaYPVU4Q8vtpSN7oSTK1AXyXLYYR835CBrNSmgbLvoBDNroCKwcQrzw4b76BFNLe6EuWvBcMgX6npeeAbPg8z8iJ4PKz3gA64o1Y72kCrqyqus718LwXcmp5jxsYvJB2CJHzyZ
```
{% endcode %}

### 2. Получим ID токенов

Чтобы проводить следующие операции нам нужно знать ID токенов. Получим его следующей командой:

```text
coda client get-tokens -public-key B62qrPN5Y5yq8kGE3FbVKbGTdTAJNdtNtB5sNVpxyRwWGcDEhpMzc8g
```

В ответ мы получим следующее:

{% code title="\#ПРИМЕР ОТВЕТА" %}
```text
Accounts are held for token IDs:
1
```
{% endcode %}

### 3. Проверим баланс токенов

Баланс токенов проверяем командой ниже с вашим ID токенов:

```text
coda client get-balance -token 1 -public-key B62qrPN5Y5yq8kGE3FbVKbGTdTAJNdtNtB5sNVpxyRwWGcDEhpMzc8g
```

Мы увидим баланс mina токенов.

### 4. Минт токенов

Чтобы сминтить новые токены нужно выполнить команду `mint-tokens`. Будут созданы 1,000 токенов в учетной записи отправителя транзакции под номером token ID 2.

```text
coda client mint-tokens -sender B62qrPN5Y5yq8kGE3FbVKbGTdTAJNdtNtB5sNVpxyRwWGcDEhpMzc8g -token 2 -amount 1000
```

Проверим баланс командой \(баланс появится не сразу, нужно подождать около 5 минут\):

```text
coda client get-balance -token 2 -public-key B62qrPN5Y5yq8kGE3FbVKbGTdTAJNdtNtB5sNVpxyRwWGcDEhpMzc8g
```

Через некоторое время мы должны увидеть на балансе 1,000 mina токенов.

{% code title="\#ПРИМЕР ОТВЕТА" %}
```text
coda client get-balance -token 2 -public-key B62qrPN5Y5yq8kGE3FbVKbGTdTAJNdtNtB5sNVpxyRwWGcDEhpMzc8g
Balance: 1000 tokens
```
{% endcode %}

### 5. Отправка токенов

По заданию нам нужно отправить 50 токенов на адрес `B62qoDWfBZUxKpaoQCoFqr12wkaY84FrhxXNXzgBkMUi2Tz4K8kBDiv`.  
Чтобы это сделать нам сначала нужно добавить получателя командой ниже:

```text
coda client create-token-account -sender B62qrPN5Y5yq8kGE3FbVKbGTdTAJNdtNtB5sNVpxyRwWGcDEhpMzc8g -receiver B62qoDWfBZUxKpaoQCoFqr12wkaY84FrhxXNXzgBkMUi2Tz4K8kBDiv -token 2
```

Теперь отправим 50 токенов.   
В поле `-memo "My First TX"` вместо `My First TX` можно вписать что угодно. Либо оставить так, как есть.

```text
coda client send-payment -sender B62qrPN5Y5yq8kGE3FbVKbGTdTAJNdtNtB5sNVpxyRwWGcDEhpMzc8g -receiver B62qoDWfBZUxKpaoQCoFqr12wkaY84FrhxXNXzgBkMUi2Tz4K8kBDiv -token 2 -memo "My First TX" -amount 50
```

Через некоторое время токены поступят на адрес. Чтобы проверить баланс введите следующую команду:

```text
coda client get-balance -token 2 -public-key B62qoDWfBZUxKpaoQCoFqr12wkaY84FrhxXNXzgBkMUi2Tz4K8kBDiv
```

Теперь сделайте скриншот вывода команды баланса как показано ниже. 

![](../.gitbook/assets/image%20%283%29.png)

### 6. Заполнение формы

Для заполнения формы по заданиям Challenge \#1 и Challenge \#2 перейдите по [этой ссылке](https://share.hsforms.com/1V-gRVnWZSLehZVB_F3sacQ4xuul). 

{% embed url="https://share.hsforms.com/1V-gRVnWZSLehZVB\_F3sacQ4xuul" %}

1. Вам нужно ввести свой email.
2. Discord ID
3. Время производства блока, которое мы считали в Challenge \#1
4. Загрузить скриншот логов производства блока и текстовый файл с логами из Challenge \#1
5. Загрузить скриншот баланса токенов по адресу `B62qoDWfBZUxKpaoQCoFqr12wkaY84FrhxXNXzgBkMUi2Tz4K8kBDiv` из Challenge \#2

![](../.gitbook/assets/image%20%284%29.png)

