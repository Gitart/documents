## Протокол выполнения скриптов

Протоколирование выполнения скриптов в отдельной базе. 
Для этого разворачиваем сервис который принимает на вход данные о прохождении скрипта. На базе данных строится отчет о существующих ошибках при сборки релиза.

## Reliase Protocol

```bat
rp.exe PROJECT RLS SQLNAME ERR TYPE OWNER TASK 

Где :
      PROJECT     -- код проекта
      RLS         -- номер релиза
      SQLNAME     -- наименование sql
      ERR         -- ошибка (если есть)
      TYPE        -- тип 
      OWNER       -- разработчик 
      TASK        -- задача в JIRA
```



### Rls 
|Field|Type|Description
|----|-----|---|
|**Id**|String|Unique key
|**Rls**|String|Номер релиза
|**Created**|Date|Дата создания записи
|**Project**|String|Проект код проекта
|**Sum**|String|Контрольная сумма
|**Status**|String|Статус всего релиза (Ok,Er,Ar)

### RlsProtocol
|Field|Type|Description
|----|-----|---|
|**Id**|String|Unique key
|**Rls**|String|Номер релиза
|**Project**|String|Проект код проекта
|**Created**|Date|Дата создания записи
|**Updated**|Date|Дата обновления записи
|**Sql**|str|Имя запроса
|**Status**|String|Статус (Ok,Er,Ar)
|**Owner**|String|Developer
|**Develop**|String|Разработчик
|**Object**|String|Объект
|**Comment**|String|Коментарии или примечания 
|**Task**|String|Номер задачи
|**Path**|String|Путь к скрипту
|**Size**|String|Размер скрипта
|**Revizion**|String|Ревизии
|**Module**|String|Модуль
|**Lnk**|String|Линк на скрипт в SVN

## Status  
  
|Name|Description
|----|-----|
|**Ok**|Удачно завершенный скрипт
|**Er**|Скрипт завершен с ошибкой
|**Ar**|Скрипт перенесен в архив
|**Bl**|Заблокированный скрипт 
|**Inv**|Не рабочий скрипт

## Тип файлов  
  
|Name|Description
|----|-----|
|**Sql**|Скрипт
|**trg**|Триггер
|**prc**|Процедура
|**pkb**|?
|**dtl**|?
|**pkh**|?










