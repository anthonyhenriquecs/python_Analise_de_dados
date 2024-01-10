# python_Analise_de_dados

import pandas as pd

tabela = pd.read_csv("cancelamentos_sample.csv")
#visualizar a base de dados e limpar cagadas


#(Informações que nao te ajudam, atrapalham!)
#1°cagada- colunas inuteis
tabela = tabela.drop(columns="CustomerID")
display(tabela)
#2°cagada- valores vazios

#Corrigir as cagadas da base de dados
display(tabela.info())
#Valores vazios
#excluir linhas com valores vazios
tabela = tabela.dropna()
display(tabela.info())
