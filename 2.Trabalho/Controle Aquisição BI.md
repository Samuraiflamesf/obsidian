---
dg-publish: true
title: Controle Aquisição BI
dg-publish: false
tags:
  - trabalho/BI
  - andamento
---
| [Voltar](index) |
### Objetivo principal do dashboard:
- Numero de processos sem AFM
- Tempo medio(Tempo da  DATA CI e Tempo da AFM Gerada)
- 3 relatos
### Quais filtros?
Quais sao os programa de saude que existe aquisição via recurso estadual
Aplicar filtro de validade para verificar RP(ativo ou nao)
Filtro por Item(Medicamento)
Para COAFE, Programa de saude (Quarentena) deve ser ser considerado
para CAFAB, em SEM AFM, deve criar coluna de PAOE
Filtro para Medicamento Importado

### Verificar com CAF(Luciano)

### Troca de nome de colunas:
QTD Licitada == QTD Contratada(Pos vem da AFM)

**Colunas Automaticas**
Dias em andamento do processo = data da CI - Dia atual
Dias em estoque()
Unidade desabastecida? = Se tiver data da ultima distribução
Data Prevista para Entrega =  data ass AFM +15 dias

Coluna de percentual de entrega(Painel parcialmente atendido)
    Criar uma divisão(25,50,75 e 90) como opção
## Fonte de dados:
Planilha de inventario - SIMPAS
**Relatório de Estoque**(Tira segregação/Quarentena/)
    CEAF 1B e 2
    Estoque Regulador
    AJ
    Ver com Fran
Relatorio de Entrada(Para buscar outros dados)
    Cruzamento entre N AFM

## Origem Da CI deve ter cor diferentes

Link:: [BI](https://app.powerbi.com/reportEmbed?reportId=b3b73b81-f66d-4d99-874e-7fa09043cc24&autoAuth=true&ctid=4cd835f4-5440-408f-93a3-975fc17c384a)
