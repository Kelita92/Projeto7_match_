# Projeto7_match_
Este projeto consiste em um formulario de inscrições para um evento no periodo da noite.
Vagas = 50 
MoraEmSP = "SP"
Maioridade = +18
HorarioEvento = "noite"

# Função para cadastrar um participante
def cadastrar_participante():
    # Coleta das informações do participante
    print("Insira seu nome completo:")
    nome = input()
    print("Insira sua idade:")
    idade = int(input())
    print("Insira seu endereço:")
    endereco = input()
    print("Você reside no estado de São Paulo? (S/N)")
    reside_em_sp = input().lower()
    print("Horário do Evento? (manhã, tarde ou noite) ")
    HorarioEvento = input()
# Verifica se o participante atende a todas as condições
    if idade < 18:
        print("Você não é maior de idade.")
        return
    elif reside_em_sp != "s":
        print("Inscrição inválida.Você não reside no estado de São Paulo!")
        return
    elif HorarioEvento != "noite":
        print("Inscrição inválida, o evento ocorre a noite.")
        return

    # Verifica se ainda há vagas disponíveis
    vagas_disponiveis = Vagas - len(participantes)
    if Vagas == 0:
        print("As inscrições estão encerradas.")
        return

    # Cadastra o participante
    participantes.append({
        "nome": nome,
        "idade": idade,
        "endereco": endereco,
        "reside_em_sp": MoraEmSP,
        "HorárioEvento": HorarioEvento

    })
    print("Inscrição realizada com sucesso!")

# Lista de participantes
participantes = []

# Loop principal
while True:
    # Opções do menu
    print("Escolha uma Opção:")
    print("1 - Cadastrar participante")
    print("2 - Listar participantes")
    print("3 - Sair")

    # Escolha do usuário
    escolha = int(input())

    # Execução da opção escolhida
    if escolha == 1:
        cadastrar_participante()
    elif escolha == 2:
        for participante in participantes:
            print(participante)
    elif escolha == 3:
        break
