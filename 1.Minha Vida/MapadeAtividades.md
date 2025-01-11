---
dg-publish: true
title: Mapa de Atividades
draft: true
tags:
  - moc
  - pessoal
description: CheckList de atividades para serem resolvidas
---
| [Voltar](index) |
``` dataview
table task.text as "Atividades"
from #atividades and #pessoal  
flatten file.tasks as task
where !task.completed
sort file.name

```