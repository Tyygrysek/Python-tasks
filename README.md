from random import*
word_list = ['тарелка', 'стул', 'окно', 'крокодил', 'наушники', 'принтер', 'локомотив', 'подшипник', 'проспект', 'монитор']
def get_word():
  word = word_list[randint(0, len(word_list) - 1)].upper()
  return word
# функция получения текущего состояния
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
  word_completion = '_' * len(get_word())
  guessed_letters = []               # список уже названных букв
  guessed_words = []
  while tries != 0:
    print(display_hangman(tries))
    print(word_completion)
    guess = input('Введите букву или слово целиком').upper()
    if len(guess) > 1:
      guessed_words.append(guess)
    else:
      guessed_letters.append(guess)
play(get_word())
