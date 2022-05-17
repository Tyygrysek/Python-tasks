
phrase = input('Введите фразу, которую необходимо шифровать / дешифровать:' '\n')
words = phrase.split()
spisok_itog1 = []
for h in range(len(words)):
  counter = 0
  for c in range(len(words[h])):
    if words[h][c].isalpha() == True:
      counter += 1
spisok = ''
for h in range(len(words)):
  for c in range(len(words[h])):
    if words[h][c].isalpha() == True:    
      let_ind = ord(words[h][c])
      if ord(words[h][c].lower()) + counter > 122:
        let_ind = let_ind - 26 + counter  
        spisok.append(chr(let_ind))
      else:
        let = chr(ord(words[h][c]) + counter)
        spisok.append(let)
    else:
      spisok.append(words[h][c])
print(spisok)
