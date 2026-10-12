# Fast_api

Учебный проект на FastAPI: асинхронный REST API с SQLAlchemy 2.0 и SQLite.

## Стек

- Python 3.9+
- FastAPI, Uvicorn
- SQLAlchemy 2.0 (asyncio) + aiosqlite
- Pydantic v2, pydantic-settings
- Poetry

## Запуск

```bash
poetry install
poetry run python main.py
```

Сервер поднимется на http://127.0.0.1:8000, документация Swagger — на http://127.0.0.1:8000/docs.

Файл базы `db.sqlite3` и таблицы создаются автоматически при старте.

## Эндпоинты

| Метод | Путь | Описание |
|-------|------|----------|
| GET | `/api/v1/products/` | Список продуктов |
| POST | `/api/v1/products/` | Создать продукт |
| GET | `/api/v1/products/{product_id}/` | Продукт по id |
| POST | `/users/` | Создать пользователя (без сохранения в БД) |
| GET | `/items/` | Список элементов (заглушка) |
| GET | `/items/latest/` | Последний элемент (заглушка) |
| GET | `/items/{item_id}/` | Элемент по id (заглушка) |
| GET | `/hello/?name=...` | Приветствие |
| POST | `/calc/add/?a=1&b=2` | Сложение двух чисел |

## Структура

```
main.py            точка входа, сборка приложения
core/config.py     настройки (префикс API, URL базы)
core/models/       модели SQLAlchemy и DatabaseHelper
api_v1/products/   схемы, CRUD и роуты продуктов
users/             схемы и роуты пользователей
items_views.py     роуты items
```
