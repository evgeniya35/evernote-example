# evernote-example
Набор скриптов для работы с API [Evernote](https://evernote.com/) - сервиса ведения заметок, календарей, организации дел. Для работы необходимо зарегистрироваться, получить токен приложения по инструкции [Аутентификация с помощью Evernote Cloud API с использованием OAuth](https://dev.evernote.com/get-token/)

## Окружение
Python должен быть установлен.
Пример файла переменных окружения:
```
EVERNOTE_CONSUMER_KEY={Персональный ключ}
EVERNOTE_CONSUMER_SECRET={Секретный ключ}
EVERNOTE_PERSONAL_TOKEN={Персональный token}

JOURNAL_TEMPLATE_NOTE_GUID={GUID записи/заметки}
JOURNAL_NOTEBOOK_GUID={GUID блокнота}

INBOX_NOTEBOOK_GUID={GUID блокнота}
```

## Зависисмости
Используйте pip для установки зависимостей:
```bash
pip install -r requirements.txt
```
Установите [evernote-sdk-python3](https://github.com/evernote/evernote-sdk-python3)


## list_notebooks.py
Выводит в консоль уникальный идентификатор GUID и наименование блокнотов пользователя.
Запуск:
```bash
python list_notebooks.py
```

## dump_inbox.py
Выводит в консоль текстовое содержимое заметок блокнота `INBOX_NOTEBOOK_GUID`.
Запуск. Укажите количество выводимых заметок в аргументе скрипта, по умолчанию 10:
```bash
python dump_inbox.py 2
```
Пример вывода:
```
--------- 1 ---------
Hello, dvmn!

--------- 2 ---------
Hello, world!
```

## add_note2journal.py
Копирует заметку `JOURNAL_TEMPLATE_NOTE_GUID` в блокнот `JOURNAL_NOTEBOOK_GUID`.
Запуск. Укажите дату `YYYY-MM-DD` в аргументе скрипта:
```bash
python add_note2journal.py "2021-11-07"
```
Выводит в консоль заголовок новой заметки. Пример вывода:
```
Title Context is:
{
    "date": "2021-11-07",
    "dow": "воскресенье"
}
Note created: Это тестовая заметка, 2021-11-07, воскресенье
Done
```

## Цель проекта
Код написан в образовательных целях на онлайн-курсе для веб-разработчиков [dvmn.org](https://dvmn.org/).