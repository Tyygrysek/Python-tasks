from random import*
word_list = ['тарелка', 'стул', 'окно', 'крокодил', 'наушники', 'принтер', 'локомотив', 'подшипник', 'проспект', 'монитор']
def get_word():
  word = word_list[randint(0, len(word_list) - 1)].upper()
  return word
# функция получения текущего состояния
def print_word(word_, list_):
  for c in word_:
    if c in list_:
      print(c, end ='')
    else: 
      print('_', end = '')
  print()
      
def display_hangman(tries):
    stages = [  # финальное состояние: голова, торс, обе руки, обе ноги
                '''
                   --------
                   |      |
                   |      O
                   |     \\|/
                   |      |
                   |     / \\
                   -
                ''',
                # голова, торс, обе руки, одна нога
                '''
                   --------
                   |      |
                   |      O
                   |     \\|/
                   |      |
                   |     / 
                   -
                ''',
                # голова, торс, обе руки
                '''
                   --------
                   |      |
                   |      O
                   |     \\|/
                   |      |
                   |      
                   -
                ''',
                # голова, торс и одна рука
                '''
                   --------
                   |      |
                   |      O
                   |     \\|
                   |      |
                   |     
                   -
                ''',
                # голова и торс
                '''
                   --------
                   |      |
                   |      O
                   |      |
                   |      |
                   |     
                   -
                ''',
                # голова
                '''
                   --------
                   |      |
                   |      O
                   |    
                   |      
                   |     
                   -
                ''',
                # начальное состояние
                '''
                   --------
                   |      |
                   |      
                   |    
                   |      
                   |     
                   -
                '''
    ]
    return stages[tries]

def play(word):
  tries = 6
  print('Давайте играть в угадайку слов!')
  guessed = False    # сигнальная метка
  word_completion = '_' * len(word)
  guessed_letters = []               # список уже названных букв
  guessed_words = []
  print(display_hangman(tries))
  print(word_completion)
  print(word)
  while True:
    guess = input('Введите букву или слово целиком' '\n').upper()
    if not guess.isalpha:
      print('Нужно ввести букву или символ')
      continue
    if guess in guessed_letters or guess in guessed_words:
      print('Уже было!')
    if len(guess) > 1:
      if guess == word:
        print('You Win!')
        break
      else:
        guessed_words.append(guess)
        tries -= 1
        print(display_hangman(tries))
        print(f'Неправильно! У тебя осталось {tries} попыток')
        print_word(word, guessed_letters)
        if tries == 0:
          print(f'Вы не смогли угадать слово: {word}')
          break
        continue
      
        print(display_hangman(tries))        
    if guess.upper() in word:
      guessed_letters.append(guess)
      for c in word:
        if c not in guessed_letters:
          print('Угадали букву')
          print_word(word, guessed_letters)
          guessed = False
          break
        guessed = True
      if guessed:    
        print_word(word, guessed_letters)
        print('Поздравляем, вы угадали слово! Вы победили!')
        break
    else:
      guessed_letters.append(guess)
      tries -= 1
      print(f'Не верно, осталось попыток {tries}')
      print(display_hangman(tries))
      print_word(word, guessed_letters)
    if tries == 0:
      print(f'Вы не смогли угадать слово: {word}')
      break
      
play(get_word())

