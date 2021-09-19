# TP_HL_Course_Work
Проектирование веб-сервиса HighLoad (третий семестр)

# Instagram
# MVP
1. Авторизация/регистрация
2. Публикация фотографий
3. Просмотр ленты
4. Лайки/комментарии

# 1. Целевая аудитория
- 1 млрд. людей использует Instagram ежемесячно
- 63% (630 млн.) пользователей Instagram заходят в сеть, по крайней мере, один раз в день. 42% (420 млн.) делают это несколько раз в день. 
- 95 млн. публикаций фотографий в день
- Местоположение подавляющего большинства целевой аудитории: 
  - Северная Америка 
    - США ~ 120 млн./месяц
    -  Мексика ~ 22 млн./месяц
  - Евразия 
    - Индия ~ 75 млн./месяц
    - Индонезия ~ 62 млн./месяц
    - Турция ~ 38 млн./месяц
    - Россия ~ 37 млн./месяц
    - Япония ~ 27 млн./месяц
    - Великобритания ~ 24 млн./месяц
    - Германия ~ 20 млн./месяц
  - Южная Америка 
    - Бразилия ~ 69 млн./месяц

# 2. Расчет нагрузки
## Продуктовые метрики
Из анализа целевой аудитории делается вывод, что:
- 1 млрд. - месячная аудитория сервиса
- Примерно на пользователя приходится ~ 100 фотографий. Данные были взяты из анализа количества фотографий своих подписчиков в Instagram.
- Опубликовав фото с размером 559 Кб. Затем сохранил эту фотографию из Instagram с размером 158 Кб. Фотография уменьшила свой размер в 3,5 раза. => Средний размер хранилища пользователя примерно равен 15,4 Мб. (Если брать примерный размер фото в 158 Кб.)
- Среднее количество действий пользователя по типам в день:
  - Возьмем 420 млн. активных пользователей в день. Делим на 95 млн. публикаций в день. Получим ~ 4 фотографии пользователь публикует в день.
  - 4.2 млрд. лайков ежедневно. Возьмем 630 млн. активных пользователей в день, кто оставляет лайк. Получим ~ 6 лайков в день на одного пользователя.
  - Предположим, что комментариев оставляют в 100 раз реже, чем лаки. ~ 42 млн. комментариев в день. Возьмем 420 млн. активных пользователей в день. Получим ~ 0,1 комментариев в день на одного пользователя.
  - 347 тыс. скороллов ленты в минуту. Один скролл = 1 фотографии. 500 млн публикаций в день. Возьмем 420 млн. активных пользователей в день. И получим ~ 1,2 просмотров фотографий в день пользователем.
- По статистике за 2019 год число пользователей составляло 1,2 млрд., за 2020 год цифра составила 1,5 млрд. За год прирост на 300 млн. новых пользователей. Получим ~ 821 тыс. новых пользователей в день. Число повторных авторизаций примерно поделим в 3 раза. Получим ~ 273 тыс.

## Технические метрики
- Если предположить, что аудитория 1,5 млрд. и ~ 100 фотографий на каждом профиле, то получаем 21,5 Пб.
- Сетевой трафик:
  - Существенным типом трафика является загрузка фотографий. Фотография уже отправляется в ужатом состояние. 95 млн. фото на 158 Кб. за день => Передаётся ~ 168 Мб/с
  - Существенным типом трафика является получение фотографий. 500 млн. за день => Передаётся ~ 871 Мб/с

- RPS:
  - Публикация фото: 95 млн. в день => 1100 RPS
  - Лайки: 4.2 млрд. в день => 48600 RPS
  - Комментарии: 42 млн. в день => 486 RPS
  - Просмотр ленты: 500 млн. в день => 5787 RPS
  - Регистрация: 821 тыс. в день => 10 RPS
  - Авторизация: 273 тыс. в день => 3 RPS
