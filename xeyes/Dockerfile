# Используем образ Ubuntu как основу для нашего контейнера
FROM ubuntu:latest

# Выполняем обновление пакетов и устанавливаем программы для работы с графическим интерфейсом
RUN apt-get update && apt-get install -y \
    # Утилиты для запуска графических приложений, включая xeyes
    x11-apps \
    # Средство для управления аутентификацией X-серверов
    xauth \
    # Очистка кеша пакетов для уменьшения размера образа
    && rm -rf /var/lib/apt/lists/*

# Настраиваем переменную среды DISPLAY для указания, куда отправлять графику
# host.docker.internal указывает на хост-машину, а :0 — на главный дисплей X-сервера
ENV DISPLAY=host.docker.internal:0

# Устанавливаем рабочую директорию, где будет запущено приложение
WORKDIR /app 

# Команда по умолчанию для запуска контейнера
# Здесь запускается xeyes для отображения графического окна
CMD ["xeyes"]
