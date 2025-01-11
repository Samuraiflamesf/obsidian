---
title: Mapa de Atividades
tags:
  - moc
  - trabalho
description: CheckList de atividades para serem resolvidas
---
| [Voltar](index) |
``` dataview
table task.text as "Atividades"
from #trabalho/atividades 
flatten file.tasks as task
where !task.completed
sort file.name

```