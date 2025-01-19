---
title: Trees of knowledge
dg-home: true
dg-publish: true
---
****
> Bem-vindo ao meu espaço pessoal! Este site foi criado para organizar e compartilhar minhas notas de estudo, anotações de trabalho e outros recursos úteis. Aqui você encontrará uma variedade de informações e ferramentas que uso no meu dia a dia profissional e acadêmico.

# 🌱 Minha Vida
- 🖥️ Programação
    - [[Tutoriais do YouTube]]
    - [[Aprendendo Git]]
    - [[Aprendendo Python]]
    - [[Aprendendo PhP]]
    - [[Aprendendo Obsidian]]
    - [[Tutoriais do YouTube]]
- 👇 Navegação
    - [[Lista de Poesias]]
    - [[Lista de Manga]]
    - [[Lista de Livros]]
    - [[Lista de Filmes e Series]]
    - [[Lista de Restaurantes]]
- 🎴 Minhas Experiências
    - [[Internacional]]
    - [[Brasil]]
    - [[Bahia]]
    - [[Salvador]]
# 👨‍🎓 Faculdade
- ➗ Faculdade de [[Matematica_IFBA]]
    - [[Estatística Geral - Teoria e Aplicações]]
- 📊 Faculdade de [[DataScience_PUC]]
    - [[Data Discovery e Analytics]]
    - [[esta]]
- 🍲 Faculdade de [[Gastronomia_UNIFACS]]
    - [[Livros de Gastronomia]]
- 📝 Cursos Interessantes
    - [[Qualidade de Dados em Saúde para IA]]
# 💼 Work
- [[MapaProjetosTrabalho]]: Notas e informações relevantes para meus projetos e tarefas de trabalho.
- [[MapadeAtividades]]: CheckList de atividades para serem resolvidas
- [[MapaReuniõesTrabalho]]: Anotações sobre as reuniões e eventos do Trabalho.  
# 〽️ Estatísticas
### 📥 Caixa de Entrada
```dataview
TABLE file.ctime as "Criado em"
FROM "3.Caixa de Entrada"
Limit 5
sort file.ctime desc
```
### 📖 Últimos Livros Adicionados
```dataview
LIST FROM #livro WHERE Status = false
SORT file.ctime DESC
LIMIT 5
```
### 🎬 Últimos Filmes Adicionados
```dataview
LIST 
FROM #filme
WHERE assistido = false
SORT file.ctime DESC
LIMIT 5
```
### 📼 Informações Gerais
-   📝 Total de Notas no Cofre: `$=dv.pages().filter(p => p.tags).length`
-   📚 Total de Livros: `$=dv.pages('#livro').length`
-   🍿 Total de Filmes: `$=dv.pages('#filme').length`
---
Se você tem sugestões, correções ou gostaria de contribuir de alguma forma, sinta-se à vontade para entrar em contato. Toda ajuda é bem-vinda!
-   [E-mail](mailto:samuraiflamesf@gmail.com)
-   [Github](https://github.com/Samuraiflamesf/CofreObisidian)
-   [Youtube](https://youtube.com/user/SamuraiFlameSF)
  
Obrigado por visitar meu espaço pessoal! Espero que você encontre algo útil e que possa ajudar nos seus estudos ou trabalho.