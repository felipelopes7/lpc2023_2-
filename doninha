import random
import string

def gerar_string_aleatoria(tamanho):
    return ''.join(random.choice(string.ascii_uppercase
    + ' ') for y in range(tamanho))

def calcular_aptidao(alvo, candidato):
    return sum(1 for a, b in zip(alvo, candidato) if a == b)

def mutar(antecessor , taxa_mutacao):
    return ''.join(
        c if random.random() > taxa_mutacao
        else random.choice(string.ascii_uppercase + ' ')
        for c in antecessor)
      
def algoritmo_weasel_dawkins(alvo, tamanho_populacao, taxa_mutacao):
    antecessor = gerar_string_aleatoria(len(alvo))
    geracao = 0

    while antecessor != alvo:
        descendente = [mutar(antecessor , taxa_mutacao)
        for x in range(tamanho_populacao)]
        antecessor = max(descendente, key = lambda
        descendente: calcular_aptidao(alvo, descendente))
        geracao += 1
        print(f"Geração {geracao}: {antecessor}")
      
    print(f"Alvo atingido em {geracao} gerações")

alvo_string = "METHINKS IT IS LIKE A WEASEL"
tamanho_populacao = 100
taxa_mutacao = 0.05
      
algoritmo_weasel_dawkins(alvo_string, tamanho_populacao, taxa_mutacao)
