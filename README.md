'''moove = input('В каком напрвлении проведем шифрование: left = налево, right = направо' '\n')
leng = input('Выберете язык, на котором будет необходимо зашифровать текст: ru = русский, en = английский' '\n')'''
k = int(input('Укажите шаг сдвига:' '\n'))
phrase = input('Введите фразу, которую необходимо шифровать / дешифровать:' '\n')
def ru_phrase():
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
ru_phrase()
