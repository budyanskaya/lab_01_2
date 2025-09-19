# Лабораторная работа 1.2 Написание скриптов с использованием условных операторов. Решение задач с использованием циклов
## Цели:
1. Изучить основные управляющие конструкции языка Python: условный оператор и циклы.
2. Научиться использовать управляющие структуры для решения задач различной сложности.
3. Закрепить навыки обработки данных с использованием коллекций и итераторов.
4. Развить умение комбинировать условия и циклы для оптимизации
алгоритмов.

## № 1.2.1 Рассчитать значение f при заданном значении вещественного числа x
```
x = float(input("Введите число x: ")) #запрашиваем ввод числа

if x >= 0: # проверяем условия для х
    f = x**0.5 + x**2
else:
    f = 1 / x

print(f"f = {f:.2f}") # выводим результат
```
Вывод:

<img width="712" height="255" alt="image" src="https://github.com/user-attachments/assets/6073c286-7bb2-4b23-b78f-81bf5b5822a3" />

## № 1.2.2 Определите максимальное и минимальное значения из двух различных целых чисел.
```
a1 = int(input("Введите первое число: "))# запрашивае ввод числа
a2 = int(input("Введите второе число: "))

if a1 > a2: #задаем условия для чисел
  a_max = a1
  a_min = a2
else:
  a_max = a2
  a_min = a1

print(f"Максимум: {a_max}, минимум: {a_min}") # выводим результат
```
Вывод:

<img width="888" height="363" alt="image" src="https://github.com/user-attachments/assets/677bcbd9-40a9-40da-8955-044f576f9722" />

## № 1.2.3 Вася пытается высунуть голову в форточку размерами a и b см. Приняв условно, что его голова - круглая диаметром d см, определите, сможет ли Вася сделать это. Для прохождения головы в форточку необходим зазор в 1 см. с каждой стороны. Все величины - целые числа.
```
a = int(input("Ширина форточки: ")) #запрашиваем ввод чисел для зармера форточки и головы
b = int(input("Высота форточки: "))
d = int(input("Диаметр головы: "))

if a > 0 and b > 0 and d >0: # проверяем положительные ли числа и задаем условия
    fix = 1  # Зазор

    if d <= a - 2*fix and d <= b - 2*fix: # учитываем зазор с каждой стороны по 1см
      print("Да")
    else:
      print("Нет")

# выводим результат
else:
  print("Проверьте ввод")
```
Вывод:

<img width="882" height="526" alt="image" src="https://github.com/user-attachments/assets/2b8d52e5-f322-4a43-985d-6e715ec907bb" />

## № 1.2.4 Известны год и номер месяца сегодняшнего дня, а также год и номер месяца рождения человека (нумерация месяцев с 1: январь - 1 и т.д.). Определите возраст человека (число полных лет).
```
year_today = int(input("Введите текущий год: ")) # запрашиваем ввод данных
month_today = int(input("Введите текущий месяц: "))

year = int(input("Введите год рождения: "))
month = int(input("Введите месяц рождения: "))

# считаем полное количество лет
age = year_today - year # вычисляем разницу по годам
if month_today < month: # учитываем то, что если текущий месяц меньше месяца рождения, то день рождения еще не наступил
  age -= 1
# выводим результат
print("Число полных лет: ", age)
```
Вывод:

<img width="1093" height="442" alt="image" src="https://github.com/user-attachments/assets/959bbe67-a10a-43cf-be7c-38575a1af609" />

## № 1.2.5 Дана точка с целыми ненулевыми координатами (x;y). Определить номер четверти координатной плоскости, которой она принадлежит.
```
x = int(input("Введите координату x: ")) # запрашиваем ввод ненулевых координат
y = int(input("Введите координату y: "))

if x > 0 and y > 0: # определяем четверть
    print("1-я четверть")
elif x < 0 and y > 0:
    print("2-я четверть")
elif x < 0 and y < 0:
    print("3-я четверть")
else:  
    print("4-я четверть")
```
Вывод:

