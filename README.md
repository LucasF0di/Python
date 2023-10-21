# Python
Exercicio criar um banco 

saldo = 1000
limite_saques = 3
saques_realizados = 0

while True:
    print("Escolha uma operação:")
    print("1. Depósito")
    print("2. Saque")
    print("3. Extrato")
    print("4. Sair")
    
    escolha = input("Digite o número da operação desejada: ")
    
    if escolha == "1":
        valor = float(input("Digite o valor do depósito: "))
        if valor > 0:
            saldo += valor
            print(f'Depósito de R${valor} realizado. Saldo atual: R${saldo:.2f}')
        else:
            print("Valor de depósito inválido.")
    
    elif escolha == "2":
        if saques_realizados < limite_saques:
            valor = float(input("Digite o valor do saque: "))
            if valor > 0 and valor <= saldo:
                saldo -= valor
                saques_realizados += 1
                print(f'Saque de R${valor} realizado. Saldo atual: R${saldo:.2f}')
            elif valor <= 0:
                print("Valor de saque inválido.")
            else:
                print("Saldo insuficiente.")
        else:
            print("Limite de saques atingido.")
    
    elif escolha == "3":
        print(f'Saldo atual: R${saldo:.2f}')
    
    elif escolha == "4":
        print("Saindo do sistema bancário.")
        break
    
    else:
        print("Escolha inválida. Por favor, escolha uma opção válida.")
