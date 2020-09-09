---
description: >-
  Предоставьте время для производства блоков с помощью New Pickles SNARK
  (Награда 1,000 pts)
---

# Challenge \#1

### Открываем логи Coda

```text
docker logs --follow coda
```

Ищем строки `Producing block in 0 slots` и `Generated transition $state_hash was accepted into transition frontier` и делаем скриншот как на картинке ниже. Далее считаем время от производства блока до генерирования нового. В моем случае это 4 минуты 57 секунд. 

Сохраните скриншот и время до генерации нового блока а так же скопируйте содержимое логов в текстовый файл. Это нам понадобится для заполнения формы. 

![](../.gitbook/assets/image%20%282%29.png)