<img width="808" height="412" alt="image" src="https://github.com/user-attachments/assets/54a17e98-3c65-4e02-b8da-2c6b4da7bd71" />

## № 1.2.6 Даны вещественные числа a, b, c (a≠0). Решите уравнение ax2+bx+c=0. При выводе значений оставьте 1 знак после запятой
```
a = float(input("a = ")) # запрашиваем ввод коэффициентов квадратного уравнения 
b = float(input("b = "))
c = float(input("c = "))

D = b**2 - 4*a*c # считаем дискриминант

if D < 0: # проверяем корни
    print("Решений нет")
elif D == 0:
    x = -b / (2 * a)
    print(f"x = {x:.1f}")
else:
    x1 = (-b - D**0.5) / (2 * a)
    x2 = (-b + D**0.5) / (2 * a)
    print(f"x1 = {x1:.1f}, x2 = {x2:.1f}")
```
Вывод:

<img width="811" height="493" alt="image" src="https://github.com/user-attachments/assets/e3d04b47-a75d-41c1-a4ff-2651b5ff9b1e" />

## № 1.2.7 Дана непустая последовательность целых чисел, оканчивающаяся нулем. Найти сумму и количество введенных чисел.
```
nums_sum = 0   # сумма 
nums_count = 0 # количество 

x = int(input("Введите число: ")) # вводим первое число

while x != 0: # используем цикл, чтобы последовательно обрабатывать вводимые числа, пока не встретим 0 
    nums_sum += x      
    nums_count += 1    
    x = int(input("Введите число: "))  # читаем следующее число

# выводим результат
print("Сумма =", nums_sum)
print("Количество =", nums_count)
```
Вывод:

<img width="978" height="487" alt="image" src="https://github.com/user-attachments/assets/b6711c8e-9375-4616-bfaa-d1239271066b" />

## № 1.2.8 Дано число n. Из чисел 0,5,10,15,20,25,... напечатать те, которые не превышают n.
```
n = int(input("n = ")) # запрашиваем ввод числа n

x = 0
while x <= n: # начинаем с 0 и будем прибавлять 5, пока число не превысит n
    print(x)
    x += 5  # следующее число последовательности
```
Вывод:

<img width="867" height="232" alt="image" src="https://github.com/user-attachments/assets/40eabd12-8096-440f-80b6-dcfb97613368" />

## № 1.2.9 Дано вещественное число a. Найдите наименьшее натуральное n, для которого верно
```
a = float(input("a = ")) # вводим число а

n = 1        # начинаем с 1
x_sum = 0.0  # сумма ряда

while x_sum <= a: # пока сумма не превысит a, добавляем следующий член
    x_sum += 1 / n
    n += 1

n -= 1 # после выхода из цикла n увеличилось на 1 лишний раз, поэтому вычитаем 1

print("n =", n)
```
Вывод:

<img width="855" height="362" alt="image" src="https://github.com/user-attachments/assets/06fb0c50-9bb5-40d3-bad6-2ede1d684869" />

## № 1.2.10 Дано натуральное число. Определите сумму и количество его цифр.
```
n = int(input("n = ")) # вводим число

n_sum = 0
n_count = 0

temp = n # создаём копию числа, чтобы не потерять исходное значение

while temp > 0: # до тех пор пока число не стало 0, извлекаем последнюю цифру
    digit = temp % 10       
    n_sum += digit          
    n_count += 1            
    temp = temp // 10       

print("Сумма =", n_sum) # выводим результат
print("Количество =", n_count)
```
Вывод:

<img width="777" height="447" alt="image" src="https://github.com/user-attachments/assets/37265413-37f2-4ed2-b1ad-5fa1385e7866" />

