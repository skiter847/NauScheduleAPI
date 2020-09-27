# Установка

Установка с помощью pip `pip install nauschedule`

# Примеры

Для начала импортируем класс для работы с API
```python
from nauschedule import NAUScheduler

nau = NAUScheduler()
```
Список  доступных методов:

* get_department_codes() - вернет словарь, где ключем являеться название факультета, а значением код факультета.
* get_departments() - список словарей, где указаны все факультеты их коды, деканы и тд.
* get_schedule() - вернет словарь, где ключ будет '<Номер недели>.<День недели>.<Номер пары>', а значением словарем с 
информацией о предмете: название, преподаватель, место проведения и тд. 
    * department_name [str] (обязательно) - Название факультета.
    * group_number [str] (обязательно) - Номер группы.
    * subgroup [int] (необязательно) - Номер подгруппы.
    * only_lecture [bool] (необязательно) - Получить результат где будут только лекции.
    * only_practice [bool] (необязательно) - Получить результат где будет только практика.

К примеру: 
```python
    nau.get_schedule('ФАЕТ', '305')
    # '1.Пнд.3': {'teacher': 'Осіпчук А.О.', 'discipline': "Основи комп'ютерного проектув. РЕА", 'classroom': ' 3. 209', 'group': 'ФАЕТ 3к5п', 'isLecture': True}, ...

``` 

