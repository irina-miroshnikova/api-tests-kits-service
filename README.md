# API Tests for Kits Service

Проект содержит API-автотесты для сервиса создания пользовательских наборов (Kits).

## Что проверяется

- Валидация входных данных
- Негативные сценарии (invalid input)
- Граничные значения (boundary values)
- Корректность HTTP-ответов

## Содержание проекта

Структура файлов:

```

api-tests-kits-service/
│── configuration.py            # Базовые URL и пути API
│── data.py                     # Тела запросов и заголовки
│── sender_stand_request.py     # Функции отправки HTTP-запросов
│── create_kit_name_kit_test.py # Автотесты по чек-листу
│── README.md                   # Описание проекта
│── .gitignore                  # Исключения для Git

```

---

## Установка и запуск

### 1. Клонировать репозиторий

```bash
git clone https://github.com/irina-miroshnikova/api-tests-kits-service.git
```

### 2. Перейти в директорию проекта

```bash
cd api-tests-kits-service
```

### 3. Создать виртуальное окружение

```bash
python -m venv .venv
```

### 4. Активировать окружение

**Windows PowerShell:**

```bash
.venv\Scripts\Activate.ps1
```

**Windows CMD:**

```cmd
.venv\Scripts\activate.bat
```

**Git Bash:**

```bash
source .venv/Scripts/activate
```

### 5. Установить зависимости

Если есть requirements.txt:

```bash
pip install -r requirements.txt
```

Если файла нет:

```bash
pip install pytest requests
```

---

## Запуск тестов

### Запустить все тесты

```bash
pytest -s
```

### Запустить конкретный тест

```bash
pytest create_kit_name_kit_test.py::test_kit_name_1_symbol -s
```

---

## Описание логики тестов
Тесты реализуют проверку валидации данных API и обработки ошибок.
Тесты проверяют:

* допустимую длину поля `name`;
* пустые значения;
* превышение максимальной длины;
* спецсимволы, пробелы, цифры;
* отсутствие параметра;
* неверный тип (число);
* корректные ответы сервера (201 и 400).

Позитивные и негативные проверки вынесены в отдельные функции для удобства переиспользования.

---

## Требования

* Python 3.10+
* Pytest
* Requests
* Активный стенд Практикума (URL указан в `configuration.py`).

---

## Примечание

Некоторые тесты могут завершиться статусом **FAILED**, если сервер возвращает некорректный ответ.