## № 1.2.11 Вывести в строку 10 первых натуральных чисел, оканчивающихся на цифру k, кратных числу s и находящихся в интервале, левая граница которого равна start.
```
start = int(input("start = ")) # запрашиваем ввод данных 
k = int(input("k = "))
s = int(input("s = "))

n_count = 0        # счётчик найденных чисел
num = start        # начинаем проверку с числа start


while n_count < 10: # ищем подходящие числа и выводим их

   
    if num % s == 0 and num % 10 == k: # проверяем заданные условия
        print(num, end=" ")
        n_count += 1
    num += 1  # переходим к следующему числу
```

Вывод:

<img width="825" height="487" alt="image" src="https://github.com/user-attachments/assets/6904b270-a6b2-4f72-901e-c98e24a84fef" />

## № 1.2.12 Даны целые числа a и b (a может быть больше b). Напечатайте: числа от минимального до максимального в строчку (разделяя пробелом); числа от максимального до минимального «столбиком»
```
a = int(input("a = ")) # запрашиваем ввод чисел
b = int(input("b = "))


low = min(a, b)   # определяем границы
high = max(a, b)  

for i in range(low, high + 1): # выводим числа от минимального до максимального в одну строку
    print(i, end=" ")
print()  

for i in range(high, low - 1, -1): # выводим числа от максимального до минимального «столбиком»
    print(i)
```
Вывод:

<img width="902" height="542" alt="image" src="https://github.com/user-attachments/assets/0e6c5291-afc3-4b4d-ad45-23c51395ec66" />

## № 1.2.13 Для введенных с клавиатуры положительных целых чисел a и b (a≤b) определите: сумму всех целых чисел от a до b; произведение всех целых чисел от a до b; среднее арифметическое всех целых чисел от a до b; среднее геометрическое нечетных чисел от a до b. Отрезок поиска включает сами числа a и b. При выводе вещественных результатов оставьте два знака после запятой.
```
a = int(input("a = ")) # ввод чисел
b = int(input("b = "))

n_sum = 0             # сумма всех чисел
n_mult = 1            # произведение всех чисел
odd_mult = 1          # произведение нечётных чисел
odd_count = 0         # количество нечётных чисел
count = 0             # количество всех чисел

for i in range(a, b + 1): # цикл по всем целым числам от a до b включительно
    n_sum += i
    n_mult *= i
    count += 1
    if i % 2 != 0:          
        odd_mult *= i
        odd_count += 1

n_avg = n_sum / count # среднее арифметическое

if odd_count > 0: # среднее геометрическое нечётных чисел
    n_avg_geom = odd_mult ** (1 / odd_count)
else:
    n_avg_geom = 0  # если нечётных нет, можно вывести 0 

print("Сумма =", n_sum)
print("Произведение =", n_mult)
print("Среднее арифметическое = {:.2f}".format(n_avg))
print("Среднее геометрическое нечетных чисел = {:.2f}".format(n_avg_geom))
```
Вывод:

<img width="903" height="581" alt="image" src="https://github.com/user-attachments/assets/430fc254-3cff-4caa-bfcf-79e267bc0c37" />

## № 1.2.14 Начав тренировки, лыжник в первый день пробежал s км. (s>0, вещественное число). Каждый следующий день он увеличивал пробег на p % (0<p≤100, вещественное число) от пробега предыдущего дня. Определите: пробег лыжника за второй, третий, …, десятый день тренировок; какой суммарный путь он пробежал за первые 10 дней тренировок. При выводе вещественных результатов оставьте один знак после запятой.
```
s = float(input("Пробег за 1-й день (км.) = ")) # ввод данных
p = float(input("На сколько увеличивает пробег (%) = "))

total = s  # суммарный пробег за все дни 

for day in range(2, 11): # цикл со 2-го по 10-й день
    s = s + s * p / 100 # увеличиваем пробег на p% от предыдущего дня
    total += s # прибавляем к общей сумме
    print(f"Пробег за {day}-й день: {s:.1f} км.")

print("Суммарный пробег: {:.1f} км.".format(total))
```
Вывод:

