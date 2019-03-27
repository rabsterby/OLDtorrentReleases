# torrentReleases
Следим за качественными цифровыми релизами фильмов без суеты

mkdir -p /home/movies
wget --no-check-certificate -O /home/movies/digitalreleases.py https://raw.githubusercontent.com/Kyrie1965/torrentReleases/master/digitalreleases.py


Добавление задания в cron

Добавим в cron задачу, которая каждый день в 6 утра будет запускать digitalreleases.py и генерировать актуальный файл с релизами.

Откройте в редакторе файл crontab:

crontab -e

Добавьте в конце (замените root на admin в зависимости от вашего устройства):

00 06 * * *  python3 /home/movies/digitalreleases.py > /home/movies/log.txt 2>&1

Финальная настройка

Запустите программу вручную в первый раз, чтобы она сгенерировала файл /var/www/releases.html:

python3 /home/movies/digitalreleases.py

Полное описание с подробностями читайте по ссылке:
https://habr.com/ru/post/443584/
