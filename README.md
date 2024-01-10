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

#Analise inicial dos cancelamentos

#Quantas cancelaram e quantas não cancelaram
display(tabela["cancelou"].value_counts())

#em percentual
display(tabela["cancelou"].value_counts(normalize=True))

#Analise das causas de cancelamento(como as colunas impactam no cancelamento)
#!pip install plotly
#grafico/dashboards
import plotly.express as px

#cria o grafico
for coluna in tabela.columns:
    grafico = px.histogram(tabela, x=coluna, color="cancelou")

    #exibe o grafico
    grafico.show()
    
