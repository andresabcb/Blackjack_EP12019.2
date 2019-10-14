# desabix
from random import shuffle
import os

def embaralha_cartas(lista):
    cartas=lista[:]
    shuffle(cartas)
    return cartas

def retorna_carta(lista_cartas):
    carta=int(lista_cartas[0])
    del(lista_cartas[0])
    return carta

#def clear():
    #if os.:
        

#def reiniciar_jogo():
    #clear()
    
    

k = 10
j = 10
q = 10
#primeiro programa 
deck_de_cartas = [2,3,4,5,6,7,8,9,10,'k','j','q','a']*4
saldo_inicial=100
valor_apostado=int(input('Você possui {0} dólares. Qual será o valor da sua aposta? (mínimo: 15) '.format(saldo_inicial)))
saldo=saldo_inicial-valor_apostado

print(deck_de_cartas)

if valor_apostado>=15 and valor_apostado<=saldo:
    cartas_embaralhadas=(embaralha_cartas(deck_de_cartas))
    print(embaralha_cartas(deck_de_cartas))
    carta1=retorna_carta(cartas_embaralhadas)
    carta2=retorna_carta(cartas_embaralhadas)
    soma_de_cartas=carta1+carta2
#cartas iniciais do usuário
    print('Suas cartas iniciais são: {0} e {1}'.format(carta1,carta2))

    print(soma_de_cartas)

    if soma_de_cartas==21:
        saldo=valor_apostado*2.5+saldo
        print('Você ganhou o jogo (Blackjack) e tem agora {0}'.format(valor_apostado))
        
    while soma_de_cartas<21:
        escolha=input('Você deseja parar ou continuar? ')
        if escolha=='parar':
            print('Você acabou com {0} reais'.format(saldo))
        elif escolha=='continuar' or escolha=='Continuar':
            nova_carta=retorna_carta(cartas_embaralhadas)
            soma_de_cartas+=nova_carta
            print('Suas cartas agora são {0}, {1} e {2} (soma: {3}).'.format(carta1,carta2,nova_carta,soma_de_cartas))
