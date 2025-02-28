# marioti.py
import os
import sys

def criar_diretorios(diretorios):
    for dir_name in diretorios:
        if not os.path.exists(dir_name):
            os.makedirs(dir_name)
            print(f'Diretório "{dir_name}" criado!')
        else:
            print(f'Diretório "{dir_name}" já existe.')

def listar_diretorios():
    try:
        for dir_name in os.listdir():
            if os.path.isdir(dir_name):
                print(f" - {dir_name}")
    except OSError as e:
        print(f"Erro: {e}")

if __name__ == "__main__":
    if len(sys.argv) < 2:
        print("Uso: python script.py <dir1> <dir2> ...")
        sys.exit(1)

    criar_diretorios(sys.argv[1:])
    listar_diretorios()
