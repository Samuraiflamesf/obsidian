---
Title: OLAP
created: 2024-11-11
dg-publish: true
tags:
  - pessoal/estudos
  - pessoal/puc
  - pessoal/web
  - DataDiscoveryAnalytics
---
É utilização de ferramentas de análises de dados e Bi como armazenamento de dados, para ajudar na solução de problemas. 
### Arquitetura de um Projeto
![[Pasted image 20240626132137.png]]
A consolidação de todos os dados em um único repositório forma um Data Warehouse. Usando OLAP (Processamento Analítico Online), é possível acessar todo o conjunto de dados, mas selecionando apenas os dados específicos necessários para análise. O processo típico envolve a extração, transformação e carregamento (ETL) de dados do Data Warehouse para criar um Data Marts, que é um subconjunto de dados otimizado para análises específicas. Esses dados então passam por OLAP e são finalmente disponibilizados ao usuário final por meio de um cliente.
### Ciclo de vida de Projeto de Dados
![[Pasted image 20240628132646.png]]