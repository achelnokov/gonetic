# Goneric

Библиотека сравнения слов с использованием алгоритма Daitch-Mokotoff Soundex.

Краткое описание алгоритма можно прочитать [тут](https://en.wikipedia.org/wiki/Daitch%E2%80%93Mokotoff_Soundex)

С помощью данного пакета можно кодировать слова алгоритмом и использовать полученные коды для индексации записей или сравнения слов.

Пример использования

```
package main

import (
	"fmt"
	"gitverse.ru/achelnokov/gonetic"
)

func main() {
	fmt.Println(gonetic.SetText("Иванов").DMCodes())
}

```

Функция **DMCodes** возвращает карту (map[string]string) где ключ - это указанное слово, значение - это код сформированный алгоритмом.



---


**Пример сравнения:**

Петр Иванов -> map[Иванов:076700 Петр:739000]
Пётр Ивонов -> map[Ивонов:076700 Пётр:739000]
Petr Ivanov -> map[Ivanov:076700 Petr:739000]

Петр Иванов == Пётр Ивонов == Petr Ivanov

Аспирин -> map[Аспирин:047960]
Оспирин -> map[Оспирин:047960]
Осперин -> map[Осперин:047960]

Аспирин == Оспирин == Осперин



