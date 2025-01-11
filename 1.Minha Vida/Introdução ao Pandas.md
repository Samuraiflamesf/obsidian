---
dg-publish: true
title: Introdução ao Pandas
created: 2024-07-17
tags:
  - pessoal/web
  - pessoal/estudos
  - python
---
| [Voltar](index) | [[Aprendendo Python]] | [[Limpeza de dados - Pandas]]
# Primeiramente para importar o pandas:
```python
import pandas as pd
```
## Alguns codigos prontos para pegar e usar:
- Ordene os dados em ordem alfabética:
```python
df = df.sort_values(by='Nome')
```
- Removendo coluna:
```python
df = df.drop(columns=['Coluna'])

columns_to_drop = ['Número Apac', 'Quantidade', 'Lote', 'CNES']
df2 = df2.drop(columns=columns_to_drop)
```
- Filtrar as linhas onde o Estado é 'SP':
```python
df = pd.read_csv('PIB_100_maiores_cidades_2017.txt', sep=',', encoding='latin-1')

df_SP = df[df['Estado'] == 'SP']
```
- Removendo espaço em banco no final do texto:
```python
df['coluna_texto'] = df['coluna_texto'].str.rstrip()
```
- Preenchendo valores ausentes na coluna A com valores da coluna B 
```python
df['A'].fillna(df['B'], inplace=True)
```
- Renomeando colunas específicas:
```python
df = df.rename(columns={'coluna1': 'nova_coluna1', 'coluna2': 'nova_coluna2'})
```
- Combinação dataframes:
![[Pandas_Python-20240729124926150.webp]]
```python
m = pd.merge(tabela_1, tabela_2, how = 'inner', on = 'Nome')
```
- Nova ordem das colunas 
```python
new_order = ['A', 'B', 'C'] 

df_reordered = df[new_order]
```
- Apaga apenas as linhas com todas as coluna com valores vazios (null)
```python
df = df.dropna(how = 'all')
#  Especificando a coluna
df.dropna(subset=["price"], axis=0)
```
- Remover duplicatas considerando todas as colunas 
```python
df_sem_duplicatas = df.drop_duplicates()
```
- Contar variaveis
```python
df.Sequência.value_counts()
df['Sequência'].value_counts()
```
- Convertendo todos os valores para maiúsculas 
```python
df_upper = df.applymap(lambda x: str(x).upper())
# ou
conferencia_df["Lote"] = conferencia_df["Lote"].apply(lambda x: str(x).upper())
```
- Convertendo a coluna 'data' para o tipo datetime64
```python
 df['data'] = pd.to_datetime(df['data'])
```
- Convertendo a coluna para string
```python
df2['coluna_float'] = df2['coluna_float'].astype(str)
```
- Remover sufixo
```python
df.columns = df.columns.str.removeprefix("R$ ")
```
- 
```python

```
- 
```python

```

