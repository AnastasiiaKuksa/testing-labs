# Лабораторна робота №6

### Виконала:  
**Кукса Анастасія**

## ЗАВДАННЯ №1. GET-запит (отримання даних)

### Запит:

GET `https://jsonplaceholder.typicode.com/posts`


### Результат перевірки:

1. Статус-код: 200 OK ✅
2. Формат відповіді: JSON ✅
3. Відповідь містить список об’єктів: так, кожен об’єкт містить поля userId, id, title, body. ✅

<img width="1919" height="809" alt="image" src="https://github.com/user-attachments/assets/d320d291-34df-4438-a5eb-701665db8767" />


## ЗАВДАННЯ №2.  GET-запит з параметром

### Запит:

GET `https://jsonplaceholder.typicode.com/posts/1`

### Результат перевірки:

1. Статус-код: 200 OK ✅
2. Поля у відповіді присутні: userId, id, title, body ✅

<img width="1919" height="772" alt="image" src="https://github.com/user-attachments/assets/0845dd0f-deeb-405e-b641-cc7a12b7b4ce" />

## ЗАВДАННЯ №3. POST-запит (створення ресурсу)

### Запит:

POST `https://jsonplaceholder.typicode.com/posts`

### Body (raw, JSON):
```
{
  "title": "Postman API test",
  "body": "This is a test post",
  "userId": 1
}
```

### Результат перевірки:

1. Статус-код: 201 Created ✅
2. Поле id присутнє ✅
3. Відповідь у форматі JSON ✅
<img width="1919" height="756" alt="image" src="https://github.com/user-attachments/assets/55a9a514-ebbd-409c-869d-26cc2399f081" />

## ЗАВДАННЯ №4.  PUT-запит (оновлення ресурсу)
### Запит:

PUT `https://jsonplaceholder.typicode.com/posts/1`

### Body (raw, JSON):
```
{
  "id": 1,
  "title": "Updated title",
  "body": "Updated body",
  "userId": 1
}
```
### Результат перевірки:

1. Статус-код: 200 OK ✅
2. Дані у відповіді оновлені ✅

<img width="1912" height="723" alt="image" src="https://github.com/user-attachments/assets/643abf80-9748-4111-9215-5732d2b357b8" />


## ЗАВДАННЯ №5.  DELETE-запит (видалення ресурсу)

### Запит:

DELETE `https://jsonplaceholder.typicode.com/posts/1`

### Результат перевірки:

1. Статус-код: 200 OK або 204 No Content ✅
2. Тіло відповіді порожнє або мінімальне ✅

<img width="1913" height="640" alt="image" src="https://github.com/user-attachments/assets/c58c6596-7c1a-4f6f-848a-0c62190b9392" />

