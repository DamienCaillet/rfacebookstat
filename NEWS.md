# rfacebookstat 2.2.3.9000

Дата релиза: 2021-01-06

* Добавил в результат возвращаемый функцией `fbGetAdCreative()` поле `image_url`.

# rfacebookstat 2.2.2

Дата релиза: 2021-01-04

Мелкие правки ссылок в документации для публикации новой версии пакета на CRAN.

# rfacebookstat 2.2.1

Дата релиза: 2020-12-28

* Исправлена ошибка атрибута interval в функции `fbGetMarketingStat()`, ранее он просто игнорировался, и отдавал результат по дням.
* Пакет переведён на работу с API v9.0
* В функцию `fbGetMarketingStat()` добавлен аргумент `fetch_by`, который позволяет разбить запрос а длительный период на подзапросы по неделе, месяцу, кварталу, году и так далее.

Видео обзор релиза: https://youtu.be/ZN9-aYqq2tQ

# rfacebookstat 2.2.0

Дата релиза: 2020-09-23

* В пакет добавлена функция `fbGetBusinessManagersUsers()`, которая позволяет запросить список пользователей бизнес менедрежа Facebook.

# rfacebookstat 2.1.9

Дата релиза: 2020-09-24

* Значительное ускорение функции `fbGetMarketingStat()`, ранее при запросе данных в разбивке по дням, функция отправляла на каждый день новый запрос, с версии 2.1.9 данные за весь период будут запрашиваться в одном запросе, если в результате вы получите более 5000 строк то будет запущен постраничный сбор данных, который в любом случае будет значительно быстрее чем, запрос данных отдельно за каждый день.
* В функцию добавлен `fbGetMarketingStat()` добавлен аргумент `date_preset`, с помощью которого можно задавать условный временной диапазон. Возможные значения: today, yesterday, this_month, last_month, this_quarter, lifetime, last_3d, last_7d, last_14d, last_28d, last_30d, last_90d, last_week_mon_sun, last_week_sun_sat, last_quarter, last_year, this_week_mon_today, this_week_sun_today, this_year.
* В функцию добавлен `fbGetMarketingStat()` добавлен аргумент `use_account_attribution_setting`. Если для этого параметра установлено значение true, результаты ваших объявлений будут отображаться с использованием настроек атрибуции, определенных для рекламного аккаунта.
* В результат возвращаемый функцией `fbGetAdAccounts()` добавлено поле created_time, в котором хранится дата и время создания аккаунта.


# rfacebookstat 2.1.8

Дата релиза: 2020-08-27

* В результат возвращаемый функцией `fbGetCampaings()`, добавлена полz start_time и stop_time.

# rfacebookstat 2.1.7

Дата релиза: 2020-08-27

* Исправлены ссылки в документации
* Ещё сильнее снижен лимит на количество объектов запрашиваемыхв одном запросе в функции `fbGetAdCreative()`, теперь за раз функция запрашивает всего 250 креативов, связано с ошибкой `Please reduce the amount of data you're asking for, then retry your request`.


# rfacebookstat 2.1.6

Дата релиза: 2020-08-26

* В функциях `fbGetAds()`, `fbGetAdCreative()`, `fbGetCampaings()`, `fbGetAdSets()` изменил повоедение при ошибках обращения к API, теперь данные функции в случае ошибки, будут остановлены с ошибкой, а не просто выведут уведомление.

# rfacebookstat 2.1.5

Дата релиза: 2020-08-21

* Пакет переведён на работу с Facebook Marketing API версией v8.0.
* Ещё сильнее урезал лимит на 1 запрос по количеству креативов получаемых с помощью функции `fbGetAdCreative()`, т.к. всё равно на больших аккаунтах возникала ошибка.

# rfacebookstat 2.1.4

Дата релиза: 2020-08-05

* Исправил ошибку, которая возникала при автоматическом обновлении токена `Error: object 'st_token' not found`.

# rfacebookstat 2.1.3

Дата релиза: 2020-07-17

* Исправление в технической функции `fbAction()`, теперь она корректно парсит поле video_thruplay_watched_actions.

# rfacebookstat 2.1.2

Дата релиза: 2020-06-12

* Исправление функции `fbGetAdCreative()`, ранее возникала ошибка ели в аккаунте более 1000 креативов.

# rfacebookstat 2.1.1

Дата релиза: 2020-05-29

* Исправление функции `fbGetCostData()`.

# rfacebookstat 2.1.0

Дата релиза: 2020-05-26

* В пакет добавлена функция `fbGetCostData()`, которая запрашивает и преобразует данные о расходах на facebook, для загрузки в Google Analytics.
* Миграция на API v.7.0

# rfacebookstat 2.0.3

Дата релиза: 2020-05-06

Исправлена ошибка в функции `fbGetAdCreative()`, ранее не парсились ссылки, хеши миниатюр и сообщения в видео креативах. 
Также в результат возвращаемый данной функцией добавлены поляЖ

* object_type - Тип объекта
* video_id - Идентификатор видео

# rfacebookstat 2.0.2

Дата релиза: 2020-03-24

