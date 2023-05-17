# EN |  Weather
The program shows the weather in the city from the list of cities using the website "http://wttr.in /".
The program is written in Python version 3.10.5.

Libraries used:
- [Requests](https://requests.readthedocs.io/en/latest/index.html)

Website:
- [wttr.in](https://wttr.in/)

# How the code works?
Adds the necessary library
```python
import requests
```

Creating a list of "cities", which consists of Russian cities
```python
cities = {
    'Омск',
    'Калининград',
    'Челябинск',
    'Владивосток',
    'Красноярск',
    'Москва',
    'Екатеринбург'
}
```

Next, we create a function for accessing the site with the variable "city" and a function with parameters
```python
def make_url(city):
    return f'http://wttr.in/{city}'

def make_parameters():
    params = {
        'format' : 2,
        'M': '',
        'lang' : 'ru'
    }
    return params
```

Creating a function where the status of the code is checked. If the site code is 200, then we output the response to the command line, if it is not 200, then we output a network error to the response line
```python 
def what_weather(city):
    try:
        res = requests.get(make_url(city), params=make_parameters())
        if res.status_code == 200:
            return res.text
        else:
            return '<ошибка на сервере погоды>'
    except requests.ConnectionError:
        return '<сетевая ошибка>'

```

At the end, we output our answer in a loop

```python
print('Погода в городах:')
for  city in cities:
    print(city, what_weather(city))
```
## An example of how the program works:

![image](https://user-images.githubusercontent.com/64695348/232311404-db86a488-df16-493a-9de8-5821dbe84755.png)


# RU | Погода
Программа показывает погоду в городе из списка городов, использующих веб-сайт "http://wttr.in /".
Программа написана на Python версии 3.10.5.

Используемые библиотеки:
- [Requests](https://requests.readthedocs.io/en/latest/index.html)

Вебсайт:
- [wttr.in](https://wttr.in/)

# Как работает код?
Добавляет необходимую библиотеку
```python
import requests
```

Созданем список "городов", который состоит из российских городов
```python
cities = {
    'Омск',
    'Калининград',
    'Челябинск',
    'Владивосток',
    'Красноярск',
    'Москва',
    'Екатеринбург'
}
```
Далее мы создаем функцию для доступа к сайту с переменной "город" и функцию с параметрами
```python
def make_url(city):
    return f'http://wttr.in/{city}'

def make_parameters():
    params = {
        'format' : 2,
        'M': '',
        'lang' : 'ru'
    }
    return params
```
Далее мы создаем функцию для доступа к сайту с переменной "город" и функцию с параметрами
```python
def make_url(city):
    return f'http://wttr.in/{city}'

def make_parameters():
    params = {
        'format' : 2,
        'M': '',
        'lang' : 'ru'
    }
    return params
```

Создание функции, в которой проверяется статус кода. Если код сайта равен 200, то мы выводим ответ в командную строку, если он не равен 200, то мы выводим сетевую ошибку в строку ответа
```python 
def what_weather(city):
    try:
        res = requests.get(make_url(city), params=make_parameters())
        if res.status_code == 200:
            return res.text
        else:
            return '<ошибка на сервере погоды>'
    except requests.ConnectionError:
        return '<сетевая ошибка>'

```
В конце мы выводим наш ответ в цикле
```python
print('Погода в городах:')
for  city in cities:
    print(city, what_weather(city))
```
## Пример того, как работает программа:
![image](https://user-images.githubusercontent.com/64695348/232311404-db86a488-df16-493a-9de8-5821dbe84755.png)
