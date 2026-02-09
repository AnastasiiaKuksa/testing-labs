# Лабораторна робота №7

### Виконала:  
**Кукса Анастасія**

## Частина A. Розгортання тестового веб-застосунку (Docker)

### Крок 1. Запуск контейнера

Команда в терміналі:

```bash
docker run -d --rm -p 7080:5000 gprestes/the-internet:v2.6.5
```
<img width="1129" height="164" alt="image" src="https://github.com/user-attachments/assets/4d55b14f-e938-4487-861d-288eb08543c9" />

### Крок 2. Перевірка запуску

Відкриємо в браузері:

```
http://localhost:7080
```

<img width="1918" height="999" alt="image" src="https://github.com/user-attachments/assets/7179b10e-b9cf-4608-9314-ceb70f79047d" />


### Крок 3. Ознайомлення з функціоналом

#### Ознайомлюємося: 
- **Form Authentication**
<img width="1919" height="662" alt="image" src="https://github.com/user-attachments/assets/bd501ca9-3a0e-42c4-98ea-d74ee4c4e539" />

- **Add/Remove Elements**
<img width="1919" height="489" alt="image" src="https://github.com/user-attachments/assets/1e3eb914-9ba4-4f4e-9fd0-27a23f4cb74a" />


## Частина B. Створення автотестів у Katalon Recorder

### Крок 1. Встановлення інструменту

Встановили розширення:
<img width="1919" height="972" alt="image" src="https://github.com/user-attachments/assets/0510d826-1709-414b-82c0-788f639b28e4" />

<img width="1083" height="634" alt="image" src="https://github.com/user-attachments/assets/b31ab144-47c7-4a64-bb30-e805fcd95482" />


### Крок 2. Створення проєкту

#### Створення Test Suite з назвою: "SmokeSuite"

<img width="1004" height="649" alt="image" src="https://github.com/user-attachments/assets/b0eff7cc-75d6-4e0a-aa60-ae5cffad26ee" />

### Крок 3. Тест №1 — Успішний логін (Positive test)

#### Сценарій виконання:

Відкрили сторінку Form Authentication.
Ввели:
* username: tomsmith
* password: SuperSecretPassword!

Натиснули кнопку Login.

<img width="1918" height="727" alt="image" src="https://github.com/user-attachments/assets/9d583446-f3a6-4580-9769-52d5c56c9112" />

#### Результати перевірок:

1. На сторінці з’явилось повідомлення You logged into a secure area! ✅
2. Кнопка Logout присутня ✅
3. Користувач успішно знаходиться у secure area ✅
<img width="1919" height="718" alt="image" src="https://github.com/user-attachments/assets/5f9f4e29-b966-48e8-abf2-bce95ab9326f" />

### Крок 4. Тест №2 — Невдалий логін (Negative test)

#### Сценарій виконання:

1. Відкрили сторінку логіну.
2. Ввели неправильний пароль.
3. Натиснули Login.

#### Результати перевірок:

1. З’явилось повідомлення про помилку ✅
2. Secure area залишилась недоступною ✅
3. Кнопка Logout відсутня ✅
<img width="1919" height="795" alt="image" src="https://github.com/user-attachments/assets/395ffd46-f479-43a4-bc45-a891fc579b9a" />

### Крок 5. Тест №3 — Add / Remove Elements

#### Сценарій виконання:

1. Відкрили сторінку Add/Remove Elements.
2. Натиснули Add Element 3 рази.

#### Результати перевірок:

1. На сторінці з’явилось 3 кнопки Delete ✅
2. Видалили один елемент.
3. Після видалення залишилось 2 кнопки Delete ✅

<img width="1914" height="482" alt="image" src="https://github.com/user-attachments/assets/a62335dc-27aa-4b4d-8382-a4afecf616f4" />
<img width="1919" height="540" alt="image" src="https://github.com/user-attachments/assets/a142b599-2c51-40e3-b5c1-10c0d0e30a1c" />


