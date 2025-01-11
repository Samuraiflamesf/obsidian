---
Title: GoogleHacking
created: 2024-06-07
dg-publish: true
tags: pessoal/estudos, pessoal/web
---
| [Voltar](index) |
Para qualquer busca feita no Google, toda resposta terá a seguinte forma de exibição:
- URL para o site correspondente;
- Título;
- Resumo.
![[Pasted image 20240607170737.png]]
## ## Quais operadores mais utilizados?
Os operadores mais utilizados para realizar as buscas, são:
- **site:** limita os resultados da busca a um domínio específico, incluindo subdomínios;
- **intitle:** limita os resultados da busca a páginas em que o título contenha a palavra-chave especificada;
- **inurl:** limita os resultados da busca a páginas em que a URL contenha a palavra-chave especificada;
- **intext:** limita os resultados da busca a páginas em que o texto contenha a palavra-chave especificada;
- **filetype:** limita os resultados da busca a páginas que contenham arquivos no formato especificado. (Ex: PDF, TXT, DOC, PNG, entre outros).

A utilização dos operadores é sempre no seguinte formato:
**{operador}:{palavra-chave}**

Caso a palavra-chave possua espaços, basta escrevê-la entre aspas. Abaixo, temos mais alguns exemplos de buscas utilizando os operadores:

Neste exemplo, estamos filtrando as buscas apenas para o site _detran.ba.gov.br_, e que possua em seu texto a palavra _telefone_.

**site:detran.ba.gov.br intext:telefone**

Já neste exemplo, estamos filtrando as buscas apenas nos domínios _.com.br_ contendo arquivos do tipo _txt_ e no texto a palavra _senhas_.

**site:com.br filetype:txt intext:senhas**

No segundo exemplo, você poderá encontrar alguns arquivos que não deveriam estar expostos ao público, por isso, devemos tomar cuidado com o tipo de informação que disponibilizamos.
### References
1. https://blog.cubos.io/google-hacking-o-que-e-e-como-utiliza-lo/
  