# Ransomware
Desafio 

Descriptografia de Arquivos Usando Python e Kali Linux
Objetivo:
Reverter o processo de criptografia de um arquivo, tornando-o novamente acessível em formato legível.


Ferramentas Necessárias:
Kali Linux: Um sistema operacional focado em segurança.
Site oficial do Kali Linux(https://www.kali.org/)

Python: Linguagem de programação versátil para automação e scripts.
Site oficial do Python(https://www.python.org/)

Editor NANO: Usado neste exemplo para criar e executar o código.
Alternativamente, outras opções como myCompiler ou CMD também são válidas.
Guia básico sobre o NANO(https://medium.com/@habbema/tutorial-do-nano-3e6aec905213)


Pontos Relevantes:
O mesmo algoritmo e chave usados para criptografar o arquivo devem ser aplicados na descriptografia.
Este material é complementar ao repositório Python Encrypt File.
O script apresentado é básico e pode ser aprimorado, como incluir a seleção automática do arquivo.

Comandos para instalação no Kali Linux:

bash

sudo apt-get update && sudo apt-get upgrade
sudo apt install python3-pyaes

Procedimento Resumido:
Acessar o terminal (ou CMD) do Kali Linux.
Abrir o editor NANO com o comando nano.
Escrever o script que:
Abre o arquivo criptografado.
Define a chave para descriptografia.
Exclui o arquivo original criptografado.
Cria o arquivo descriptografado.
Salvar o script e executá-lo para descriptografar o arquivo.

Detalhamento das Etapas:
Acessar o terminal
No Kali Linux, abra o terminal usando o atalho ou menu do sistema.

Iniciar o editor NANO
Digite nano no terminal para abrir o editor de texto.

Importar bibliotecas
No início do script, inclua:

os: Para interação com o sistema operacional.
pyaes: Algoritmo de criptografia utilizado no exemplo.
Criação do arquivo .py
Escolha um nome apropriado, como decrypt_script.py, e comece a escrever o código.

Escrever o script:

import os
import pyaes

## abrir o arquivo criptografado
file_name = "teste.txt.ransomwaretroll"
file = open(file_name, "rb")
file_data = file.read()
file.close()

## chave para descriptografia
key = b"testeransomwares"
aes = pyaes.AESModeOfOperationCTR(key)
decrypt_data = aes.decrypt(file_data)

## remover o arquivo criptografado
os.remove(file_name)

## criar o arquivo descriptografado
new_file = "teste.txt"
new_file = open(f'{new_file}', "wb")
new_file.write(decrypt_data)
new_file.close()

No NANO, use Ctrl + O para salvar e Ctrl + X para sair.
Para executar, use o comando:

python3 decrypt_script.py
