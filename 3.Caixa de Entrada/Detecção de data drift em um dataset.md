---
Title: Data Drift
created: 2025-01-20
dg-publish: true
tags:
  - pessoal/estudos
  - pessoal/puc
---
![[Pasted image 20250120222920.webp]]
Existem diferentes abordagens para lidar com cada tipo de _Drift_:
- **_Data Drift_:** é importante monitorar os dados usados para treinar os modelos, atualizar os dados regularmente e, se necessário, refazer os modelos completamente. A atualização dos dados pode ser feita por meio de técnicas como reamostragem, reequilíbrio de classes e reajuste de pesos.
- **_Concept Drift_:** é importante refazer o modelo completamente. Isso pode envolver a coleta de novos dados, a redefinição das variáveis de entrada e a redefinição da variável alvo. É importante lembrar que o _Concept Drift_ pode ser um sinal de que o modelo precisa ser atualizado ou que a estratégia de negócios da empresa mudou. Portanto, é importante avaliar cuidadosamente a causa do _Concept Drift_ antes de refazer o modelo