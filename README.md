# Desavios
opcao = 0
cliente = []
registro = []
deletados = []
nome = ''
while ( opcao != 9 ):     
    print('+-----------------------------------------------------------------------------------------+') 
    print('|                     Escolhar uma das Opições Abaixo                                     |')    
    print('| 1 - Registar cliente | 2 - Excluir  | 3 - Listar Clientes    | 4 - Cambio               |')
    print('| 5 - Ordenar          | 6 - Inverter | 7 - Total de Clientes  | 8 - listar relatórios    |')
    print('|                                 | 9 - Sair |                                            |')
    print('+-----------------------------------------------------------------------------------------+')
    opcao = int(input('Operação Desejada: '))
    if ( opcao == 1 ):
        nome = input('Adicionar cliente: ')
        if (nome in cliente ):
            print(nome + ' ja esta cadastrado.')
        else:            
            cliente.append(nome)            
            print(nome + ' cadastrado com sucesso.')
    elif ( opcao == 2):
        nome = input('Nome do cliente que deseja excluir: ')
        if ( nome in cliente):
            deletados.append(nome)
            cliente.remove(nome)            
            print(nome + ' renovido com sucesso!')
        else:
            
            print(nome + ' não esta cadastrado!')
    elif( opcao == 3 ):              
        for x in range(0,len(cliente)):
            print(cliente[x])        
    elif( opcao == 4 ):
        nome = input('Nome do cliente registrado: ')
        if (not (nome in cliente ) ):            
            print(nome + ' Cliente não esta cadastrado.')
            print('Por favor registar na opição 1 ')
        else:  
            usuarionome = nome          
            moeda_origem = str(input('Informe a moeda de origem: '))
            valor_origem = float(input('Informe o valor em ' + moeda_origem + ': '))
            moeda_destino = str(input('Informe a moeda de destino: '))
            valor_destino = float(input('Informe a cotação do ' + moeda_destino + ': ' ))
            conversão = valor_origem / valor_destino
            registro.append('A ' + usuarionome + ' vai Converter ' + moeda_origem + ': ' + str(valor_origem) + ' para '  + moeda_destino  + ' a conversão {:.2f} Sobre a Taxa de {:.2f}  '.format(conversão,(conversão % 10)))
            print('A ' + usuarionome + ' vai Converter ' + moeda_origem + ': ' + str(valor_origem) + ' para '  + moeda_destino  + ' a conversão {:.2f} Sobre a Taxa de {:.2f}  '.format(conversão,(conversão % 10)))
                
    elif( opcao == 5 ):
        cliente.sort()        
        print('Lista  de cliente ordenada de forma crecente.')
    elif( opcao == 6 ):
        cliente.reverse()      
        print('Lista de cliente ordenada de forma invertida.')
    elif( opcao == 7 ):
        
        print(len(cliente))
    elif(opcao == 8 ):
        print('1- Para Estorico de cambio')
        print('2- Para Estorico de Clientes Deletados')
        opre = int(input())
        if(opre == 1):            
            for x in range(0,len(registro)):
                print(registro[x])
        elif(opre == 2 ):             
            for x in range(0,len(deletados)):
                print(deletados[x])
        else:            
            print('Opição invalida''\n''Redirecionado para o menu inicial')
    elif( opcao == 9 ):
        print('Tenha um bom dia')
        break
    else:
        print('opição invalida.')
# Observação para poder fazer os passa a seguir você tem quer ter instalado python em seu computador tonar o 
# arquivo um executável primeiro vamos abaixar o módulo PyInstaller pelo cmd digitado pip install pyinstaller 
# depois usado o cmd você vai ter que ir ate onde esta o arquivo com o código python depois usado o cmd vc 
# usara o comando pyintaller com o nome do arquivo depois de torna o arquivo exe ele vai criar mais pasta dai 
# e só você ir ate dist nome do arquivo que foi dado e dentro dessa pasta vai encontra o arquivo exe EX: cd desktop pyintaller nome_aquivo.py 
# Observação para poder fazer os passa a seguir você tem quer ter instalado python em seu computador para 
# complinar aquivos python primeiro vamos abaixar o módulo PyInstaller pelo cmd digitado 
# pip install pyinstaller depois navegue até o local do seu script Python depois use Type " nome_do_aquivo.py 
# python O interpretador Python irá compilar o script O programa vai abri uma tela 
# Em meu trabalho tem 9 opção que podem ser escolhidas 1 para cadastras a pessoas 2 para  excuir 3 lista quem esta cadastrado
# 4 é a opção onde e feito o calculo do cambio 5 e 6 são para ordenar a lista de outra forma 7 para mostra um total de
# pessoas cadastradas e 8 para mostra um relatorio de cambio e de pessoas que foram excluidas do sistema e 9 para sair 
