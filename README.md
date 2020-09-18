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
