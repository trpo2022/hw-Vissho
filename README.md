NinjaKeyboard - клавиатурный тренажер

Пользователю предоставляется строка, ввод которой он должен выполнить за произвольное время.  
Далее, пользователю выводится статистика по введенной строке. Критерии анализа написаны в ТЗ далее.  

Цель - получить информацию о том, насколько развит набор скорости на клавиатуре у пользователя по некоторым характеристикам.  

Анализ включает в себя:  
1 - Скорость набора (Количество символов/слов в секунду)  
2 - Сравнения скорости набора пользователя с общественной статистикой скорости набора на клавиатуре  
3 - Количество ошибок, допущенных пользователем  
4 - Указание на ошибки, допущенные пользователем  

Пользователь также может выбрать язык, на котором будет производиться ввод  
Доступно 2 языка:  
  1 - Русский  
  2 - Английский (English)  

Пользователю предоставляется на выбор 3 уровня сложности представленной строки.  
Уровни:  
  1 - Легкий (Включает в себя только слова из повседневного употребления/набора на клавиатуре)  
  2 - Средний (Включает в себя уровень сложности <Легкий>, а так же специальные слова, редко употребляемые в повседневной речи/наборе на клавиатуре, числа)  
  3 - Сложный (Включает в себя уровень сложности <Сложный>, а так же специальную научную литературу, символы)  

После отработки программы, пользователю будет предложено воспользоваться программой снова.  

Формат входных данных  
-для выбора языка и уровня сложности пользователь вводит соответствующую цифру. В ИК будут выделены переменные типа int для хранения результата.  
-для ввода строки пользователю будет предоставлено вводить произвольные символы клавиатуры. В ИК данные будут храниться в массиве стипа char (*char).  

Строки, которые будут предоставляться пользователю для ввода будут храниться в файле, формата '.txt' в представленном ниже виде. Первые 150 строк файла будут выделены для русского языка. Следующие - для английского. Каждые 150 строк в свою очередь соответственно делятся по 50 строк по уровню сложности.  
  
  Возможное содержание файла data.txt  
//Строки 1-150  
Я не получу хорошую оценку по предмету в университете.  
...  
//Строки 150-300  
I won't get nice mark in subject at the university.  

В случае, если пользователь ввел строку верно, то далее будет представлен ее анализ.  
В случае, если пользователь ввел строку неверно, будет выведена ошибка и информация о ней (где именно пользователь допустил ошибку).  

Детали реализации  
-Программа будет использовать функцию fgets() для записи ввода строки пользователем. Так как стандартная функция scanf() считывает строку по первого символа разделителя, что совершенно не подходит для данной реализации.  
-Для вывода ошибок и информации о них будет использоваться красный цвет.  
-Для проверки на корректность введенной пользователем строки будет использоваться отдельная функция.  

Функция будет принимать в себя строку, которую ввёл пользователь, и номер строки в базе данных, которую необходимо было вводить.  
Обработка будет происходить с помощью функции strcmp().  

Пример использования программы  
~$ ./keyboardninja  
```
 _   __           _                         _ _   _ _       _         
| | / /          | |                       | | \ | (_)     (_)        
| |/ /  ___ _   _| |__   ___   __ _ _ __ __| |  \| |_ _ __  _  __ _   
|    \ / _ \ | | | '_ \ / _ \ / _` | '__/ _` | . ` | | '_ \| |/ _` |  
| |\  \  __/ |_| | |_) | (_) | (_| | | | (_| | |\  | | | | | | (_| |  
\_| \_/\___|\__, |_.__/ \___/ \__,_|_|  \__,_\_| \_/_|_| |_| |\__,_|  
             __/ |                                        _/ |        
            |___/                                        |__/   
            *******************************************  
           * Вас приветствует программа KeyboardNinja! *  
            *******************************************  
       ***Введите цифру соответственно выбранному Вами языка***  
       1 - Русский язык (Russian)  
       2 - Английский язык (English)  
: 1  
       ***Введите желаемый уровень сложности соответственно цифре***  
       1 - Легкий  
       2 - Средний  
       3 - Сложный  
: 2  
       Отличный выбор! Через некоторое время Вам будет представлена строка,  
       которую необходимо вводить, как только увидите ее на экране, немедлннно приступайте!  
3  
2  
1  
  
Я не получу хорошую оценку по предмету в университете.  

: Я не получу хорошую оценку по предмету в университете.  

              ***WOW Вы ввели строку без ошибок!***  
Скорость Вашего набора на клавиатуре составляет примерно 120 слов в минуту  
          В среднем, это выше чем у 42% населения планеты  

              ***Воспользоваться программой еще раз?***  
              1 - ДА  
              2 - НЕТ  
: 2  
До свидания!  

~$  
