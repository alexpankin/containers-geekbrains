1. В репозитории есть main.go файл для нашего приложения
2. За базовый образ можете взять golang:1.12.0-alpine3.9, но это не обязательно
3. Порт уже прописан в приложении, обратите на это внимание, когда будете делать проксирование в контейнер
4. Далее давайте сведём всё построение нашего Dockerfile примерно к одному стандарту:

   - в контейнере нужно создать папку /app
   - скопировать в /app наше приложение (можно всю текущую директорию)
   - назначить эту директорию рабочей (текущей)
   - скачать модуль download (go mod download)
   - собрать наше приложение (go build -o main)
   - точкой запуска, соответственно будет /app/main

5. После успешного билда образа, ставим на него тэг ваш_юзернейм/mygoapp
6. Загружаем наш образ в докерхаб
7. Запустить контейнер из образа, чтобы он отвечал на локальном порту 8888, работал в фоновом режиме
8. Докерфайл и все команды которые выполняли (можно скрины) загружайте в домашнее задание
