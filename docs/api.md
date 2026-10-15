# Описание API AccessEvent

## Таблица эндпоинтов

| Метод | URL | Доступ | Вход (JSON) | Ответы |
|---|---|---|---|---|
| POST | /api/register | все | username, email, password, role | 201 user_id; 400 ошибки валидации |
| POST | /api/login | все | email, password | 200 token; 401 неверные данные |
| GET | /api/events | все | — | 200 список мероприятий |
| GET | /api/events/<id> | все | — | 200 мероприятие; 404 не найдено |
| POST | /api/events | organizer | title, event_date, is_inclusive | 201 id; 401 без токена |
| PUT | /api/events/<id> | organizer | title, description, event_date, location | 200 обновлённое; 403 чужое |
| DELETE | /api/events/<id> | organizer | — | 200 удалено; 403 чужое |
| POST | /api/registrations | user | event_id, accessibility_request | 201; 400 повторная; 404 нет события |
| GET | /api/registrations | user | — | 200 список регистраций |
| PUT | /api/registrations/<id> | organizer | status (pending/confirmed/cancelled) | 200; 400 неверный статус |

## Примеры

### POST /api/register — запрос
```json
{"username": "anna", "email": "anna@mail.ru", "password": "Passw0rd!", "role": "user"}