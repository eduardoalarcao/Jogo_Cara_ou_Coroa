# Jogo_Cara_ou_Coroa
# Uma versão do jogo de cara ou coroa em python
import random
import time 
# Funções necessárias para o jogo

def face_da_moeda_adversario(a):
  a = 0
  print(" ")
  face_adversario = random.randint(0,1)
  if face_adversario == 0:
    return "face do adversario: cara; sua face: coroa"
  else:
    return "face do adversario: coroa; sua face: cara" 

def sua_face_da_moeda(b):
  b = 1
  escolher = True
  while escolher:
    escolher = False
    print(" ")
    sua_face = input("Qual face da moeda você escolhe? ")
    if sua_face == "cara":
      print(" ")
      return "sua face: cara; face do adversario: coroa"
    elif sua_face == "coroa":
      print(" ")
      return "sua face: coroa; face do adversario: cara"
    else:
      resposta = input("Não entendi. Você pode enviar outra resposta? ")
      if resposta in ["sim","posso","sim,posso","sim,eu posso","sim, posso","sim, eu posso","sim posso","sim eu posso"]:
        escolher = True
      else:
        print(" ")
        print("Ok. Acabou o jogo")
        escolher = False
  return " "      

def jogando_moeda(c):
  c = 2
  if informação in ["sua face: cara; face do adversario: coroa","face do adversario: coroa; sua face: cara"]:
    print(" ")
    print("A sua face da moeda é cara")
  elif informação in ["sua face: coroa; face do adversario: cara", "face do adversario: cara; sua face: coroa"]:
    print(" ")
    print("A sua face da moeda é coroa")
  global resultado
  girar = random.randint(0,1)
  if girar == 0:
    resultado = "cara"
  else:
    resultado = "coroa"
  print(" ")
  time.sleep(3)
  return resultado

def resultado_do_jogo(d):
  d = 3 
  if informação in ["sua face: cara; face do adversario: coroa","face do adversario: coroa; sua face: cara"] and resultado == "cara":
    print(" ")
    print("Parabéns, Você ganhou o jogo!")
  elif informação in ["sua face: coroa; face do adversario: cara", "face do adversario: cara; sua face: coroa"] and resultado == "coroa":
    print(" ")
    print("Parabéns, Você ganhou o jogo!")
  else:
    print(" ")
    print("Vish, você perdeu o jogo! Bom pro seu adversário.")
  print(" ")  
  time.sleep(1.5)
  return "Fim do jogo. Espero que você tenha se divertido!" 

def código_do_jogo(e):
    print(" ")
    print("Tudo pronto! Vamos começar o jogo.")
    moeda = input("Você está preparado? ")
    if moeda in ["sim","estou","sim,estou","sim,eu estou","sim, estou","sim, eu estou","sim estou","sim eu estou","eu estou","tô","to","eu to","eu tô"]:
      print(jogando_moeda(2))
      time.sleep(1.5)
      print(resultado_do_jogo(3))
    else:
      print(" ")
      print("Entendo, tudo bem. Volte para jogar quando quiser!")
    return " "

def pergunta_principal(f):
  global iniciar
  decidir = True
  while decidir:
    decidir = False
    jogo = input("Você quer jogar cara ou coroa? ")
    if jogo in ["sim","quero","sim,quero","sim,eu quero","sim, quero","sim, eu quero","sim quero","sim eu quero","eu quero"]:
      iniciar = True
    elif jogo in ["não","não quero","nao","nao quero","nãoquero","naoquero"]:
      print(" ")
      print("Que pena, esse jogo é tão legal! Tudo certo.")
      iniciar = False
    else:
      resposta1 = input("Não entendi. Você pode enviar outra resposta? ")
      if resposta1 in ["sim","posso","sim,posso","sim,eu posso","sim, posso","sim, eu posso","sim posso","sim eu posso"]:
        decidir = True
        iniciar = False
      else:
        print(" ")
        print("Ok. Acabou o jogo")
        iniciar = False
    return " "

# Código do jogo "cara ou coroa" - versão completa 

print(" ")
print("ATENÇÃO! Para o bom funcionamento do jogo, não use 'espaço' no início ou no final das suas respostas")
print(" ")
print(pergunta_principal(6))
while iniciar:
  iniciar = False
  escolha = input("Você quer escolher a sua face da moeda? ")
  if escolha in ["sim","quero","sim,quero","sim,eu quero","sim, quero","sim, eu quero","sim quero","sim eu quero"]:        
    informação = sua_face_da_moeda(1)
    print(informação)
    continuar = True
    if informação in ["sua face: cara; face do adversario: coroa","face do adversario: coroa; sua face: cara","sua face: coroa; face do adversario: cara", "face do adversario: cara; sua face: coroa"]:
      print(código_do_jogo(5))
    else:
      print(" ")  
  elif escolha in ["não","não quero","nao","nao quero","nãoquero","naoquero"]:
    informação = face_da_moeda_adversario(0)    
    print(informação)
    print(código_do_jogo(5))
    continuar = True
  else:
    resposta2 = input("Não entendi. Você pode enviar outra resposta? ")
    if resposta2 in ["sim","posso","sim,posso","sim,eu posso","sim, posso","sim, eu posso","sim posso","sim eu posso"]:
        iniciar = True
        continuar = False
    else:
      print(" ")
      print("Ok. Acabou o jogo")
      iniciar = False
      continuar = False
  while continuar:
      continuar = False
      time.sleep(2)
      repetir = input("Quer jogar mais uma vez? ")
      if repetir in ["sim","quero","sim,quero","sim,eu quero","sim, quero","sim, eu quero","sim quero","sim eu quero"]:
        print(" ")
        iniciar = True
      else:
        print(" ")
        print("Ok. Volte para jogar quando quiser!")
        iniciar = False
