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
    else:
        print("Привет, я Анфиса!")
        print("<неизвестный запрос>")
        
process_query('Сколько у меня друзей?')
process_query('Как меня зовут?')
