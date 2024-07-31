import random

def jogar_adivinhacao():
    print("Bem-vindo ao jogo de Adivinhação!")
    
    # Define o intervalo dos números
    intervalo_inferior = 1
    intervalo_superior = 100
    
    # Gera um número aleatório dentro do intervalo
    numero_secreto = random.randint(intervalo_inferior, intervalo_superior)
    
    tentativas = 0
    max_tentativas = 10
    
    print(f"Tente adivinhar o número entre {intervalo_inferior} e {intervalo_superior}.")
    
    while tentativas < max_tentativas:
        try:
            palpite = int(input("Digite seu palpite: "))
        except ValueError:
            print("Por favor, digite um número válido.")
            continue
        
        tentativas += 1
        
        if palpite < intervalo_inferior or palpite > intervalo_superior:
            print(f"Seu palpite está fora do intervalo! Escolha um número entre {intervalo_inferior} e {intervalo_superior}.")
        elif palpite < numero_secreto:
            print("Muito baixo!")
        elif palpite > numero_secreto:
            print("Muito alto!")
        else:
            print(f"Parabéns! Você adivinhou o número {numero_secreto} em {tentativas} tentativas.")
            break
    else:
        print(f"Você não conseguiu adivinhar o número. O número era {numero_secreto}.")

if __name__ == "__main__":
    jogar_adivinhacao()
