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
