 Практическое задание 2

Студент группы *ЭФМО-02-25 Пягай Даниил Игоревич*

## Описание

**Цели:**

- Понять назначение ключевых директорий (cmd/, internal/, pkg/ и др.).
- Научиться раскладывать код и артефакты проекта по "правильным" местам.
- Собрать минимальный скелет проекта и запустить "пустой" main.go.

## Создание структуры проекта

```bash
mkdir -p ~/myapp/cmd/myapp ~/myapp/internal/app ~/myapp/utils
cd ~/myapp
```

### Инициализация модуля

```bash
go mod init myapp
```

### Создание файлов проекта

Создаём три файла:

1. cmd/myapp/main.go - минимальный вход.
2. internal/app/app.go - "сердце" приложения.
3. utils/logger.go - простой логгер.

Содержание cmd/myapp/main.go:

![main.go](img/main.go.png)

Содержание internal/app/app.go:

![app.go](img/app.go.png)

Содержание utils/logger.go:

![logger.go](img/logger.go.png)

## Запуск и проверка

```bash
go run ./cmd/myapp
```
![run.go](img/go.run.png)

Проверка запущенного API (в другом терминале):

```bash
curl http://localhost:8081/Hello
curl http://localhost:8081/ping
```
![curl](img/curl.png)

## Сборка бинарника

```bash
go build -o bin/myapp ./cmd/myapp
./bin/myapp
```

![build_curl.go](img/build.go.curl.png)

Ответы `curl` совпадают с предыдущим шагом.

## Структура проекта

'''bash

![structure.go](img/structure.png)
