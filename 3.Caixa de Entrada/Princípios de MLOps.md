---
Title: Princípios de MLOps
created: 2025-01-20
dg-publish: true
tags:
  - pessoal/estudos
  - pessoal/puc
---
Alguns dos fundamentos de MLOps são os seguintes:
- **Automação**: O nível de automação dos _pipelines_ de Dados, Modelo de ML e Código determina a maturidade do processo de ML. Com o aumento da maturidade, a velocidade para o treinamento de novos modelos também aumenta. O objetivo de uma equipe de MLOps é automatizar a implantação de modelos de ML no sistema de software principal ou como um componente de serviço. Isso significa automatizar as etapas completas do fluxo de trabalho de ML sem nenhuma intervenção manual.
- **[[Continuous X]]**:
	- **Integração Contínua (CI)** estende o código e os componentes de teste e validação, adicionando dados e modelos de teste e validação.
	- **Entrega Contínua (CD)** se preocupa com a entrega de um pipeline de treinamento de ML que implanta automaticamente outro serviço de previsão do modelo de ML.
	- **[[Treinamento Contínuo]] (CT)** é exclusivo da propriedade de sistemas de ML, que retreina automaticamente os modelos de ML para reimplantação.
	- **Monitoramento Contínuo (CM)** se preocupa com o monitoramento de dados de produção e métricas de desempenho do modelo, que estão vinculados às métricas de negócios;
- **Versionamento**: O objetivo do controle de versão é tratar scripts de treinamento de ML, modelos de ML e conjuntos de dados para treinamento de modelos como cidadãos de primeira classe nos processos de DevOps. Neste caso, rastreia-se modelos de ML e conjuntos de dados com sistemas de controle de versão; 
- **Rastreio de Experimento**s: O desenvolvimento de _Machine Learning_ é um processo altamente iterativo e centrado em pesquisa. Em contraste com o processo tradicional de desenvolvimento de software, no desenvolvimento de ML, vários experimentos de treinamento de modelos podem ser executados em paralelo antes de tomar a decisão de qual modelo será promovido para produção;
- **Teste**: é a forma de garantir a qualidade e a “saúde”, os artefatos testados são os _pipelines_ de dados, de treino de modelo e de disponibilização da aplicação, além dos dados em si, modelo e saúde da aplicação;
- **Monitoramento**: Depois que o modelo for implantado, ele precisa ser acompanhado para garantir que o modelo funcione conforme o esperado;
- **Reprodutibilidade**: A reprodutibilidade significa que todas as fases do processamento de dados, treinamento do modelo e implantação do modelo devem produzir resultados idênticos com a mesma entrada. Se temos os mesmos dados, mesmos modelos, mesmas configurações e mesmos ambientes, temos de ser capazes de produzir os mesmos artefatos;