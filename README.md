# Домашнее задание к занятию "7.5. Основы golang" dev-17_golang-yakovlev_vs
golang

С `golang` в рамках курса, мы будем работать не много, поэтому можно использовать любой IDE. 
Но рекомендуем ознакомиться с [GoLand](https://www.jetbrains.com/ru-ru/go/).  

## Задача 1. Установите golang.
1. Воспользуйтесь инструкций с официального сайта: [https://golang.org/](https://golang.org/).
2. Так же для тестирования кода можно использовать песочницу: [https://play.golang.org/](https://play.golang.org/).

#### Решение

```bash
root@ansibleserv:~/ansible/playbook# go version
go version go1.13.8 linux/amd64
```

## Задача 2. Знакомство с gotour.
У Golang есть обучающая интерактивная консоль [https://tour.golang.org/](https://tour.golang.org/). 
Рекомендуется изучить максимальное количество примеров. В консоли уже написан необходимый код, 
осталось только с ним ознакомиться и поэкспериментировать как написано в инструкции в левой части экрана.

#### Решение
Ознакомился
#### Задача 3. Написание кода. 
Цель этого задания закрепить знания о базовом синтаксисе языка. Можно использовать редактор кода 
на своем компьютере, либо использовать песочницу: [https://play.golang.org/](https://play.golang.org/).

1. Напишите программу для перевода метров в футы (1 фут = 0.3048 метр). Можно запросить исходные данные 
у пользователя, а можно статически задать в коде.
    Для взаимодействия с пользователем можно использовать функцию `Scanf`:
    ```
    package main
    
    import "fmt"
    
    func main() {
        fmt.Print("Enter a number: ")
        var input float64
        fmt.Scanf("%f", &input)
    
        output := input * 2
    
        fmt.Println(output)    
    }
    ```

#### Решение

```bash
package main

import "fmt"

func main() {
    fmt.Print("Enter meters: ")
    var input float64
    fmt.Scanf("%f", &input)

    output := input * 3.28084

    fmt.Println(output, "ft")
}
```
```bash
root@ansibleserv:~/go# go run 3.1/main.go
Enter meters: 1
3.28084 ft
root@ansibleserv:~/go# go run 3.1/main.go
Enter meters: 3
9.84252 ft
```

 
2. Напишите программу, которая найдет наименьший элемент в любом заданном списке, например:
    ```
    x := []int{48,96,86,68,57,82,63,70,37,34,83,27,19,97,9,17,}
    ```

#### Решение
```bash
package main

import "fmt"

func main() {
    x := []int{48,96,86,68,57,82,63,70,37,34,83,27,19,97,9,17}

    min := x[0]
    for _, y := range x {
            if (y < min) {
                min = y
            }
    }

    fmt.Println(min)
}
```

```bash
root@ansibleserv:~/go# go run 3.2/main.go
9
```


3. Напишите программу, которая выводит числа от 1 до 100, которые делятся на 3. То есть `(3, 6, 9, …)`.

#### Решение

```bash
package main

import "fmt"

func createNumbers(lo int, hi int) []int {
	s := make([]int, hi-lo+1)
	for i := range s {
		s[i] = i + lo
	}
	return s
}

func main() {
	for _, value := range createNumbers(1, 100) {
		if value%3 == 0 {
			fmt.Println(value)
		}
	}
}
```

```bash
root@ansibleserv:~/go# go run 3.3/main.go
3
6
9
12
15
18
21
24
27
30
33
36
39
42
45
48
51
54
57
60
63
66
69
72
75
78
81
84
87
90
93
96
99

```


В виде решения ссылку на код или сам код. 

#### Задача 4. Протестировать код (не обязательно).



### Как cдавать задание

Выполненное домашнее задание пришлите ссылкой на .md-файл в вашем репозитории.

---


