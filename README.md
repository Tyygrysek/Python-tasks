def duplicate_count(text):
  counter = 0
  s = 0
  spis = []
  for i in range(len(text)):
    s = 0
    for j in range(i+1, len(text)):
      if text[i] == text[j] and text[i] not in spis:
        s += 1
      if s > 1:
        counter += 1
        spis.append(text[i])
        break
        
      
  return counter
