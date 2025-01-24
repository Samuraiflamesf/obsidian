---
Title: Git e Github
created: 2025-01-24
dg-publish: true
tags:
  - pessoal/estudos
  - pessoal/quaseumdev
  - DataOps
---
| [Voltar](index) |
**Git** é um sistema de controle de versão distribuído, que permite que várias pessoas trabalhem em um mesmo projeto ao mesmo tempo, sem que haja conflitos entre as alterações realizadas. Já o **GitHub** é uma plataforma de hospedagem de código-fonte baseada em **Git**, que permite que desenvolvedores colaborem em projetos e compartilhem seu código com outras pessoas. Em resumo, **Git** é uma ferramenta de controle de versão, enquanto **GitHub** é uma plataforma de hospedagem de código-fonte que utiliza o **Git** como base.

As principais características do Git são:
- Branching e Merging;
- Pequeno e rápido;
- Distribuído;
- Staging Area;
- Gratuito e Aberto.

Já para o GitHub, as principais características são:
- Colaborativo;
- Automações e CI/CD;
- Segurança;
- Gerenciamento de Projetos;
- Administração de Times;
- Comunidade.

O versionamento de código com Git trabalha de seguindo basicamente o fluxo da seguinte figura:
![[Pasted image 20250124165608.webp]]
Esse fluxo segue os seguintes princípios:

1. **Branch Principal (Master/Main):** Quando você cria um repositório Git, ele começa com um branch principal, geralmente chamado "master" ou "main". Este branch representa a linha de base do seu projeto e geralmente contém o código estável e pronto para produção.
2. **Criação de Novas Branches:** Para desenvolver recursos, corrigir bugs ou realizar experimentos sem afetar o branch principal, você cria novas branches a partir do branch principal. Essas branches são cópias do estado atual do projeto no momento em que são criadas.
3. **Trabalho em Branches Secundárias:** Os desenvolvedores trabalham em suas branches secundárias, fazendo alterações, adicionando código e realizando testes. Cada branch secundária é isolada do branch principal e de outras branches secundárias, permitindo o desenvolvimento independente.
4. **Merging (Mesclagem):** Quando um desenvolvedor conclui seu trabalho em uma branch secundária e está satisfeito com as alterações, ele pode mesclar (merge) essa branch de volta ao branch principal. Isso incorpora as alterações da branch secundária ao código principal do projeto.
5. **Resolução de Conflitos:** Em algumas situações, pode ocorrer um conflito durante a mesclagem, especialmente quando duas branches alteraram a mesma parte do código. Nesse caso, os desenvolvedores precisam resolver os conflitos manualmente, decidindo qual versão das alterações será mantida.
6. **Branches de Recursos e de Manutenção:** Além das branches de desenvolvimento de recursos, é comum criar branches de manutenção (como "hotfix" para correção rápida de bugs) e branches de recursos (como "feature" ou "develop" para desenvolvimento de novas funcionalidades).
7. **Histórico Linear:** O Git mantém um histórico linear de commits para cada branch. Isso significa que, mesmo que você tenha várias branches de desenvolvimento, o histórico de cada branch é independente e organizado de forma linear.
8. **Branches Remotas:** Além das branches locais, o Git permite criar e trabalhar com branches remotas, que estão em um repositório remoto (como no GitHub). Você pode empurrar (push) branches locais para um repositório remoto e puxar (pull) branches remotas para seu repositório local.
![[Pasted image 20250124170840.png]]

Alguns comandos para serem utilizados no Git:
- **git init**: inicializa um repositório Git em um diretório;
- **git add**: adiciona arquivos ao staging area;
- **git commit**: cria um novo commit com as alterações adicionadas ao staging area;
- **git push**: envia as alterações locais para um repositório remoto;
- **git pull**: baixa as alterações de um repositório remoto para o repositório local;
- **git branch**: lista, cria ou deleta branches;
- **git merge**: mescla alterações de uma branch em outra;
- **git clone**: clona um repositório remoto para o repositório local;
- **git status**: mostra o status atual do repositório;
- **git log**: mostra o histórico de commits do repositório.

Para aplicarmos esses princípios de integração e versionamento, é necessário entender como gerenciar as bibliotecas utilizadas para treino e _deploy_ dos nossos modelos.