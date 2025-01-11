---
title: Introdução ao graficos do Pandas
created: 2024-08-12
dg-publish: true
tags:
  - pessoal/estudos
  - pessoal/quaseumdev
  - python
---
| [Voltar](index) | [[Aprendendo Python]] |
> [!dica] Criando um dataframe:
> dados = pd.DataFrame(lista)
# Gráfico de colunas
dados.plot.bar()
# Gráfico de barras horizontais
dados.plot.barh()
# Gráfico de linhas
dados.plot.line()
# Gráfico de pizza
dados.plot.pie(subplots=True)
[[Aprendendo Python]]