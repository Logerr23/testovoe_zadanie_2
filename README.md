## Задание 1  
Ссылка на страницу, которую необходимо протестировать:
https://widgets.inssmart.ru/contract/mortgage/?appId=79f46bfb-d4ba-50aa-8269-7289dd16700c&secret=6ca520c0-328b-5b65-ab5c-b41332a3e667

Задача:
1.  Составьте перечень проверок (чек лист) для первой страницы, который по Вашему мнению будет достаточным для выпуска продукта в продакшен.
2. Сгруппируйте проверки в форме иерархического списка. В этом  вам поможет https://checkvist.com/ (должен получиться полноценный чек лист, с понятной группировкой. Документ должен соответствовать вашему представлению о том, что можно использовать в реальной работе, не забывайте про ожидаемый результат)
3. Укажите приоритеты проверок.

### Решение - https://checkvist.com/p/kBqbX8HyMOFgtjpzR3IJQ6

## Задание 2  
Коллекция в swagger, с которой предстоит работать: https://petstore.swagger.io/

Вам необходимо на основе этой коллекции, создать коллекцию в Postman
Нужно будет работать с запросами:

1. Создать нового питомца (метод POST /pet)
Прописать скрипт, который берет из тела ответа id созданного питомца и записывает в 
окружение.

2. Запросить питомца по id (метод GET /pet/{petId}) используя в запросе ранее 
записанную переменную из окружения
Прописать скрипт, который будет брать тело ответа, менять параметр «status» на 
«sold» (продан) и перенаправлять его в запрос на изменение питомца (метод PUT 
/pet)

3. Коллекцию необходимо экспортировать (Export/ Export Collection) и отправить на почту (ссылками на постман не принимаю!).

В итоге должно быть два запроса, при отправке которых должен создаваться новый 
питомец и он же продаваться

### Решение - [коллекция](https://github.com/Logerr23/testovoe_zadanie_2/blob/main/%D0%97%D0%B0%D0%B4%D0%B0%D0%BD%D0%B8%D0%B5%202.json)

## Задание 3 
Таблицы, с которыми предстоит работать:: заказы (Orders) и клиенты (Customers), найти их можно тут:
https://www.w3schools.com/sql/trysql.asp?filename=trysql_asc

Необходимо вывести id клиента и имя клиента, сделавших больше 5-ти заказов, а также количество заказов и дату последнего заказа. Список должен идти по убыванию от клиентов с большим количеством заказов к клиентам с меньшим количеством заказов

### Решение: 
```SQL
SELECT  
    c.CustomerID,  
    c.CustomerName,  
    COUNT(o.OrderID) as TotalOrders,  
    MAX(o.OrderDate) as LastOrderDate  
FROM  
    Customers c  
    JOIN Orders o  
        ON c.CustomerID = o.CustomerID  
GROUP BY  
    c.CustomerID,  
    c.CustomerName  
HAVING  
    COUNT(o.OrderID) > 5  
ORDER BY  
    TotalOrders DESC;  
```
