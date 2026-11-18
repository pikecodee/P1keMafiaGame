# P1keMafiaGame
Прочтите README!

[RU]
MafiaPlugin
Плагин «Мафия» для Paper-серверов с интеграцией LuckPerms. Реализует полноценный игровой цикл: лобби с отсчётом, случайную раздачу ролей через группы LuckPerms, ночные действия (убийство мафией, лечение доктором, проверка шерифом, блокировка голоса путаной), дневное голосование с возможностью пропуска, автоматическое определение победы с фейерверками и звуком дракона. Роли: Mafia, Doctor, Putana, Sherif, Villager — выдаются автоматически, права группам нужно настроить один раз в LuckPerms. Команды: /mafia, /join, /ss, /s, /d, /n, /vt, /vs, /mh, /rep, /v, /vskip, /m, /k, /heal, /ch, /fuck. Права: maf.admin, maf.all, maf.mafia, maf.doctor, maf.sherif, maf.putana. Конфигурация задаёт координаты дневной точки, ночных домов и параметры лобби (минимум/максимум игроков, длительность отсчёта).

Сводная таблица команд
Команда	Описание	Право	Кому доступна
/mafia	Запускает лобби игры, рассылает приглашение в чат	maf.admin	Админ
/join	Присоединиться к игре в лобби	maf.all	Все
/ss	Принудительный старт игры (даже без минимума игроков)	maf.admin	Админ
/s	Принудительно остановить игру	maf.admin	Админ
/d	Начать день, телепорт на day-spawn	maf.admin	Админ
/n	Начать ночь, телепорт по домам из конфига	maf.admin	Админ
/vt	Открыть дневное голосование	maf.admin	Админ
/vs	Остановить голосование и подсчитать голоса	maf.admin	Админ
/mh	Показать правила и список команд	maf.all	Все
/rep <текст>	Репорт администрации (только OP)	maf.all	Все
/v <ник>	Проголосовать против игрока днём	maf.all	Все
/vskip	Пропустить голосование (если >50% живых)	maf.all	Все
/m <текст>	Чат мафии (видят только мафии)	maf.mafia	Мафия
/k <ник>	Выбрать жертву убийства ночью	maf.mafia	Мафия
/heal <ник>	Исцелить убитого мафией	maf.doctor	Доктор
/ch <ник>	Проверить игрока (+ не мафия, - мафия)	maf.sherif	Шериф
/fuck <ник>	«Отработать» — блокирует следующий голос цели	maf.putana	Путана

Права (permissions)
Право	                  Описание	                                  Default
maf.admin	       Все административные команды	                        op
maf.all	         Базовые команды (join, mh, rep, v, vskip)	         true
maf.mafia	          Команды мафии (/m, /k)	                         false
maf.doctor	         Команды доктора (/heal)	                       false
maf.sherif	          Команды шерифа (/ch)	                         false
maf.putana	          Команды путаны (/fuck)	                       false

Группы LuckPerms и их настройка
Плагин при раздаче ролей автоматически добавляет игроков в группы с именами строго Mafia, Doctor, Putana, Sherif, Villager. Регистр важен. Группу Sherif создавайте без второй f
Выполните эти команды один раз в консоли сервера или от имени админа в игре:

/lp creategroup Mafia
/lp creategroup Doctor
/lp creategroup Putana
/lp creategroup Sherif
/lp creategroup Villager

/lp group Mafia    permission set maf.mafia  true
/lp group Doctor   permission set maf.doctor true
/lp group Putana   permission set maf.putana true
/lp group Sherif   permission set maf.sherif true
/lp group Villager permission set maf.all    true



[EN] 


MafiaPlugin
A "Mafia" plugin for Paper servers with LuckPerms integration. It implements a complete game loop: a lobby with a countdown, random role assignment via LuckPerms groups, night actions (mafia kill, doctor heal, sheriff check, putana vote-block), daytime voting with a skip option, and automatic win detection with fireworks and the ender dragon sound. Roles: Mafia, Doctor, Putana, Sherif, Villager — assigned automatically; the permissions for these groups need to be configured once in LuckPerms. Commands: /mafia, /join, /ss, /s, /d, /n, /vt, /vs, /mh, /rep, /v, /vskip, /m, /k, /heal, /ch, /fuck. Permissions: maf.admin, maf.all, maf.mafia, maf.doctor, maf.sherif, maf.putana. The configuration defines the daytime spawn coordinates, night house coordinates, and lobby parameters (minimum/maximum players, countdown duration).

Command Reference
Command	Description	Permission	Available to
/mafia	Starts the game lobby and broadcasts an invitation to chat	maf.admin	Admin
/join	Joins the game lobby	maf.all	Everyone
/ss	Force-starts the game (even without the minimum number of players)	maf.admin	Admin
/s	Force-stops the game	maf.admin	Admin
/d	Starts the day, teleports to day-spawn	maf.admin	Admin
/n	Starts the night, teleports players to houses from the config	maf.admin	Admin
/vt	Opens daytime voting	maf.admin	Admin
/vs	Stops voting and tallies the votes	maf.admin	Admin
/mh	Shows the rules and command list	maf.all	Everyone
/rep <text>	Sends a report to the administration (OP only)	maf.all	Everyone
/v <nick>	Votes against a player during the day	maf.all	Everyone
/vskip	Skips voting (if more than 50% of alive players agree)	maf.all	Everyone
/m <text>	Mafia chat (visible only to mafia members)	maf.mafia	Mafia
/k <nick>	Selects a kill target at night	maf.mafia	Mafia
/heal <nick>	Heals a player killed by the mafia	maf.doctor	Doctor
/ch <nick>	Checks a player (+ not mafia, - mafia)	maf.sherif	Sheriff
/fuck <nick>	"Works" — blocks the target's next vote	maf.putana	Putana
Permissions
Permission	Description	Default
maf.admin	All administrative commands	op
maf.all	Basic commands (join, mh, rep, v, vskip)	true
maf.mafia	Mafia commands (/m, /k)	false
maf.doctor	Doctor commands (/heal)	false
maf.sherif	Sheriff commands (/ch)	false
maf.putana	Putana commands (/fuck)	false
LuckPerms Groups and Setup
When assigning roles, the plugin automatically adds players to groups named strictly Mafia, Doctor, Putana, Sherif, Villager. Case matters. Create the Sherif group without the second f.

Run these commands once in the server console or as an admin in-game:

text
/lp creategroup Mafia
/lp creategroup Doctor
/lp creategroup Putana
/lp creategroup Sherif
/lp creategroup Villager

/lp group Mafia    permission set maf.mafia  true
/lp group Doctor   permission set maf.doctor true
/lp group Putana   permission set maf.putana true
/lp group Sherif   permission set maf.sherif true
/lp group Villager permission set maf.all    true
A couple of notes for the GitHub version: the phrase «Отработать» in the /fuck row is a euphemism that doesn't translate cleanly — I rendered it as "Works" in quotes, but you may prefer "Provides services" or keep the original Russian term if your audience understands it. Also, the Sherif group name is intentionally misspelled (missing the second f) because that's exactly what the code expects — I kept that note in the translation so contributors don't "fix" it and break the plugin.
