# PythonLearning

# Циклы

messages_count = 10
for i in reversed(range(2, messages_count + 1)):
    print('- Анфиса, есть ли новые письма?')
    print('- Непрочитанных писем:', str(i) + '.')
    print('Я прочитал одно, и их осталось', str(i-1) + '.')
print('- Анфиса, есть ли новые письма?')
print('- Одно непрочитанное письмо.')
print('Я прочитал его. И нет больше писем!')

# Логические выражения
# if-elif-else
for messages_count in range(0, 100):
    remainder = messages_count % 10
    if messages_count == 0:
        print('У вас нет новых сообщений')
    elif 10 < messages_count < 21:
        print('У вас', messages_count, 'новых сообщений')
    elif remainder == 1:
        print('У вас', messages_count, 'новое сообщение')
    elif remainder >= 2 and remainder <= 4:
        print('У вас', messages_count, 'новых сообщения')
    elif remainder >= 5 and remainder <= 9 or remainder== 0:
        print('У вас', messages_count, 'новых сообщений')
 
# Функции и их аргументы 
 
def print_friends_count(friends_count, name=''):  
    if friends_count == 1:
        text = '1 друг'
    elif 2 <= friends_count <= 4:
        text = str(friends_count) + ' друга'
    elif friends_count >= 5:
        text = str(friends_count) + ' друзей'
    if name == '':
        print('У тебя', text)
    else:
        print(name + ', у тебя', text)

print_friends_count(3, 'Артём')
print_friends_count(friends_count=7, name='Марина')
print_friends_count(6)
print_friends_count(4, name='Настя')

# Разбиение на функции
FRIENDS = ['Серёга', 'Соня', 'Дима', 'Алина', 'Егор']

def print_friends_count(friends_count):
    if friends_count == 1:
        print('У тебя 1 друг')
    elif 2 <= friends_count <= 4:
        print('У тебя ' + str(friends_count) + ' друга')
    elif friends_count >= 5:
        print('У тебя ' + str(friends_count) + ' друзей')

def process_query(query):
    if query == 'Сколько у меня друзей?':
        print("Привет, я Анфиса!")
        count = len(FRIENDS)
        print_friends_count(count)
    elif query == 'Кто все мои друзья?':
        print("Привет, я Анфиса!")
        print("Твои друзья:", ', '.join(FRIENDS))
    else:
        print("Привет, я Анфиса!")
        print("<неизвестный запрос>")
        
process_query('Сколько у меня друзей?')
process_query('Как меня зовут?')
process_query('Кто все мои друзья?')

# Счетчик
may_2017 = [24, 26, 15, 10, 15, 19, 10, 1, 4, 7, 7, 7, 12, 14, 17, 8, 9, 19, 21, 22, 11, 15, 19, 23, 15, 21, 16, 13, 25, 17, 19]
may_2018 = [20, 27, 23, 18, 24, 16, 20, 24, 18, 15, 19, 25, 24, 26, 19, 24, 25, 21, 17, 11, 20, 21, 22, 23, 18, 20, 23, 18, 22, 23, 11]

def comfort_count(temperatures):
    count = 0
    for temperature in temperatures:
        if 21 < temperature < 27:
            count += 1
    print('Количество комфортных дней в этом месяце:', count)

comfort_count(may_2017)  # узнаем, что было в мае 2017 г.
comfort_count(may_2018)  # узнаем, что было в мае 2018 г.

# Словари
friends_names = ['Аня', 'Коля', 'Лёша', 'Лена', 'Миша']
friends_cities = ['Владивосток', 'Красноярск', 'Москва', 'Обнинск', 'Чебоксары']

friends = {}
i = 0
for i in range(0,len(friends_names)):
    friends[friends_names[i]] =  friends_cities[i]
    i =+ 1
print (friends)
print ("Лена живёт в городе " + friends['Лена'])


# Еще Словари
def is_anyone_in(collection, city):
    if city in collection.values():  # если есть среди значений словаря collection 
        for name in collection:  # переберите все ключи словаря
            if city == collection[name]:  # если соответствующее ключу значение равно city
                print('В городе ' + city + ' живёт ' + name + '.')
    else:
        print('Пока никого.')

friends = {
    'Серёга': 'Омск', 
    'Соня': 'Москва', 
    'Дима': 'Челябинск', 
    'Алина': 'Хабаровск', 
    'Егор': 'Пермь'
}

is_anyone_in(friends, 'Хабаровск')

# И еще :)
# напишите здесь функцию print_shopping_list(),
# подобрав уникальные названия продуктов и сложив значения
def print_shopping_list(pizza, salad):
    pizza_set = set(pizza)
    salad_set = set(salad)
    full_list = pizza_set.union(salad_set)
    for i in full_list:
        if (i in pizza) and (i in salad):  
            total_value = pizza[i] + salad[i]
            print(i+':', total_value)
        elif i in pizza:
            print(i+':', pizza[i])
        elif i in salad:
            print(i+':', salad[i])
    
pizza = {'мука, кг': 1,
         'помидоры, кг': 1.5,
         'шампиньоны, кг': 1.5,
         'сыр, кг': 0.8,
         'оливковое масло, л': 0.1,
         'дрожжи, г': 50}
