---
index: 16
title: Signal для Android
---
Signal для Android
==============================
Безопасные сообщения

**Урок для чтения: [Отправка сообщений](umbrella://communications/sending-a-message)**  
**Уровень**: Начальный-Средний  
**Необходимое время**: 15-20 минут  
**Опубликовано:** Апрель 2018 (некоторые изображения датируются более ранними версиями)  
**Источники:** EFF, Самозащита от слежки [Как: использовать сигнал для Android](https://ssd.eff.org/en/module/how-use-signal-android); Безопасность-в-коробке [SIGNAL ДЛЯ  ANDROID](https://securityinabox.org/en/guide/signal/android/).  

**Использование Signal даст вам:**

- Возможность отправлять зашифрованные сквозным методом групповые, текстовые, графические и видео сообщения, а также производить зашифрованные телефонные звонки с другими пользователями Signal.

**Местоположение загрузки**: [Google Play](https://play.google.com/store/apps/details?id=org.thoughtcrime.securesms).

**Системные требования**: Android 2.3 и выше, с Google Play Services (вам необходимо иметь учетную запись Google, которая будет связана с установкой приложения).

**Версия, используемая в этом руководстве**: Signal 3.31.3

**Лицензия:** GPLv3

**Дополнительные материалы**:

*   [http://support.whispersystems.org/](http://support.whispersystems.org/)
*   [https://signal.org/blog/standalone-signal-desktop/](https://signal.org/blog/standalone-signal-desktop/)
*   [https://whispersystems.org/blog/signal-video-calls/](https://whispersystems.org/blog/signal-video-calls/)


## Введение

Signal - это бесплатное программное обеспечение с открытым исходным кодом для Android, iOS и настольного компьютера, которое использует сквозное шифрование, позволяя пользователям отправлять зашифрованные сквозным методом групповые, текстовые, графические и видео сообщения, а также производить зашифрованные телефонные разговоры между пользователями Signal.

Хотя Signal использует телефонные номера в качестве контактов, зашифрованные звонки и сообщения фактически используют ваше подключение для передачи данных; поэтому обе стороны разговора должны иметь доступ к Интернету на своих мобильных устройствах. В связи с этим пользователи Signal не несут платы за SMS и MMS за подобные разговоры.

В Android Signal может заменить приложение для обмена текстовыми сообщениями по умолчанию, поэтому в Signal все еще можно отправлять незашифрованные SMS-сообщения.

Примечание:
* Signal запрещает другим лицам доступ к содержимому ваших сообщений и голосовых вызовов, но он не скрывает тот факт, что вы отправляете зашифрованные сообщения или совершаете зашифрованные голосовые вызовы. В некоторых странах такие инструменты шифрования, как Signal, могут привлечь внимание или нарушить закон.
* Open Whisper Systems, создатели Signal, используют инфраструктуру других компаний (Google на Android), чтобы отправлять своим пользователям оповещения, когда они получают новое сообщение. Это означает, что некоторые метаданные или информация о том, кто получает сообщения и когда они были получены, могут утекать в эти компании.

## Установка Signal на ваш телефон Android 

### Шаг 1: Загрузка и установка Signal 

На вашем Android-устройстве войдите в Google Play и выполните поиск «Signal». Выберите [Signal от Open Whisper Systems](https://play.google.com/store/apps/details?id=org.thoughtcrime.securesms). ,

После того, как вы нажмете «Установить», вы увидите список функций Android, к которым у Signal должен быть доступ, чтобы они могли работать. Нажмите «Принять».

После завершения загрузки Signal нажмите «Открыть», чтобы запустить приложение.

### Шаг 2: Зарегистрируйтесь и подтвердите свой номер телефона

Теперь вы увидите следующий экран. Введите номер своего мобильного телефона и нажмите «Зарегистрироваться».

![](tool_signalandroid_resized000_0.png)

Вам будет предложено подтвердить свой номер телефона. Нажмите «Продолжить».

![](tool_signalandroid_resized001_0.png)

Чтобы подтвердить свой номер телефона, вам будет отправлено SMS-сообщение с шестизначным кодом. Поскольку Signal может получить доступ к вашим текстовым сообщениям SMS, он автоматически распознает, когда вы получили код, и завершит регистрацию.

![](tool_signalandroid_resized002_0.png)

После завершения этого процесса вас спросят, хотите ли вы, чтобы Signal был вашим приложением для SMS по умолчанию. Это может быть полезно для хранения всех ваших сообщений в одном месте. Имейте в виду, что если вы примете это, сообщения, отправленные контактам, на которых не установлен Signal (даже если вы отправляете их из приложения Signal ), не будут зашифрованы.

## Использование Signal

Чтобы использовать Signal, у человека, которому вы звоните, должен быть установлен Signal. Если вы попытаетесь отправить сообщение кому-либо, используя приложение Signal, но у него не установлено такое приложение , Signal отправит стандартное незашифрованное текстовое сообщение. Если вы попытаетесь позвонить этому человеку, Signal сделает стандартный звонок.

Signal предоставляет вам список других пользователей Signal в ваших контактах. Для этого данные, представляющие номера телефонов в вашем списке контактов, загружаются на серверы Signal, хотя эти данные удаляются практически сразу.

### Как отправить зашифрованное сообщение

Нажмите на значок карандаша в правом нижнем углу экрана.

![](tool_signalandroid_resized003_0.png)

Вы увидите список всех зарегистрированных пользователей Signal в ваших контактах. Вы также можете ввести номер телефона пользователя Signal, которого нет в ваших контактах. При выборе контакта вы попадете на экран обмена текстовыми сообщениями для своего контакта. Обратите внимание, что для пользователей Signal вы увидите текст «Отправить сообщение Signal» - это означает, что сообщение будет зашифровано. На этом экране значок «телефон» в правом верхнем углу экрана будет показывать, что вы можете сделать зашифрованный голосовой вызов также с помощью Signal. С этого экрана вы можете отправлять зашифрованные сквозным методом текстовые, графические или видео сообщения.

![](tool_signalandroid_resized006.png)

Для пользователей, у которых не установлен Signal, вы увидите текст «Отправить незащищенное SMS», который не будет отправлять сообщение с шифрованием. На этом экране значок «телефон» в верхнем правом углу экрана будет выполнять обычный незашифрованный телефонный звонок.

![](tool_signalandroid_resized004_0.png)

### Как инициировать зашифрованный звонок

Чтобы начать зашифрованный звонок контакту, выберите этот контакт, а затем нажмите на значок телефона. Вы узнаете, что контакт может принимать вызовы Signal, если рядом со значком телефона вы увидите маленький значок замка.

![](tool_signalandroid_resized006-1.png)

Как только вы начали вызов - он уже зашифрован.

### Как инициировать зашифрованный видеозвонок

Чтобы сделать зашифрованный видеозвонок, просто позвоните кому-нибудь, как описано выше:

![](tool_signalandroid_initial_video_screen.png)

и коснитесь значка видеокамеры. Возможно, вам придется разрешить Signal доступ к видео с вашей камеры. Это покажет вас по видео вашему другу (ваш друг может сделать то же самое).

### Как начать зашифрованный групповой чат

Вы можете отправить зашифрованное групповое сообщение, нажав на значок дополнения (три точки в правом верхнем углу экрана) и выбрав «Новая группа».

![](tool_signalandroid_resized020_0.png)

На следующем экране вы сможете назвать группу и добавить в нее участников.

![](tool_signalandroid_resized021_0.png)

![](tool_signalandroid_resized016_0.png)

После добавления участников вы можете нажать на галочку в правом верхнем углу экрана. Это инициирует групповой чат.

![](tool_signalandroid_resized019_0.png)

Если вы хотите изменить значок группы, добавить или удалить участников, это можно сделать на экране группового чата, нажав значок дополнения (три точки в верхнем правом углу экрана) и выбрав «Обновить группу».

### Бесшумные беседы

Иногда разговоры могут отвлекать. Одной из функций, которая особенно полезна для групповых чатов, является отключение уведомлений, поэтому вы не увидите новое уведомление каждый раз, когда приходит новое сообщение. Это можно сделать на экране группового чата, коснувшись значка дополнения (три точки в верхнем правом углу экрана) и выбрав «Отключить уведомления». Затем вы можете выбрать, как долго вы хотите, чтобы отключение звука было активным. Это может быть применено и к отдельным разговорам, если это необходимо.

### Как верифицировать ваши контакты

На этом этапе вы можете проверить подлинность собеседника, чтобы убедиться, что его ключ шифрования не был подделан или заменен на ключ другого человека, когда ваше приложение загрузило его (процесс, называемый проверкой ключа). Проверка - это процесс, который происходит, когда вы находитесь в присутствии человека, с которым разговариваете.

Сначала откройте экран, на котором вы можете писать своему контакту, как описано выше. На этом экране нажмите значок дополнения (три точки в правом верхнем углу экрана) и выберите «Настройки разговора».

![](tool_signalandroid_resized010_0.png)

На следующем экране нажмите «Проверить номера безопасности».

![](tool_signalandroid_resized011_0.png)

Теперь вы попадете на экран, на котором отображается QR-код и список «номеров безопасности». Этот код будет уникальным для каждого контакта, с которым вы общаетесь. Пусть ваш контакт перейдет на соответствующий экран для разговора с вами, чтобы на его экране также отображался QR-код.

![](tool_signalandroid_resized012_0.png)

Вернувшись на свое устройство, вы можете нажать на свой QR-код, который будет использовать камеру для сканирования QR-кода, отображаемого на экране вашего контакта. Совместите камеру с QR-кодом:

![](tool_signalandroid_resized014.png)

Надеемся, что ваша камера отсканирует штрих-код и отобразит галочку, например:

![](tool_signalandroid_resized015.png)

Это означает, что вы успешно подтвердили свой контакт. Если вместо этого ваш экран выглядит следующим образом, что-то пошло не так:

![](tool_signalandroid_resized013.png)

Возможно, вы захотите избегать обсуждения деликатных тем, пока не подтвердите ключи с этим человеком.

*Примечание для опытных пользователей: на экране, отображающем ваш QR-код, также есть значок, указывающий ваш номер безопасности в правом верхнем углу. Персональная проверка является предпочтительным методом, но вы, возможно, уже подтвердили подлинность своего контакта, используя другое безопасное приложение, такое как PGP. Поскольку вы уже проверили свой контакт, вы можете безопасно использовать доверие, установленное в этом приложении, для проверки номеров безопасности в Сигнале, без необходимости физического присутствия в присутствии вашего контакта. В этом случае вы можете поделиться своим номером безопасности с этим приложением, нажав значок «Поделиться», и отправить своему контактному лицу свой номер безопасности.*

### Исчезающие сообщения

Signal имеет функцию, называемую исчезающими сообщениями, которая гарантирует, что сообщения будут удалены с вашего устройства и устройства вашего контакта через некоторое выбранное количество времени после их просмотра. Чтобы разрешить исчезновение сообщений для разговора, откройте экран, на котором вы можете писать своему контакту. На этом экране нажмите значок дополнения (три точки в верхнем правом углу экрана) и выберите «Исчезающие сообщения».

![](tool_signalandroid_resized022_0.png)

Появится новый экран, который позволяет выбрать, как быстро исчезнут сообщения:

![](tool_signalandroid_resized009.png)

После выбора параметра вы должны увидеть в беседе информацию о том, что «исчезающие сообщения» включены.

![](tool_signalandroid_resized008_0.png)

Теперь вы можете отправлять сообщения с гарантией того, что они будут удалены через указанное количество времени.