Исправлены некоторые проблемы которые возникали у пользоваталей при авторизации через стандартное приложение.

Добавлена скритая функция `fbRevokeAppPrivilegies()`, с помощью которой вы можете отозвать выданные приложению разрешения.

# rfacebookstat 2.0.1

Дата релиза: 2020-02-07

Пакет переведён на работу с API версии v6.0. Фактически на стороне Facebook Marketing API никаких изменений не было, единственное, что изменилось это значение опции *rfacebookstat.api_version* по умолчанию.


# rfacebookstat 2.0.0

Дата релиза: 2019-12-17

* Новые функции
    * `fbAuth()` - Новая функция авторизации, подробности в разеле **Авторизация**.
    * `fbGetUserAdAccounts()` - Загрузка списка аккаунтов к которым есть доступ у определённого пользователя facebook.
	* `fbGetAdAccountsConversions()` - Получить список конвесий настроенных в рекламной аккаунте.
	* `fbGetAdVideos()` - Загрузка списка видео из рекламного аккаунта
	* `fbGetSettings()` - Вывести в консоль все применённые в пакете настройки.

* Доработанные функции
    * В функцию `fbGetMarketingStat()` добавлен аргумент *attribution_window* с помощью которого вы можете запрашивать поле *actions* и применять к нему различные окна атрибуции.
    * Так же был полностью переписан процесс разворачивания вложенных полей типа *actions*, и прочих. Теперь функция `fbGetMarketingStat()` работает с ними более стабильно.
	* Изменения в функциях `fbGetApps()` и `fbGetPages()` теперь вы можете запрашивать список продвигаемых страниц и приложений непосредственно из рекламных аккаунтов. 
	    * Теперь вы можете запрашивать список страниц и приложений из конкретного аккаунта, используя аргумент *accounts_id*. Это новый аргумент который был добавлен вместо устаревшего *projects_id*.
		* В обеих функциях значительно расширен список полей которые они возвращают.
	* В большинстве функций аргумент *accounts_id* больше не является обязательным, и по умолчанию запрашивает данные по всем рекламным аккаунтам к которым у вас есть доступ, эта доработка коснулась следующих функций:
	    * `fbGetCampaigns()`
		* `fbGetAdSets()`
		* `fbGetAds()`
		* `fbGetAdCreative()`
		* `fbGetApps()`
		* `fbGetPages()`
		* `fbGetAdAccountUsersPermissions()`
		* `fbGetAdAccountUsers()`
		
* Удалённые функции
    * Из пакета полностью удалена функция `fbGetProjects()`, в связи с тем, что в Facebook больше не существует проектов.

* Авторизация
    * Был значительно улучшен процесс авторизации, теперь помимо опций вы можете использовать переменные среды.
    * Так же при авторизации начиная с версии 2.0.0 учётные данные сохраняются в локальный файл, и по умолчанию вы получаете долгосрочный токен.
	* В пакет встроено собственное приложение, теперь нет необходимости регистрировать собственное приложение и запрашивать стандартнй доступ к API, он уже по умолчанию вшит в пакет.
	
* Документация
    * В виньетку по загрузке статистики добавлена информация про окна атрибуции: `vignette('rfacebookstat-get-statistics', package = 'rfacebookstat')`
	* В пакет добавлена новая виньетка посвящённая процессу авторизации и его автоматизации:  `vignette('rfacebookstat-authorization', package = 'rfacebookstat')`
	
* Прочее
    * Пакет переведён на работу с версией API v5.0.


# rfacebookstat 1.10.0

Дата релиза: 2019-09-10

* Пакет переведён на работу с API V4.0
* Добавлена новая функция `fbGetBusinessUserAdAccounts()`, позволяющая загрузить по пользователю бизнесс менеджера список аккаунтов к которому ему предоставлен доступ.


# rfacebookstat 1.9.1

Исправлена виньетка


# rfacebookstat 1.9.0

Дата релиза: 2019-05-21

CСсылка на подробное описание релиза: [Link](https://github.com/selesnow/rfacebookstat/releases/tag/1.9.0)

## Что нового

* Новая функция `fbGetCatalogs` предназначенная для загрузки каталогов;
* Опции, для упрощения и компактности синтаксиса в пакет добавлены 4 опции
    * rfacebookstat.api_version - Версия API, по умолчанию v3.3
	* rfacebookstat.access_token - Токен доступа к API
	* rfacebookstat.accounts_id - ID рекламного аккаунта
	* rfacebookstat.business_id - ID бизнес менеджера
* Упрощённый формат фильтрации данных, пример `"impressions LESS_THAN 5000"`;
* Исправлена ошибка возникающая при загрузке action и применения action_breakdowns;
* В пакет добавлена виньетка посвящённая загрузки статистики из рекламных аккаунтов Facebook: `vignette('rfacebookstat-get-statistics', package = 'rfacebookstat')`;
* Добавлен обработчик лимитов API;
* В результат возвращаемый функцией `fbGetAdCreative` добавлено поле *link_nested* с данными по дочерним ссылкам из кольцевой галереи.
