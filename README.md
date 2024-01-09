# Практическая работа №1. Приложение с общей архитектурой JavaEE #
## Задание 1 ##
Одним из вариантов запуска сервера приложений GlassFish является команда:

```
C:\путь\к\glassfish\bin\asadmin start-domain
```
C:\путь\к\glassfish - фактический путь к папке с программой

Пример использования команды и успешный **запуск** сервера:

![image](https://github.com/BandooSs/CSA_LR_1/blob/master/screenshot/1.jpg)



Пример как можно **остановить** работу сервера:

![image](https://github.com/BandooSs/CSA_LR_1/blob/master/screenshot/2.jpg)




Также возможно **перезапустить** сервер с помощью команды:

![image](https://github.com/BandooSs/CSA_LR_1/blob/master/screenshot/3.jpg)



## Задание 2 ##
 В качестве СУБД была выбрана программа **PostgreSQL**, версия 16.1

## Задание 3 ##
Наша база данных состоит из двух сущностей: **Player** и **Team**

Также будет реализована связь **один ко многим** => одна команда может иметь много игроков, но каждый игрок может быть связан только с одной командой.



Ниже представлен **скрипт** для создания таблиц Player и Team:

```
CREATE TABLE Team
(
   id_team int PRIMARY KEY,
   frist_name varchar(64) NOT NULL,
  city_name varchar(64) NOT NULL
);


CREATE TABLE Player
(
   id_player int PRIMARY KEY,
   first_name varchar(64) NOT NULL,
   last_name varchar(64) NOT NULL,
   fk_id_team int REFERENCES Team(id_team)
)
```

## Задание №4 ##

Для создания данных использовались **аннотации**:

1. **@Entity** - отмечает класс как сущность базы данных.
2. **@Id** - устанавливает поле как первичный ключ (Primary Key).
3. **@GeneratedValue** - устанавливает стратегию генерации значений для первичного ключа.
4. **@Column** - отмечает поле как колонку в таблице, когда имя поля неочевидно для записи в базу данных.
5. **@ManyToOne** - используется для работы с полями внешнего ключа (Foreign Key).
6. **@JoinColumn** - используется для явного указания имени колонки в базе данных, где будет храниться внешний ключ при использовании аннотации @ManyToOne.

Классы для представления сущностей расположены в папке models.

## Задание №5 ##

Бизнес-уровень для доступа к данным предоставляет метод **getAll()**, который возвращает список всех игроков из базы данных. Внутри метода реализована логика выполнения SQL-запроса и маппинга результатов в объекты Player.


## Задание №6 ##

Уровень представления был реализован с использованием сервлетов и JSP-файлов.

Существуют следующие типы сервлетов:
- **PlayerServlet** - получает список игроков с использованием PlayerService и передает его на JSP-страницу для отображения на клиентской стороне.
- **TeamServlet** -  перенаправляет запрос на JSP-страницу "/teamsJSP.jsp" без выполнения какой-либо логики обработки данных.
- **HelloServlet** -  перенаправляет запрос на JSP-страницу "/index.jsp"


Существуют следующие **JSP-файлы**:

- **index.jsp** -  представляет приветственное сообщение "Hello World!" и две ссылки на сервлеты, которые предназначены для дальнейшей навигации в приложении
- **playersJSP.jsp** -  принимает список игроков из атрибута запроса и отображает их в виде маркированного списка
- **teamJSP.jsp** - содержит заголовок "!!!!!All teams:"

## Задание № 7 ##

Для того чтобы все **работало вместе**, необходимо:

1. внедрить базу данных в приложение на сервере;
2. настроить приложение для использования определенной базы данных;
3. создать .war-пакет нашего приложения;
4. развернуть приложение на сервере.

Для взаимодействия с сервером мы используем графический интерфейс, доступный по адресу http://localhost:4848/.
### Создание .war-пакета ###
С помощью команды:  
```
mvn clean install
```
### Добавление war-пакета на сервер приложения ###


![изображение](https://github.com/BandooSs/CSA_LR_1/blob/master/screenshot/4.png)



## Результат работы ##

Основаня страничка, которая содержит два перехода на другие старницы с игроками и командами, а также красивое **приветствие**:
![изображение]([https://github.com/RaisssHab/ESA2023/assets/60664914/6b1089f6-cfb9-4b59-851b-989dd45de4f4](https://github.com/BandooSs/CSA_LR_1/blob/master/screenshot/5.png))

We can't add a lexicon entry without a phrase and a semantics. Let's create a couple for each:

![изображение](https://github.com/RaisssHab/ESA2023/assets/60664914/fbdfe4a2-ee13-4645-947e-96069995571c)

![изображение](https://github.com/RaisssHab/ESA2023/assets/60664914/4e503ece-e6f0-47f8-a736-066deeb21f01)

![изображение](https://github.com/RaisssHab/ESA2023/assets/60664914/384e05a5-757e-430d-b831-9c0fc2262609)

![изображение](https://github.com/RaisssHab/ESA2023/assets/60664914/f0650b2e-bbea-4aed-9dd3-84cb981f7f84)

Now we can do the following:

![изображение](https://github.com/RaisssHab/ESA2023/assets/60664914/6e04579d-53d9-4a23-b9e4-7bc9c0ab6dea)

![изображение](https://github.com/RaisssHab/ESA2023/assets/60664914/5fa81676-9126-493e-a97b-20f2b495e1db)

Suppose we didn't like the first entry. Let's edit it:

![изображение](https://github.com/RaisssHab/ESA2023/assets/60664914/755f5200-ddda-4adc-b087-c18817078c8e)

![изображение](https://github.com/RaisssHab/ESA2023/assets/60664914/f721c595-5c0e-4f17-872e-178ed939d9a1)

![изображение](https://github.com/RaisssHab/ESA2023/assets/60664914/8b6d24b6-02ba-4a01-98af-90419640f2e2)

We now can delete the second entry:

![изображение](https://github.com/RaisssHab/ESA2023/assets/60664914/1919e1bc-71b7-4c82-8886-528e0f50152c)

![изображение](https://github.com/RaisssHab/ESA2023/assets/60664914/ecd848b3-a121-4bbf-9514-a0b405947c1d)

![изображение](https://github.com/RaisssHab/ESA2023/assets/60664914/941b4799-ec15-4368-a6bd-8cb7d7d90c50)