<img width="998" height="603" alt="image" src="https://github.com/user-attachments/assets/410b7c2e-a822-40fe-8917-870a72959f63" />

## № 1.2.15 Известна масса каждого предмета в кг., загружаемого в грузовик. Определить, возможна ли перевозка груза, если грузоподъемность грузовика равна p кг.
```
p = float(input("Грузоподъемность грузовика (кг.) = ")) # ввод грузоподъёмности и количества предметов
n = int(input("Количество предметов = "))

total = 0  # общая масса всех предметов

for i in range(1, n + 1): # цикл для ввода массы каждого предмета и подсчёта суммы
    mass = float(input(f"Масса {i}-го предмета (кг.) = "))
    total += mass

if total <= p: # проверяем можно ли перевозить весь груз
    print("Да")
else:
    print("Нет")
```
Вывод:

<img width="946" height="460" alt="image" src="https://github.com/user-attachments/assets/f2c40f32-b557-4c53-9299-b503e9be0e64" />

## № 1.2.16 В области несколько районов. Заданы площади, засеваемые пшеницей (га.), и средняя урожайность (ц/га) в каждом районе. Определите количество пшеницы, собранное по области. При выводе вещественных результатов оставьте один знак после запятой.
```
n = int(input("Количество районов = ")) # вводим количество районов

total = 0.0  # общая масса пшеницы 

for i in range(1, n + 1): # для каждого района спрашиваем площадь и урожайность
    area = float(input(f"Площадь {i}-го района (га) = "))
    yield_avg = float(input(f"Урожайность в {i}-м районе (ц/га.) = "))
    total += area * yield_avg  # добавляем собранное количество

print("Собрано пшеницы: {:.1f} ц.".format(total))
```
Вывод:

<img width="970" height="482" alt="image" src="https://github.com/user-attachments/assets/e376d030-5c83-47e9-adb6-769ee9c4b744" />

## № 1.2.17 Решите задачу № 2.7, организовав бесконечный цикл, который бы прерывался при выполнении условия, используя оператор break.
```
nums_sum = 0    # сумма введённых чисел
nums_count = 0  # количество введённых чисел
i = 1           # порядковый номер для вывода приглашения

while True:  # бесконечный цикл
    x = int(input(f"Введите {i}-е число: "))
    if x == 0:      # если ввели 0 — прерываем цикл
        break
    nums_sum += x   # добавляем к сумме
    nums_count += 1 # увеличиваем количество
    i += 1

print("Сумма =", nums_sum)
print("Количество =", nums_count)
```
Вывод:

<img width="857" height="530" alt="image" src="https://github.com/user-attachments/assets/621eb527-112c-42f0-acac-9da7947d759d" />

## № 1.2.18 Предложение, введенное с клавиатуры, содержит слова из гласных и согласных букв кириллицы (регистр может быть различный), а также пробелы. Определите количество гласных и согласных букв в предложении. Для пропуска пробелов используйте оператор continue .
```
sentence = input("Введите предложение: ") # ввод данных

count_gl = 0     # количество гласных
count_sogl = 0   # количество согласных

vowels = "аеёиоуыэюя"  # гласные буквы в нижнем регистре

for ch in sentence:
    ch = ch.lower()           # переводим букву в нижний регистр
    if ch == " ":             # пропускаем пробелы
        continue
    if ch in vowels:          # если символ гласный
        count_gl += 1
    else:                     # иначе считаем как согласный
        count_sogl += 1

print(f"Кол-во букв в предложении: гласных - {count_gl}, согласных - {count_sogl}")
```
Вывод:

<img width="1278" height="496" alt="image" src="https://github.com/user-attachments/assets/7aaff8cc-1ccf-40d4-9471-56354a837ea9" />

