from random import randint
answers = ['Бесспорно', 'Предрешено', 'Никаких сомнений', 'Определённо да', 'Можешь быть уверен в этом', 'Мне кажется - да', 'Вероятнее всего', 'Хорошие перспективы', 'Знаки говорят - да', 'Да', 'Пока неясно, попробуй снова', 'Спроси позже', 'Лучше не рассказывать', 'Сейчас нельзя предсказать', 'Сконцентрируйся и спроси опять', 'Даже не думай', 'Мой ответ - нет', 'По моим данным - нет', 'Перспективы не очень хорошие', 'Весьма сомнительно']
def print_name(name):
  if name:
    print('Привет, ', name.capitalize(), '!', sep = '' )
  else: 
    print('Тогда просто привет!')
def ans():
    ind = randint(0, len(answers) - 1)
    print(answers[ind])
def continue_game():   
  ans = input('Хотите задать еще один вопрос ("д"/"н")?' '\n')
  while True:
    if ans in ('y', 'д', 'Д', 'Y'):
      return True
    else:
      print('До скорых встреч!')
      return False
def magic_ball():
  while True:
    que = input('На какой вопрос ты хотел бы получить ответ?' '\n')
    ans()
    if continue_game():
      continue
    else:
      break
print('Привет Мир, я магический шар, и я знаю ответ на любой твой вопрос.')
nm = input('Как я могу к тебе обращаться?' '\n')
print_name(nm)
magic_ball()

