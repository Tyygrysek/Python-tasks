from random import randint
digits = '0123456789'
lowercase_letters = 'abcdefghijklmnopqrstuvwxyz'
uppercase_letters = 'ABCDEFGHIJKLMNOPQRSTUVWXYZ' 
punctuation = '!#$%&*+-=?@^_'
chars = ''
num_of_passw = int(input('Введи количество паролей, необходимых для генерации: '))
len_of_passw = int(input('Введи длину пароля: '))
def ign_num():
  ans = input('Включать ли цифры 0123456789 ?')
  if ans in ('д', 'Д', 'Y', 'y'):
    return True 
  else:
    return False
def ign_upp_lett():
  ans = input('Включать ли прописные буквы ABCDEFGHIJKLMNOPQRSTUVWXYZ?')
  if ans in ('д', 'Д', 'Y', 'y'):
    return True 
  else:
    return False
def ign_low_lett():
  ans = input('Включать ли строчные буквы abcdefghijklmnopqrstuvwxyz?')
  if ans in ('д', 'Д', 'Y', 'y'):
    return True 
  else:
    return False
def ign_symb():
  ans = input('Включать ли символы !#$%&*+-=?@^_?')
  if ans in ('д', 'Д', 'Y', 'y'):
    return True 
  else:
    return False
def ign_rep():
  ans = input('Исключать ли неоднозначные символы il1Lo0O?')
  if ans in ('д', 'Д', 'Y', 'y'):
    return True 
  else:
    return False
if ign_num():
  chars += digits
if ign_upp_lett():
  chars += uppercase_letters
if ign_low_lett():
  chars += lowercase_letters
if ign_symb():
  chars += punctuation
if ign_rep():
  for c in 'il1Lo0O':
    chars = chars.replace(c, '')
def generate_password(length, chars):
  for i in range(num_of_passw):
    passw = ''
    for j in range(length):
      passw += chars[randint(1, len(chars) - 1)]
    print(passw)

generate_password(len_of_passw, chars)