salad = {'огурцы, кг': 1,
         'перцы, кг': 1,
         'помидоры, кг': 1.5,
         'оливковое масло, л': 0.1,
         'листья салата, кг': 0.4}

print_shopping_list(pizza, salad)

# Прототип запроса к базе данных
DATABASE = {
    'Серёга': 'Омск',
    'Соня': 'Москва',
    'Миша': 'Москва',
    'Дима': 'Челябинск',
    'Алина': 'Красноярск',
    'Егор': 'Пермь',
    'Коля': 'Красноярск'
}


def format_friends(friends_count):
    if friends_count == 1:
        return 'У тебя 1 друг'
    elif 2 <= friends_count <= 4:
        return 'У тебя ' + str(friends_count) + ' друга'
    elif friends_count >= 5:
        return 'У тебя ' + str(friends_count) + ' друзей'


def process_query(query):
    if query == 'Сколько у меня друзей?':
        count = len(DATABASE)
        return format_friends(count)
    elif query == 'Кто все мои друзья?':
        friends_string = ', '.join(DATABASE)
        return 'Твои друзья: ' + friends_string
    elif query == 'Где все мои друзья?':
        for i in DATABASE:
            database_values = set(DATABASE.values()) 
        return 'Твои друзья в городах: '+ ', '.join(database_values)
    else:
        return '<неизвестный запрос>'


def runner():
    print('Привет, я Анфиса!')
    print(process_query('Сколько у меня друзей?'))
    print(process_query('Кто все мои друзья?'))
    print(process_query('Где все мои друзья?'))


runner()

#  Метод split()
def check_query(query):
    query_list = query.split()
    if query_list[0].strip(",") == "Анфиса":
        return 'запрос к Анфисе'
    else:
        return 'запрос к кому-то ещё'

queries = [
    'Анфиса, сколько у меня друзей?',
    'Андрей, ну где ты был?',
    'Андрей, ну обними меня скорей!',
    'Анфиса, кто все мои друзья?'
]

for q in queries:
    result = check_query(q)
    print(q, '-', result)

# f-строки
def calc_stat(listened):  # от англ. calculate statistics, посчитать статистику
    N = len(listened)        # длинна списка
    total_s = 0
    for i in range(0, len(listened)): 
        total_s = total_s + listened[i]
    print(total_s)
    M = total_s // 60
    S = total_s % 60
    return f'Вы прослушали {N} песен, общей продолжительностью {M} минут и {S} секунд.'

        
print(calc_stat([193, 148, 210, 144, 174, 159, 163, 189, 230, 204]))


# Запросы к друзьям
DATABASE = {
    'Сергей': 'Омск',
    'Соня': 'Москва',
    'Миша': 'Москва',
    'Дима': 'Челябинск',
    'Алина': 'Красноярск',
    'Егор': 'Пермь',
    'Коля': 'Красноярск'
}

def format_count_friends(count_friends):
    if count_friends == 1:
        return '1 друг'
    elif 2 <= count_friends <= 4:
        return f'{count_friends} друга'
    else:
        return f'{count_friends} друзей'


def process_anfisa(query):
    if query == 'сколько у меня друзей?':
        count_string = format_count_friends(len(DATABASE))
        return f'У тебя {count_string}'
    elif query == 'кто все мои друзья?':
        friends_string = ', '.join(DATABASE.keys())
        return f'Твои друзья: {friends_string}'
    elif query == 'где все мои друзья?':
        unique_cities = set(DATABASE.values())
        cities_string = ', '.join(unique_cities)
        return f'Твои друзья в городах: {cities_string}'
    else:
        return '<неизвестный запрос>'

    
def process_friend(name, query):    
    if name in DATABASE:
        if query == 'ты где?':
            return f'{name} в городе {DATABASE[name]}'
        else:
            return '<неизвестный запрос>'
    else: 
        return f'У тебя нет друга по имени {name}'
    
def process_query(query):
    query_name_split = query.split(', ')
    if query_name_split[0] == "Анфиса":
        return process_anfisa(query_name_split[1])
    else:
        return process_friend(query_name_split[0], query_name_split[1])


def runner():
    queries = [
        'Анфиса, сколько у меня друзей?',
        'Анфиса, кто все мои друзья?',
        'Анфиса, где все мои друзья?',
        'Анфиса, кто виноват?',
        'Коля, ты где?',
        'Соня, что делать?',
        'Антон, ты где?'
        
    ]
    for query in queries:
        print(query, '-', process_query(query))


runner()

# Библиотека datetime и формат UTC
import datetime as dt

DATABASE = {
    'Соня': 'Москва',
    'Дима': 'Челябинск',
    'Алина': 'Красноярск',
    'Егор': 'Пермь'
}

UTC_OFFSET = {
    'Санкт-Петербург': 3,
    'Москва': 3,
    'Самара': 4,
    'Новосибирск': 7,
    'Красноярск': 7
}


def what_time(friend):
    friends_city = DATABASE[friend]
    city_time = dt.datetime.utcnow() + dt.timedelta(hours=UTC_OFFSET[friends_city])
    return city_time 


print(what_time('Алина'))

