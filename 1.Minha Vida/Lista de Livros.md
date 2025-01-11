---
title: Lista de Livros
created: 2024-11-01
dg-publish: true
tags:
  - moc
  - pessoal/livros
cssclasses:
  - cards
  - cards-cover
  - table-max
  - dashboard
---
| [Voltar](index) |  [[Livros de Informatica]] | [[Livros de Gastronomia]] |
```dataview
table without id 
	("![](" + Cover + ")") as Poster,
	file.link as Title	
from #livro 
where Cover != null
```