## № 1.2.19 Выведите на экран (в строку) все целые числа от a до b, кратные некоторому числу c.
```
a = int(input("a = ")) # ввод чисел 
b = int(input("b = "))
c = int(input("c = "))

for i in range(a, b + 1): # перебираем все числа от a до b включительно
    if i % c == 0:   # проверяем кратность c
        print(i, end=" ")
```
Вывод:

<img width="876" height="301" alt="image" src="https://github.com/user-attachments/assets/633f05f6-d28b-4032-804c-79343fbfd259" />

## № 1.2.20 Выведите на экран (в строку) все трехзначные натуральные числа, сумма цифр которых равна целому числу n (0<n≤27).
```
n = int(input("n = ")) # вводим данные

for num in range(100, 1000): # перебираем все трехзначные числа от 100 до 999
    hundreds = num // 100           # сотни
    tens = (num // 10) % 10         # десятки
    units = num % 10                # единицы

    if hundreds + tens + units == n: # проверяем, равна ли сумма цифр n
        print(num, end=" ")
```
Вывод:

<img width="1125" height="296" alt="image" src="https://github.com/user-attachments/assets/c2dfb162-c3d1-4c15-a519-4149db550216" />

## № 1.2.21 Известно количество учеников в классе и их рост (см.); рост мальчиков условно задан отрицательными числами. Определите средний рост мальчиков и средний рост девочек.
```
n = int(input("n = ")) # ввод количества учеников

sum_boys = 0.0   # сумма роста мальчиков
count_boys = 0   # количество мальчиков
sum_girls = 0.0  # сумма роста девочек
count_girls = 0  # количество девочек

for i in range(1, n + 1): # ввод роста каждого ученика
    r = int(input(f"Рост {i}-го ученика = "))
    if r < 0:  # если рост отрицательный — мальчик
        sum_boys += abs(r)  
        count_boys += 1
    else:      # рост положительный — девочка
        sum_girls += r
        count_girls += 1

r_sr_m = sum_boys / count_boys if count_boys > 0 else 0 # вычисляем средний рост
r_sr_d = sum_girls / count_girls if count_girls > 0 else 0

print("Средний рост мальчиков: {:.1f}".format(r_sr_m))
print("Средний рост девочек: {:.1f}".format(r_sr_d))
```
Вывод:

<img width="837" height="637" alt="image" src="https://github.com/user-attachments/assets/7dc58264-ca4a-43fa-9514-43ddcd5571e9" />

## № 1.2.22 Даны n вещественных чисел. Определите максимальное и минимальное из них. При выводе вещественных результатов оставьте два знака после запятой.
```
n = int(input("n = ")) # ввод чисел

a_max = None  # для максимального значения
a_min = None  # для минимального значения

for i in range(1, n + 1): # ввод n вещественных чисел
    x = float(input(f"{i}-е число = "))
    if a_max is None or x > a_max:
        a_max = x           # обновляем максимум
    if a_min is None or x < a_min:
        a_min = x           # обновляем минимум

print("Максимум: {:.2f}".format(a_max))
print("Минимум: {:.2f}".format(a_min))
```
Вывод:

<img width="892" height="547" alt="image" src="https://github.com/user-attachments/assets/ab09f786-6329-493b-9c63-152c9583cc38" />

## № 1.2.23 Дано натуральное число n. Определите, является ли оно членом последовательности Фибоначчи .
```
n = int(input("n = ")) # ввод числа

a, b = 0, 1 # первые два числа последовательности Фибоначчи
is_fibo = False  # является ли число членом последовательности

while b <= n: # генерируем числа Фибоначчи, пока не превысим n
    if b == n:           # если нашли совпадение
        is_fibo = True
        break
    a, b = b, a + b      # переходим к следующему числу

print("Является" if is_fibo else "Не является")
```
Вывод:

<img width="935" height="382" alt="image" src="https://github.com/user-attachments/assets/4bdbdf97-5753-45f6-8633-23fb40774a44" />

