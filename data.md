Описание данных к Dota Science Challenge
========================================

<a href="https://yadi.sk/d/FZabPHwtpwQi6">Результаты матчей</a>

Участникам предоставляется **два** набора данных: 

## Записи прошедших матчей Shanghai Major 2016

<a href="https://yadi.sk/d/0lCsVXKZpvxGo">Cсылка для скачивания набора данных</a>

- Файл с набором данных представлен в формате построчного JSON, запакованного при помощи bzip2
- Каждая строчка файла содержит в себе информацию на какой-то момент времени в матче
- Информация о матчах в файле идет в хронологическом порядке
- Строчки НЕ сгруппированы по матчам
- Обратите внимание на этот формат, т.к. данные по текущим матчам вам будут предоставляться в том же формате!
- Каталог [`dictionaries`](./dictionaries) содержит таблицы с расшифровкой идентификаторов из набора данных (`hero_id`, `ability_id`, `item_id`...)

#### Пример чтения файла в Python

```python
import bz2
import json

with bz2.BZ2File(’shanghai_live_league_games.jsonlines.bz2’) as f: 
    for line in f:
        record = json.loads(line)
        match_id = record['match_id']
        # process record
```

#### Описание полей

```python
{
    'stream_delay_s': 300.0,                       # задержка этого момента времени в секундах
    'stage_name': '#DOTA_TournamentBracket_LBR5',  # название этапа турнира
    '_timestamp': 1457169627.0,                    # время момента в формате unix timestamp
    'spectators': 95647,                           # кол-во зрителей
    'match_id': 2199144312,                        # id матча
    'league_series_id': 20,                        
    'lobby_id': 24445155709587003,                 # id лобби
    'game_number': 2,                              # номер игры в серии
    'league_id': 4266,                             # id турнира или лиги
    'scoreboard': {
        'duration': 1975.660278,                   # длительность матча в секундах
        'radiant': {
            'abilities': [                         # способности команды
                {
                    'ability_id': 5357,            # id способности  
                    'ability_level': 4             # уровень способности
                },
                ...
            ],
            'bans': [                              # баны команды в хронологическом порядке
                {
                   'hero_id': 53                   # id забаненого героя
                },
                ...
            ],
            'barracks_state': 63,                  # состояние бараков (см. битовую маску)
            'picks': [                             # пики команды в хронологическом порядке
                {
                    'hero_id': 107                 # id забаненого героя
                },
                ...
            ],
            'players': [                           # информация об игроках команды
                {
                    'gold': 759,                   # текущее золото игрока
                    'position_x': 2390.372314,     # координата x
                    'position_y': 3045.073975,     # координата y
                    'last_hits': 43,               # число добитых вражеских крипов
                    'account_id': 86727555,        # id пользователя
                    'denies': 1,                   # число добитых дружеских крипов
                    'ultimate_state': 1,           # состояние улютимативной способности (1 - способность доступна)
                    'ultimate_cooldown': 47,       # 
                    'death': 2,                    # кол-во смертей
                    'item2': 30,                   # id предмета в слоте
                    'item3': 73, 
                    'item0': 214, 
                    'item1': 102, 
                    'item4': 30, 
                    'item5': 36, 
                    'hero_id': 5,                  # id героя, за которого играет игрок
                    'xp_per_min': 283,             # средний получаемый игроком опыт в минуту
                    'player_slot': 1,              
                    'kills': 2,                    # кол-во убийств, совершённых героем
                    'assists': 9,                  # кол-во раз когда игрок помогал совершать убийства
                    'gold_per_min': 250,           # среднее за минуту зарабатываемое игроком золото 
                    'level': 13,                   # уровень героя
                    'net_worth': 5899,             # стоимость героя - сумма имеющегося золота и стоимости всех предметов
                    'respawn_timer': 0             # число секунд до возрождения героя
                },
                ...
            ],
            'tower_state': 1830,                   # состояние башен (см. битовую маску)
            'score': 22,                           # сумма убийств по команде
        },
        'dire': ...,                               # аналогично radiant
        'roshan_respawn_timer':                    # секунд до возрождения рошана (местного босса)
    }, 
    'dire_team': {
        'team_name': 'MVP Phoenix', 
        'team_id': 1148284, 
        'team_logo': 486682620712187742, 
        'complete': True
    }, 
    'series_id': 20, 
    'players': [
        {
            'team': 2,               # 0 - radiant, 1 - dire, 2,3,4 - others (spectators)
            'account_id': 299613011, # id пользователя
            'name': 'DotaMajorsRU',  # имя пользователя
            'hero_id': 0             # id героя (0 для наблюдателей)
        },
        ...
    ], 
    'league_game_id': 2,
    'series_type': 1, 
    'radiant_series_wins': 1,  # число побед команды, которая играет за radiant, в серии
    'league_tier': 3, 
    'radiant_team': {},        # аналогично dire_team       
    'dire_series_wins': 0
}
```

## Реплеи матчей, в которых участвовали команды с Shanghai Major 2016
========================================

