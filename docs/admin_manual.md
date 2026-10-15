# Руководство администратора AccessEvent

## 1. Системные требования
- Python 3.11+
- PostgreSQL 15+
- Docker 24+ (для контейнерного запуска)

## 2. Развёртывание

### Локально:
1. `python -m venv venv`, затем активируйте окружение
   (Windows: `venv\Scripts\activate`, macOS/Linux: `source venv/bin/activate`)
2. `pip install -r requirements.txt`
3. Настройте `.env` (см. раздел 3)
4. `python app.py`