## № 1.2.24 Дано n вещественных чисел. Определите, является ли последовательность упорядоченной по возрастанию. В случае отрицательного ответа выведите порядковый номер числа, нарушающего такую упорядоченность.
```
n = int(input("n = ")) # вводим количество чисел

index = -1

prev = float(input("1-е число = "))

for i in range(2, n + 1): # перебираем оставшиеся n-1 чисел
    curr = float(input(f"{i}-е число = "))

    if curr <= prev: # проверяем условие возрастания, текущее должно быть строго больше предыдущего
        index = i      
        break          # прерываем цикл, т.к условие уже нарушено
    prev = curr        # обновляем предыдущее значение

if index == -1:
    print("Является")
else:
    print(index)
```
Вывод:

<img width="1003" height="591" alt="image" src="https://github.com/user-attachments/assets/32db5ca0-f6cc-4f66-b831-5032b86864fe" />

## № 1.2.25 Выведите на экран таблицу умножения на n (2<n≤9) в виде:
```
n = int(input("n = ")) # вводим размер таблицы

for i in range(1, n + 1): # строки (первый множитель)
    for j in range(1, n + 1): # столбцы (второй множитель)
        print(f"{i} * {j} = {i*j:2}", end="  ") # выравнивает результат по ширине
    print()  
```
Вывод:

<img width="791" height="315" alt="image" src="https://github.com/user-attachments/assets/de53dc14-7188-4155-88bf-103330928b66" />

## # № 1.2.26 Выведите графическое изображения делимости чисел от 1 до n (значение n вводится с клавиатуры) - в каждой строке напечатайте очередное число и столько символов * , сколько делителей у этого числа. Например, если n=4, на экране должно быть напечатано: 1 * 2 ** 3 ** 4 ***
```
n = int(input("n = ")) # ввод данных

for i in range(1, n + 1): # перебираем числа от 1 до n
    count_div = 0  # счётчик делителей для i
    for j in range(1, i + 1): # проверяем все возможные делители числа i
        if i % j == 0:
            count_div += 1
    
    print(f"{i} {'*' * count_div}")

```
Вывод:

<img width="843" height="640" alt="image" src="https://github.com/user-attachments/assets/5404682c-8094-4a63-9fb7-cde6501bde6c" />

## № 1.2.27 Выведите на экран (в строку) n первых простых чисел.
```
n = int(input("n = ")) # ввод количества простых чисел

count = 0      # сколько простых чисел уже найдено
num = 2        # текущее число для проверки

while count < n:                 # пока не нашли n простых
    is_prime = True
    for i in range(2, int(num ** 0.5) + 1):  # проверяем делители до корня
        if num % i == 0:
            is_prime = False
            break
    if is_prime:
        print(num, end=" ")
        count += 1
    num += 1
```
Вывод:

<img width="692" height="431" alt="image" src="https://github.com/user-attachments/assets/0b28f23c-f48c-4a5a-8c90-221d70a669d6" />

## № 1.2.28 Составьте программу для нахождения всех натуральных решений уравнения x2+y2+z2=k2, где x,y,z∈[1,30], а k вводится с клавиатуры.
```
k = int(input("k = ")) # ввод значения k

for x in range(1, 31): # перебираем все возможные x, y, z от 1 до 30 включительно
    for y in range(1, 31):
        for z in range(1, 31):
            if x**2 + y**2 + z**2 == k**2:
                print(f"x = {x:2d}, y = {y:2d}, z = {z:2d}")
```
Вывод:

<img width="1251" height="537" alt="image" src="https://github.com/user-attachments/assets/a36c7df9-258f-41cf-b085-51d053aa4977" />

