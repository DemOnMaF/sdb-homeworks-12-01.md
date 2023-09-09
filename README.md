# `Домашнее задание к занятию «Кеширование Redis/memcached»`

# **Задание 1 Приведите примеры проблем, которые может решить кеширование.**

Кэширование может увеличивать производительность и быстроту ответа за счёт использования сохранённых ранее данных в кеше, и при очередном обращении клиента за одними и теми же данными, сервер может обслуживать запросы в разы быстрее, тк при перой выдаче ответа по запросу - он сохраняется в кэш. Кэширование так же помогает снизить нагрузку на сервер, сеть и СУБД, поскольку получив единожды данные - хранит их указанный период времени и при повторном запросе не нагружает основное хранилище. Кэширование БД улучшает масштабируемость за счет распределения рабочей нагрузки по запросам с серверной части на несколько дешевых интерфейсных систем - что даёт гибкость в обработке данных, + доступность данных, обеспечивая непрерывное обслуживание приложений, которые зависят от кэшированных таблиц при возможной недоступности серверов.

# **Задание 2 Установите и запустите memcached.**


# **Задание 3 Удаление по TTL в Memcached**


# **Задание 4 Запись данных в Redis**



