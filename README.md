# hello-world
This is short description
import random
a = random.randint(1, 100)
print('Добро пожаловать в числовую угадайку')
def is_valid(n):

 

    return n.isdigit() and 1 <= int(n) <= 100
pass

 

while True:
    n = input('Введите число от 1 до 100:')
    if is_valid(n) == False:
        print('А может быть все-таки введем целое число от 1 до 100?')


    else:
        n = int(n)
        if n == a:
            print('Вы угадали, поздравляем!')
            break

         elif n < a:
             print('Ваше число меньше загаданного, попробуйте еще разок')
            
        elif n > a:
            print('Ваше число больше загаданного, попробуйте еще разок')
            
print('Спасибо, что играли в числовую угадайку. Еще увидимся...')