## № 1.2.29 Дан список из n вещественных чисел, введенных с клавиатуры (среди чисел есть по крайней мере одно положительное и отрицательное число).
```
import math

n = int(input("n = "))

nums = [] # ввод исходного списка
for i in range(n):
    nums.append(float(input(f"Введите {i+1}-й элемент списка: ")))

nums_pos = [x for x in nums if x > 0] # положительные числа 

nums_neg = [] # отрицательные числа 
for x in nums:
    if x < 0:
        nums_neg.append(x)

sr_ar = sum(nums_pos) / len(nums_pos) # среднее арифметическое положительных

product = 1 # среднее геометрическое отрицательных 
for x in nums_neg:
    product *= abs(x)
sr_geom = product ** (1 / len(nums_neg))

print("Исходный список:", nums)
print("Положительные числа:", nums_pos)
print("Отрицательные числа:", nums_neg)
print("Ср. арифм.: {:.2f}".format(sr_ar))
print("Ср. геом.: {:.2f}".format(sr_geom))
```
Вывод:


<img width="732" height="667" alt="image" src="https://github.com/user-attachments/assets/65f2c121-38f0-4e6d-8ebf-f146d14a227a" />

## № 1.2.30 Дан список целых чисел, введенных с клавиатуры (длина неизвестна). Ответьте на вопросы: являются ли все элементы положительными числами? есть ли хотя бы один нулевой элемент в списке? являются ли все элементы четными числами? есть ли хотя бы один нечетный элемент в списке? Каждый из пунктов выполните дважды: используя стандартный проход в цикле (например, через алгоритм с флажком), и используя функции any() и/или all() .
```
nums = [int(item) for item in input().split()]

# 1. Все положительные 
for item in nums:
    if item <= 0:
        all_pos_1 = False
        break
else:
    all_pos_1 = True

# 1. Все положительные 
all_pos_2 = all(item > 0 for item in nums)

# 2. Хотя бы 1 нулевой элемент 
for item in nums:
    if item == 0:
        any_zero_1 = True
        break
else:
    any_zero_1 = False

any_zero_2 = any(item == 0 for item in nums)

# 3. Все чётные 
for item in nums:
    if item % 2 != 0:
        all_even_1 = False
        break
else:
    all_even_1 = True

# 3. Все чётные 
all_even_2 = all(item % 2 == 0 for item in nums)

# 4. Хотя бы 1 нечётный 
for item in nums:
    if item % 2 != 0:
        any_odd_1 = True
        break
else:
    any_odd_1 = False

any_odd_2 = any(item % 2 != 0 for item in nums)


print("Все положительные:", all_pos_1, all_pos_2)
print("Хотя бы 1 нулевой элемент:", any_zero_1, any_zero_2)
print("Все четные:", all_even_1, all_even_2)
print("Хотя бы 1 нечетный элемент:", any_odd_1, any_odd_2)
```
Вывод:

<img width="811" height="633" alt="image" src="https://github.com/user-attachments/assets/453987d4-9e2d-4b61-ba12-9b2b7cfbf690" />

## № 1.2.31 Дано предложение. Выведите его на экран, удалив из него все слова, содержащие произвольную букву (вводится с клавиатуры).
```
s = input("Введите предложение = ") # ввод данных
k = input("Введите букву = ")

words = s.split() # разделяем предложение на слова

filtered = [word for word in words if k.lower() not in word.lower()] # оставляем только те слова, в которых нет введённой буквы 

print(" ".join(filtered))
```
Вывод:

<img width="1191" height="317" alt="image" src="https://github.com/user-attachments/assets/b5ada2c9-73ed-49b9-a81c-2906a41627e6" />

## № 1.2.32 В зрительном зале кинотеатра n рядов, количество мест в которых может меняться.
```
n = int(input("Количество рядов = ")) # ввод количества рядов

# 1. Заполнение мест
seats = []
for i in range(n):
    row = [int(x) for x in input(f"Введите ряд {i+1} (0 - свободно, 1 - занято): ").split()]
    seats.append(row)

# 2. Подсчёт всех свободных мест
count = 0
for row in seats:
    for seat in row:
        if seat == 0:
            count += 1

print("Всего свободных мест:", count)

# 3. Проверка конкретного места
n_p, m_p = [int(item) for item in input("Введите ряд и место через пробел: ").split()]

if n_p < 1 or n_p > len(seats):
    print("Такого места не существует")
elif m_p < 1 or m_p > len(seats[n_p - 1]):
    print("Такого места не существует")
else:
    free = seats[n_p - 1][m_p - 1] == 0
    print("Место свободно:", free)
```
Вывод:

