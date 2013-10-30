# Курсовая работа по Базам данных

__ДГТУ | ВБПИ31 | 2013г__

---

##Задание

Задача 12. _База данных для учета аудиторного фонда университета._

>База данных должна содержать следующую информацию об аудиторном фонде университета: наименование корпуса, в котором расположено помещение, номер комнаты, расположение комнаты в корпусе, ширина и длина комнаты в метрах, назначение и вид помещения, подразделение университета, за которым закреплено помещение. В базе данных так же должна быть информация о высоте потолков в помещениях (в зависимости от места расположения помещений в корпусе). Следует так же учитывать, что структура подразделений университета имеет иерархичный вид, когда одни подразделения входят в соства других (факультет, кафедра, лаборатория, ...).  
>Помимо SQL-запросов для создания таблиц базы данных, составьте запрос на создания представления (__VIEW__), в котором помимо приведенной выше информации присутствовали бы данные о площадях и объемах каждого помещения

---

##Сущности
+ Корпус  
+ Комната  
+ Факультет  
+ Кафедра  
+ Лаборатория  

---

##Схема

| Корпус       | Комната            | Факультет     | Кафедра          | Лаборатория    |
| ---          | ---                | ---           | ---              | ---            |
| Наименование | Номер              | Название      | Название         | Кафедра        |
| ® Комнаты    | Ширина и длина     | Декан         | Зав. Кафедрой    | Ответственный  |
|              | Назначение         | ® Кафедры     | Специализация    | ® Комната      |
|              | Вид помещения      |               | ® Факультет      | ® Кафедры      |
|              | Высота потолков    |               | ® Лаборатории    |                |
|              | Подразделение      |               |                  |                |
|              | Этаж               |               |                  |                |
|              | ® Корпус           |               |                  |                |
|              | ® Лаборатория      |               |                  |                |

_® - связи (relationship)_

---

![schema](https://bitbucket.org/wiruzx/db-coursework/raw/8a5afb1ea9f6ae562f30b25e51a62ba00994d437/schema.png)
