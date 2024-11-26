import random
import time

def print_pause(message, delay=1):
    """Função para imprimir mensagens com pausa."""
    print(message)
    time.sleep(delay)
def start_game():
    """Função principal do jogo."""
    print_pause("Bem-vindo ao jogo 'Escape da Matrix'!")
    print_pause("Você está preso em uma simulação.")
    print_pause("Seu objetivo é escapar tomando as decisões certas.")
    play_game()

def play_game():
    """Lógica principal do jogo."""
    print("\nVocê acorda em uma sala com três portas: Vermelha, Azul e Verde.")
    print("1. Abrir a porta Vermelha")
    print("2. Abrir a porta Azul")
    print("3. Abrir a porta Verde")
    
    choice = input("Digite o número da sua escolha: ")

    if choice == "1":
        red_door()
    elif choice == "2":
        blue_door()
    elif choice == "3":
        green_door()
    else:
        print_pause("Escolha inválida! Tente novamente.")
        play_game()

def red_door():
    print_pause("\nVocê abriu a porta Vermelha e encontrou um robô guardião.")
    action = input("Escolha: (1) Lutar ou (2) Fugir: ")
    if action == "1":
        if random.choice([True, False]):
            print_pause("Você derrotou o robô e encontrou uma saída! Parabéns!")
        else:
            print_pause("O robô te derrotou. Fim de jogo!")
    elif action == "2":
        print_pause("Você fugiu de volta para a sala inicial.")
        play_game()
    else:
        print_pause("Escolha inválida! Tente novamente.")
        red_door()

def blue_door():
    print_pause("\nVocê abriu a porta Azul e caiu em uma armadilha.")
    print_pause("Um quebra-cabeça aparece na sua frente.")
    puzzle = input("Resolva: Quanto é 7 x 6? ")
    if puzzle == "42":
        print_pause("Resposta correta! Você encontrou a saída. Parabéns!")
    else:
        print_pause("Resposta errada! Você está preso na armadilha. Fim de jogo!")

def green_door():
    print_pause("\nVocê abriu a porta Verde e encontrou uma sala vazia.")
    print_pause("No centro, há um botão grande e vermelho.")
    action = input("Escolha: (1) Apertar o botão ou (2) Voltar: ")
    if action == "1":
        print_pause("O botão desativou a simulação. Você escapou! Parabéns!")
    elif action == "2":
        print_pause("Você voltou para a sala inicial.")
        play_game()
    else:
        print_pause("Escolha inválida! Tente novamente.")
        green_door()

if _name_ == "_main_":
    start_game()
