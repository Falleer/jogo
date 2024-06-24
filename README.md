# Importar módulos necessários
import random

# Definir a palavra secreta
palavra_secreta = "e se a gente for mais a fundo?"

# Criar uma lista para armazenar as letras já tentadas
letras_tentadas = []

# Criar uma lista para armazenar as letras corretas
letras_corretas = ["_"] * len(palavra_secreta)

# Definir o número de tentativas
tentativas = 10

# Loop principal do jogo
while tentativas > 0:
    # Mostrar a palavra secreta com as letras corretas
    print(" ".join(letras_corretas))

    # Pedir ao usuário para tentar uma letra
    letra = input("Tente uma letra: ")

    # Verificar se a letra já foi tentada
    if letra in letras_tentadas:
        print("Você já tentou essa letra!")
    else:
        # Adicionar a letra às letras tentadas
        letras_tentadas.append(letra)

        # Verificar se a letra está na palavra secreta
        if letra in palavra_secreta:
            # Substituir a letra correta na palavra secreta
            for i in range(len(palavra_secreta)):
                if palavra_secreta[i] == letra:
                    letras_corretas[i] = letra
        else:
            # Decrementar o número de tentativas
            tentativas -= 1
            print("Erro! Você tem {} tentativas restantes.".format(tentativas))

    # Verificar se o usuário ganhou
    if "_" not in letras_corretas:
        print("Parabéns! Você ganhou!")
        break

# Se o usuário não ganhou, mostrar a palavra secreta
if tentativas == 0:
    print("Você perdeu! A palavra secreta era: {}".format(palavra_secreta))