<img width="897" height="670" alt="image" src="https://github.com/user-attachments/assets/e11eb6d5-b499-4c2a-b93d-fe03929219d4" />

# № 1.2.33 Вводится список из n сотрудников в формате: Фамилия Имя Отчество Пол Стаж
```
# 1. Ввод списка сотрудников
n = int(input("Количество сотрудников = "))

employees = []
for i in range(n):
    emp = input(f"{i+1}-й сотрудник (Фамилия Имя Отчество Пол Стаж): ").split()
    emp[4] = int(emp[4])  
    employees.append(emp)

for emp in employees:# вывод списка для проверки
    print(" ".join(map(str, emp)))

# 2. Самый "молодой" и самый "старый" сотрудник 
sorted_employees = sorted(employees, key=lambda x: x[4])
employee_min = sorted_employees[0]
employee_max = sorted_employees[-1]

print("Cамый \"молодой\":", " ".join(employee_min[:3]))
print("Cамый \"старый\":", " ".join(employee_max[:3]))

# 3. Отдельные списки мужчин и женщин
men = [emp for emp in employees if emp[3] == "М"]
women = [emp for emp in employees if emp[3] == "Ж"]

k = input("Введите букву начала имени = ").lower()

# Подсчёт имен, начинающихся на букву k
men_k_count = sum(1 for emp in men if emp[1].lower().startswith(k))
women_k_count = sum(1 for emp in women if emp[1].lower().startswith(k))

# Определение, у кого таких имен больше
if men_k_count > women_k_count:
    print("У мужчин таких имен больше")
elif women_k_count > men_k_count:
    print("У женщин таких имен больше")
else:
    print("Таких имен поровну у мужчин и женщин")
```
Вывод:

<img width="766" height="532" alt="image" src="https://github.com/user-attachments/assets/1ab007f8-3cbe-4fa4-a827-979c62d0bb3e" />

## № 1.2.34 Вводится список из n годовых вкладов, предлагаемых банками, в формате: Банк Сумма Процент
```
# 1. Ввод данных о банках
n = int(input("Количество банков = "))

deposits = []
for i in range(n):
    data = input(f"{i+1}-й банк (Название Сумма Процент): ").split()
    bank = {
        "name": data[0],
        "initial_sum": int(data[1]),
        "rate": float(data[2])
    }
    deposits.append(bank)

# Вывод списка для проверки
for bank in deposits:
    print(bank["name"], bank["initial_sum"], bank["rate"])

# 2. Самый доступный банк (с минимальной первоначальной суммой)
affordable_bank = min(deposits, key=lambda x: x["initial_sum"])
print(f"Самый доступный банк: {affordable_bank['name']}, первоначальная сумма: {affordable_bank['initial_sum']:.2f} руб.")

# 3. Самый выгодный банк (по прибыли за год)
profitable_bank = max(deposits, key=lambda x: x["initial_sum"] * x["rate"] / 100)
profit = profitable_bank["initial_sum"] * profitable_bank["rate"] / 100
print(f"Самый выгодный банк: {profitable_bank['name']}, прибыль: {profit:.2f} руб.")
```
Вывод:

<img width="1107" height="585" alt="image" src="https://github.com/user-attachments/assets/7c8f2310-63c6-4264-8b80-29b937056aa6" />

# Вывод
Мы изучили основные управляющие конструкции языка Python: условный оператор и циклы, научились использовать управляющие структуры для решения задач различной сложности, закрепили навыки обработки данных с использованием коллекций и итераторов, а также развили умение комбинировать условия и циклы для оптимизации алгоритмов.





























































