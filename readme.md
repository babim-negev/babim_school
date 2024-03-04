### Учебный проект

Суть проекта:





#### Развертывание

1) Создать файлы конфигурации командой 
```console
alembic init migration
```
2) Подкорректировать в migrations/env.py
```code
# 19-21 строчка
from db.models import Base
target_metadata = Base.metadata
#target_metadata = None
```
3) В alembic.ini
```code
Корректировать 58 строчку.
sqlalchemy.url = postgresql://postgres:postgres@0.0.0.0:5433/*ваша_бд*
```

4) Создаем миграции
```code
alembic revision --autogenerate -m "first db"   
```
5)  Накатываем миграции на бд
```code
alembic upgrade head
```




22222

pytest проводить на версии ==0.18.3

запускать тест через test_handlers.py