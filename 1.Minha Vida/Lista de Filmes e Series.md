---
title: Lista de Filmes e Series
created: 2024-11-01
dg-publish: true
tags:
  - série
  - moc
  - filme
description: 
cssclasses:
  - cards
  - cards-cover
  - table-max
  - dashboard
---
| [Voltar](index) |
```dataview
table without id ("![](" + image + ")") as Poster, file.link as Title, "Nota:⭐ " + (nota) + " // Tipo: " + tipo as "Tipo e Nota" from #série or #filme where image != null sort nota desc
```

