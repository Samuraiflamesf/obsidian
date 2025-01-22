---
Title: Limpeza de dados - Pandas
created: 2024-11-18
dg-publish: true
tags:
  - pessoal/estudos
  - pessoal/quaseumdev
---
 | [Voltar](index) | [[Introdução ao Pandas]] |
### Importar o arquivo, e forçar usar um outr tipo de codificação
 ```python
# codificação = latin1 / utf8 / cp1252 / outra codificação
dados = pd.read_csv(arquivo, sep=';', skiprows=1, encoding='latin1')
```
### Apaga apenas as linhas com todas as coluna com valores vazios (null)
```python
dados = dados.dropna(how = 'all')
```
### Tirar espaços em braco no início e no fim do texto de uma celula
```python
dados.loc[:, 'Impacto'] = dados.Impacto.str.strip()
```
### Remover um prefixo nos dados
```python
dados.loc[:, 'Impacto'] = dados.Impacto.str.removeprefix("R$ ")
```
### Substituir ',' por '.'
```python
dados.loc[:, 'Impacto'] = dados.Impacto.str.replace(',', '.')
```
### Análise da qualidade das variáveis numéricas - (análise descritiva)
Resumo descritivo das colunas numéricas
```python
dados.describe()
```
Explorar medidas resumo - (média, desvio padrão, mínimo, 1º quartil, mediana, 3º quartil, máximo)
```python
dados.GESTACOES.describe()
```
Histograma
```python
sns.histplot(dados.GESTACOES)
```
Contando a quantidade de casos
 ```python
dados.PARTOS.value_counts()
```
### Converter uma coluna texto para numerico (se tiver numeros e textos misturados)
 ```python
dados['Vento'] = pd.to_numeric(dados['Vento'], errors='coerce')
# errors{‘ignore’, ‘raise’, ‘coerce’}, default ‘raise’

# If ‘raise’, then invalid parsing will raise an exception.
# If ‘coerce’, then invalid parsing will be set as NaN.
# If ‘ignore’, then invalid parsing will return the input.
```
### Trocar os números pelo conteúdo das categorias, o python não precisa que as categorias sejam códigos (apenas para regressão) - **Variáveis [[Dummy]]**
 ```python
# Já se sabe pela documentação da Base de dados que:
# 1 = partos vaginais
# 2 = partos cesáreos

dados.TIPO_PARTO.replace(1, 'Parto Normal', inplace=True)
dados.TIPO_PARTO.replace(2, 'Parto Cesáreo', inplace=True)
dados.TIPO_PARTO.value_counts()
```