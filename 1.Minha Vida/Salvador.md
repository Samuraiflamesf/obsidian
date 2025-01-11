---
Title: SALVADOR 🏖️
created: 2024-06-14
dg-publish: true
tags:
  - pessoal/list
  - pessoal/viagem
---
| [Voltar](index) |
## Lugares para Visitar:
```dataviewjs
// Defina a tag que você deseja buscar
let tag = "#SSA";

// Realize a consulta para buscar notas com a tag especificada
let pages = dv.pages(tag).sort(p => p.file.name); // Busca páginas com a tag e ordena pelo nome do arquivo

// Verifique se há notas correspondentes
if (pages.length > 0) {
    // Para cada nota encontrada, adicione um separador e o embed
    for (let page of pages) {
        dv.paragraph(`![[${page.file.name}]]`); // Adiciona o embed da nota
        dv.paragraph("---"); // Adiciona um separador
    }
} else {
    dv.paragraph("Nenhuma nota encontrada com a tag " + tag); // Mensagem se não encontrar notas
}

```

![[Lugares 0800]]
## 🦔 Experiências Diferentes para Vida
- Tomar Tequila
- Tomar Hidromel
---
> _“As melhores aventuras começam com um passo fora da zona de conforto!”_
---
## 🔗 Links Úteis
- [Museus – Pelourinho Dia e Noite](https://pelourinhodiaenoite.salvador.ba.gov.br/museus/)
- [Restaurant Week](https://restaurantweek.com.br/)
- https://pt.wikipedia.org/wiki/Lista_de_museus_de_Salvador