Ссылки на архивы в формате zip:
- <a href="https://yadi.sk/d/TSy7TIHopwEha">Secret</a>
- <a href="https://yadi.sk/d/Q0DT-5u2pwEoF">OG</a>
- <a href="https://yadi.sk/d/mpk-CR6XpwEqC">Ehome</a>
- <a href="https://yadi.sk/d/iL2gi9NSpwF3Q">EG</a>
- <a href="https://yadi.sk/d/aMRvlIEupwHCp">Liquid</a>
- <a href="https://yadi.sk/d/86EWNGH1pwRhu">Alliance</a>
- <a href="https://yadi.sk/d/XMLq9U2RpwRiC">Archon</a>
- <a href="https://yadi.sk/d/mRPFm6FbpwRik">CDEC</a>
- <a href="https://yadi.sk/d/Cpk6J5d0pwRjC">coL</a>
- <a href="https://yadi.sk/d/Mxt2VjfGpwRjZ">Fnatic</a>
- <a href="https://yadi.sk/d/E3_H2goupwRmN">LGD</a>
- <a href="https://yadi.sk/d/WVWu8jHRpwRmr">MVP</a>
- <a href="https://yadi.sk/d/4F1mflv5pwRnA">Newbee</a>
- <a href="https://yadi.sk/d/AZvKu0rKpwRnT">Spirit</a>
- <a href="https://yadi.sk/d/ng-3MKEupwRnt">ViciGaming</a>
- <a href="https://yadi.sk/d/lvC1EjtKpwRoj">VirtusPro</a>

========================================

- Один архив содержит последние матчи указанной команды.
- Каждый матч это файл вида <match_id>.jsonlines
- Формат матча немного отличается от формата текущих матчей и формата, представленного выше.

========================================
```python
{
    'match_id': 2199144312,                        # id матча
    'league_id': 4266,                             # id турнира или лиги
    'scoreboard': {
        'duration': 1975.660278,                   # длительность матча в секундах
        'radiant': {
            'barracks_state': 63,                  # состояние бараков (см. битовую маску)
            'players': [                           # информация об игроках команды
                {
                    'gold': 759,                   # текущее золото игрока
                    'last_hits': 43,               # число добитых вражеских крипов
                    'denies': 1,                   # число добитых дружеских крипов
                    'death': 2,                    # кол-во смертей
                    'hero_id': 5,                  # id героя, за которого играет игрок
                    'xp_per_min': 283,             # средний получаемый игроком опыт в минуту   
                    'kills': 2,                    # кол-во убийств, совершённых героем
                    'assists': 9,                  # кол-во раз когда игрок помогал совершать убийства
                    'gold_per_min': 250,           # среднее за минуту зарабатываемое игроком золото 
                    'level': 13,                   # уровень героя
                    'net_worth': 5899,             # стоимость героя - сумма имеющегося золота и стоимости всех предметов
                    'respawn_timer': 0             # число секунд до возрождения героя
                    ################## Обратите внимание, что в этой записи нет account_id, 
                    ################## но порядок записей совпадает с порядком записей в поле 'players'
                },
                ...
            ],
            'tower_state': 1830,                   # состояние башен (см. битовую маску)
            'score': 22,                           # сумма убийств по команде
        },
        'dire': ...,                               # аналогично radiant
    }, 
    'dire_team': {
        'team_name': 'MVP Phoenix', 
        'team_id': 1148284, 
        'complete': True,
    }, 
    'players': [
        {
            'team': 2,               # 0 - radiant, 1 - dire, 2,3,4 - others (spectators)
            'account_id': 299613011, # id пользователя
            'name': 'DotaMajorsRU',  # имя пользователя
            'hero_id': 0             # id героя (0 для наблюдателей)
        },
        ...
    ], 
    'series_type': 1, 
    'radiant_series_wins': 1,  # число побед команды, которая играет за radiant, в серии
    'radiant_team': {},        # аналогично dire_team       
    'dire_series_wins': 0
}
```

========================================

### Состояние вышек
Состояние вышек закодировано 16-ю битами. Правые 11 бит показывают состояние каждой вышки соответствующей команды, левые 5 бит не используются.

- 1 - вышка есть
- 0 - вышки нет

```
    ┌─┬─┬─┬─┬─────────────────────── Not used.
    │ │ │ │ │ ┌───────────────────── Ancient Bottom
    │ │ │ │ │ │ ┌─────────────────── Ancient Top
    │ │ │ │ │ │ │ ┌───────────────── Bottom Tier 3
    │ │ │ │ │ │ │ │ ┌─────────────── Bottom Tier 2
    │ │ │ │ │ │ │ │ │ ┌───────────── Bottom Tier 1
    │ │ │ │ │ │ │ │ │ │ ┌─────────── Middle Tier 3
    │ │ │ │ │ │ │ │ │ │ │ ┌───────── Middle Tier 2
    │ │ │ │ │ │ │ │ │ │ │ │ ┌─────── Middle Tier 1
    │ │ │ │ │ │ │ │ │ │ │ │ │ ┌───── Top Tier 3
    │ │ │ │ │ │ │ │ │ │ │ │ │ │ ┌─── Top Tier 2
    │ │ │ │ │ │ │ │ │ │ │ │ │ │ │ ┌─ Top Tier 1
    │ │ │ │ │ │ │ │ │ │ │ │ │ │ │ │
    0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0
```

### Состояние бараков
Аналогично состоянию вышек, состояние бараков кодируется 8-битным числом. Правые 6 бит показывают состояние соответсвующих бараков, а левые 2 бита не используются.

- 1 - барак есть
- 0 - барака нет
```
   ┌─┬───────────── Not used.
   │ │ ┌─────────── Bottom Ranged
   │ │ │ ┌───────── Bottom Melee
   │ │ │ │ ┌─────── Middle Ranged
   │ │ │ │ │ ┌───── Middle Melee
   │ │ │ │ │ │ ┌─── Top Ranged
   │ │ │ │ │ │ │ ┌─ Top Melee
   │ │ │ │ │ │ │ │
   0 0 0 0 0 0 0 0
```
