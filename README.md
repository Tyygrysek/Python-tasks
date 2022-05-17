moove = input('В каком напрвлении проведем шифрование: l = налево, r = направо' '\n')
leng = input('Выберете язык, на котором будет необходимо зашифровать текст: ru = русский, en = английский' '\n')
k = int(input('Укажите шаг сдвига:' '\n'))
phrase = input('Введите фразу, которую необходимо шифровать / дешифровать:' '\n')
def ru_phrase_r():
  spisok = ''
  for i in range(len(phrase)):
    let_ind = ord(phrase[i])
    if phrase[i].isalpha() == True:
      if ord(phrase[i].lower()) + k > 1103:
        let_ind = let_ind - 32 + k  
        spisok += chr(let_ind)
      else:
        let = chr(ord(phrase[i]) + k)
        spisok += let     
    else:
      spisok += phrase[i]
  print(spisok)

def en_phrase_r():
  spisok = ''
  for i in range(len(phrase)):
    let_ind = ord(phrase[i])
    if phrase[i].isalpha() == True:
      if ord(phrase[i].lower()) + k > 122:
        let_ind = let_ind - 26 + k  
        spisok += chr(let_ind)
      else:
        let = chr(ord(phrase[i]) + k)
        spisok += let     
    else:
      spisok += phrase[i]
  print(spisok)
def ru_phrase_l():
  spisok = ''
  for i in range(len(phrase)):
    let_ind = ord(phrase[i])
    if phrase[i].isalpha() == True:
      if ord(phrase[i].lower()) - k < 1072:
        let_ind = let_ind - k + 32  
        spisok += chr(let_ind)
      else:
        let = chr(ord(phrase[i]) - k)
        spisok += let     
    else:
      spisok += phrase[i]
  print(spisok)
def en_phrase_l():
  spisok = ''
  for i in range(len(phrase)):
    let_ind = ord(phrase[i])
    if phrase[i].isalpha() == True:
      if ord(phrase[i].lower()) - k < 97:
        let_ind = let_ind - k + 26  
        spisok += chr(let_ind)
      else:
        let = chr(ord(phrase[i]) - k)
        spisok += let     
    else:
      spisok += phrase[i]
  print(spisok)

def shifr():

  if moove == 'r':
    if leng == 'en':
      en_phrase_r()
    elif leng == 'ru':
      ru_phrase_r()
    else:
      print('Некорректно введен язык')
  elif moove == 'l':
    if leng == 'en':
      en_phrase_l()
    elif leng == 'ru':
      ru_phrase_l()
    else:
      print('Некорректно введен язык')
  else: 
    print('Некорректно введено направление')
def full_spisok_en():
  phrase = input('Введите фразу, которую необходимо шифровать / дешифровать:' '\n')
  for k in range(25):
    spisok = ''
    for i in range(len(phrase)):
      let_ind = ord(phrase[i])
      if phrase[i].isalpha() == True:
        if ord(phrase[i].lower()) - k < 97:
          let_ind = let_ind - k + 26  
          spisok += chr(let_ind)
        else:
          let = chr(ord(phrase[i]) - k)
          spisok += let     
      else:
        spisok += phrase[i]
    print(spisok)
  
shifr()
