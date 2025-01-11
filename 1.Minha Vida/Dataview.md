---
Title: Dataview
created: 2024-11-03
dg-publish: true
tags:
  - pessoal/estudos
  - pessoal/quaseumdev
  - obsidian
---
| [Voltar](index) |
## Algumas dicas do Plugin Dataview
**Como embutir notas com base em Tags**:
```
// Defina a tag que você deseja buscar
let tag = "#SSA";

// Realize a consulta para buscar notas com a tag especificada
let pages = dv.pages(tag).sort(p => p.file.name); 
// Busca páginas com a tag e ordena pelo nome do arquivo

// Verifique se há notas correspondentes
if (pages.length > 0) {
    // Para cada nota encontrada, adicione um separador e o embed
    for (let page of pages) {
        dv.paragraph("---"); // Adiciona um separador
        dv.paragraph(`![[${page.file.name}]]`); // Adiciona o embed da nota
    }
} else {
    // Mensagem se não encontrar notas
    dv.paragraph("Nenhuma nota encontrada com a tag " + tag); 
}
```
Para funcionar como esperado utilize `dataviewjs`.
## 🔗 Links Úteis
- [Is is possible to embed the files in the list view ? - GitHub](https://github.com/blacksmithgu/obsidian-dataview/issues/177)