#ver 3
import random
print('Добро пожаловать в числовую угадайку')
def is_valid(n):    # проверка на соответствие введенного значения условию
    return n.isdigit() and 1 <= int(n) <= 100

def input_num():    #ввод данных
  while True:
    guess = input()
    if is_valid(guess) == False:
      print('А может быть все-таки введем целое число от 1 до 100?')
    else:
      return int(guess)

def compare_num(left_num, right_num):    # Сравнение введенного значения с загаданным
  num = random.randint(left_num, right_num)
  total = 0
  while True: 
    n = input_num()
    total += 1
    if n > num:
      print('Ваше число больше загаданного, попробуйте еще разок')
    elif n < num:
      print('Ваше число меньше загаданного, попробуйте еще разок')
    else:
      print('Вы угадали число за', total, 'попыток. Поздравляем!')
      break

def continue_game():    # Предложение продолжить игру
  ans = input('Хотите продолжить ("д"/"н")?')
  while True:
    if ans in ('y', 'д', 'n', 'н'):
      return True
    else:
      print('До скорых встреч!')
      return False

def game():   # Запуск игры
  while True:
    print('Укажите диапазон угадаваемых чисел ( от 1 до 100): ')
    x, y = input_num(), input_num()
    if x > y:
      x, y = y, x
    print('Попоробуйте угадать число в диапазоне от', x, 'до', y)
    compare_num(x, y)
    if continue_game():
      continue
    else: 
      break 
game()
