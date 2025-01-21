---
Title: Princípios de MLOps
created: 2025-01-20
dg-publish: true
tags:
  - pessoal/estudos
  - pessoal/puc
  - pessoal/web
---
Alguns dos fundamentos de MLOps são os seguintes:
- **Automação**: O nível de automação dos _pipelines_ de Dados, Modelo de ML e Código determina a maturidade do processo de ML. Com o aumento da maturidade, a velocidade para o treinamento de novos modelos também aumenta. O objetivo de uma equipe de MLOps é automatizar a implantação de modelos de ML no sistema de software principal ou como um componente de serviço. Isso significa automatizar as etapas completas do fluxo de trabalho de ML sem nenhuma intervenção manual.
- **_Continuous_ X**:
	- **Integração Contínua (CI)** estende o código e os componentes de teste e validação, adicionando dados e modelos de teste e validação.
	- **Entrega Contínua (CD)** se preocupa com a entrega de um pipeline de treinamento de ML que implanta automaticamente outro serviço de previsão do modelo de ML.
	- **Treinamento Contínuo (CT)** é exclusivo da propriedade de sistemas de ML, que retreina automaticamente os modelos de ML para reimplantação.
	- **Monitoramento Contínuo (CM)** se preocupa com o monitoramento de dados de produção e métricas de desempenho do modelo, que estão vinculados às métricas de negócios;