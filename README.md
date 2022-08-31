# FieryLedLamp
Текущая версия / Current version : FieryLedLamp_v3.2_IR 107 эффектов 

  - Добавлено управление инфракрасным пультом. Возможно использование двух разных пультов одновременно. Коды пультов прописываются в файле IR_Remote.h
  Работает автоповтор при удерживании кнопки для тех команд, где это уместно. На дисплее отображается номер эффекта, при переключении эффектов,
  или значение яркости, скорости, масштаба, громкости, при их смене пультом.
  - Реструктуризированная EEPROM.
  - Возможно использование библиотеки ArduinoJson как 5-й, так и 6-й версий. В файле Constants необходимо закомментировать и разкомментировать соответствующий блок функций. По умолчанию используется 6 версия.
  – Как всегда, исправлено несколько ошибок.

# Внимание!!! ИЗМЕНЕНО ПОДКЛЮЧЕНИЕ КНОПКИ И МАТРИЦЫ!!! По умолчанию матрица в этой прошивке подключается на D3. Кнопка питается от 3.3 вольта.
# Внимательно смотрите схему подключения. Или в файле constant.h измените #define LED_PIN (0U) на #define LED_PIN (2U).

Распакуйте содержимое архива в корневую папку на диске (не на рабочий стол, пожалуйста)
и делайте всё так же, как показал Алекс Гайвер в своём видео https://youtu.be/771-Okf0dYs?t=525. Отличие от видео - матрицу подключаем к D3 и кнопку питаем от 3,3 вольта.
В архиве есть файл "ПРОЧТИ МЕНЯ!!.doc. Его нужно внимательно прочитать. Для загрузки файлов из папки data в файловую систему контролера нужно установить Uploader. Видео https://esp8266-arduinoide.ru/esp8266fs/
Версию платы в "Менеджере плат" выбирайте 2.7.4. При первом запуске лампа создаст свою WiFi сеть с именем LedLamp пароль у этой сети при первом запуске будет 31415926. После подключения к сети LedLamp наберите в браузере 192.168.4.1 и зайдите на web страницу лампы. Там можно изменить имя лампы (если их несколько в сети), навтроить подключение к Вашей домашней WiFi сети часовой пояс и переход на летнее время. Так же можно сменить пароль точки доступа (рекомендуется) и имя точки доступа. Перезагрузить лампу.
Все настройки прошивки находятся на вкладке Constants.h (там по-русски, без проблем разберётесь) и в файле data/config.json (там можно ничего не менять, всё меняется потом с web страницы лампы). Но если хотите, чтобы лампа сразу подключилась к Вашей WiFi сети, введите в файле data/cofig.json в поля "ssid": и "password": имя и пароль Вашей WiFi сети, соответственно. Поле "ESP_mode": измените с 0 на 1. Сохраните файл на то же место и сделайте upload файловой системы. Лампа сразу подключется к Вашей сети. остальные настройки можно сделать со странички лампы.

Тем, у кого лампа уже собрана и нет возможности (или сложно) добраться до разъёма для перепрошивки, можно прошиться по ОТА. Для этого нужно использовать WEB_Updater.  В папке есть файл Readme.txt. Внимательно его прочитайте

В данной прошивке режим работы ESP_MODE 1 (с роутером) или ESP_MODE 0 (без (точка доступа)) .
В любой момент его можно будет поменять, либо он сам изменится.

Обсуждение исходного и этого проектов тут: https://community.alexgyver.ru/threads/wifi-lampa-budilnik-obsuzhdenie-proshivki-fieryledlamp-ot-alvikskor.7223/page-17
