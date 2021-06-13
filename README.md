# Programinha-de-empregos
Opa, sou o Gustavo tenho 15 anos e eu estou fazendo um programa em python que faz buscas de emprego.


import requests

from bs4 import BeautifulSoup

from googlesearch import search




print("\033[36m Obrigado Por usar nosso programa.\033[m")

print("\033[36m Este programa foi desenvolvido por:\033[m")

print("\033[32m Desenvolvedor: Gustavo de Carvalho Cypriano \033[m- \033[34m email: gustavo.de.carvalho.cypriano@gmail.com\033[m")

print("\033[31m A idéia e créditos do programa támbem vão a Lucas Franco da Silva \033[m- \033[34m email: lucasf51@hotmail.com\033[m")

print("------------------------------------------------------------------------------------------------------")

emprego = input("\033[34m Digite sua profissão\033[m : ")

cidade = input("\033[34m Digite Cidade/Estado \033[m : ")

adicionais = input("\033[34m Digite informações adicionais \033[m: ")

homeoffice = input("\033[34m Você gostaria de trabalhar em casa ou presencial : \033[m")

for site in search(f'"Vagas emprego {emprego} {cidade} {adicionais} {homeoffice}" Google', stop=10):

        page = requests.get(site)
        
        soup = BeautifulSoup(page.content, "html.parser")
        
        print(site)
        
        resultado = soup.find("h1")
        
        if resultado:
        
                print(resultado.text.strip())


while (site == emprego,cidade,adicionais,homeoffice):

        print("\033[0:34m Recomeçando o PROGRAMA... \033[m")
        
        print("\033[0:34m Caso queria Olhar os novos sites, utilize nomes nas pesquisas diferentes \033[m")

        emprego = input("\033[34m Digite sua profissão: \033[m  ")
        
        cidade = input("\033[34m Digite Cidade/Estado: \033[m  ")
        
        adicionais = input("\033[34m Digite informações adicionais:  \033[m ")
        
        homeoffice = input("\033[34m Você gostaria de trabalhar em casa ou presencial : \033[m")

        for site in search(f'"Vagas emprego {emprego} {cidade} {adicionais} {homeoffice}" Google', stop=20):

                page = requests.get(site)
                
                soup = BeautifulSoup(page.content, "html.parser")
                
                print(site)
                
                resultado = soup.find("h1")
                
                if resultado:
                
                        print(resultado.text.strip())
        else:
                print("\033[0:30:41m Recomeçando o PROGRAMA...\033[m ")
                
                print("\033[0:30:41m Caso queria Olhar os novos sites, utilize nomes nas pesquisas diferentes \033[m")




