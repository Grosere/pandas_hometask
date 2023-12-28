# pandas_hometask
 
 В связи с неопределнностью методологии решения Задача 44:
 
> В ячейке ниже представлен код генерирующий DataFrame, которая состоит всего из 1 столбца. Ваша задача перевести его в one hot вид. Надо это сделать без get_dummieНs.
>> <span style="color:violet"> import </span> random
>> 
>> lst = ['robot'] <span style="color:green"> * 10 </span>
>> 
>> lst += ['human'] <span style="color:green"> * 10 </span>
>> 
>> random.shuffle(lst)
>> 
>> data = pd.DataFrame({'whoAmI':lst})
>> 
>> data.head() 

Мною была проведена работа на базе <span style="color:orange"> ___collab.google NewNotebook___ </span>., а именно:

1. В выше указанный код, добавлена строка:

> <span style="color:violet"> import </span> pandas as pd

Для того, чтобы код работал, на базе библиотеке "Пандас"

2. Для решения задачи нужно преобразовать столбец "whoAmI" в DataFrame "data" в формат one hot. Это означает, что для каждого уникального значения в столбце будет создан новый столбец, в котором будут содержаться только значения 0 или 1. Если значение в исходном столбце равно уникальному значению, то в новом столбце будет 1, иначе - 0.

В данном случае уникальные значения в столбце "whoAmI" - это "robot" и "human". Поэтому нужно создать два новых столбца: "is_robot" и "is_human".

> data['is_robot'] = data['whoAmI'].apply(lambda x: 1 if x == 'robot' else 0)
> 
> data['is_human'] = data['whoAmI'].apply(lambda x: 1 if x == 'human' else 0)

Теперь DataFrame "data" будет содержать столбцы "whoAmI", "is_robot" и "is_human", которые представляют собой данные в формате one hot.

Итоговый код:

> <span style="color:violet"> import </span> random
> 
> <span style="color:violet"> import </span> pandas <span style="color:violet"> as </span> pd
> 
>lst = ['robot'] <span style="color:green"> * 10 </span>
> 
>lst += ['human'] <span style="color:green"> * 10 </span>
> 
>random.shuffle(lst)
> 
>data = pd.DataFrame({'whoAmI':lst})
> 
>data['is_robot'] = data['whoAmI'].apply(<span style="color:blue"> lambda </span> x: 1 if x == 'robot' else 0)
> 
>data['is_human'] = data['whoAmI'].apply(<span style="color:blue"> lambda </span> x: 1 if x == 'human' else 0)
> 
>data.head()

Результат выполнения кода, приведен на скриншоте ниже:

![Результат](/Pandas.jpg)
