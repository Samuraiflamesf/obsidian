---
Title: Como estou usando um servidor 100% gratuito vitalício
created: 2025-01-22
dg-publish: true
tags:
  - pessoal/estudos
  - pessoal/quaseumdev
---
| [Voltar](index) |
### Obtenha um servidor com 24 GB de RAM + 4 CPUs + 200 GB de armazenamento + Sempre Gratuito

Como desenvolvedores, precisamos executar e hospedar backends em serviços de nuvem. Muitos BaaS (Backend as a Service) estão disponíveis, mas possuem limitações em funcionalidade, recursos ou duração do uso gratuito. Se você está cansado de procurar por um servidor gratuito e confiável, acredito que encontrou o lugar certo.

E se eu dissesse que estou usando um servidor baseado em Linux gratuitamente há mais de 4–5 anos? Sim, você ouviu direito. Estou usando este servidor Linux com Ubuntu 20 instalado, 24 GB de RAM, 4 CPUs e 200 GB de armazenamento, gratuitamente e vitalício.

Usei **AWS** e **Google Cloud Platform** por 1 ano, mas após esse período, os serviços gratuitos expiraram. A AWS oferece um servidor gratuito por um ano com 1 GB de RAM e 30 GB de armazenamento, enquanto o Google Cloud Platform fornece US$ 300 de crédito por um ano, suficiente para criar um servidor de 8 GB ou maior. Porém, o problema é que ambos oferecem isso apenas por um ano.

![Como Estou Usando um Servidor 100% Gratuito Vitalício](https://cdn-images-1.medium.com/max/3000/1*BqVsCBa2mLv1UWQrdhjX5w.png)

Cerca de quatro anos atrás, enquanto procurava por serviços gratuitos de nuvem após o término dos períodos de teste da AWS e do GCP, descobri que a Oracle Cloud oferece servidores gratuitos vitalícios sem restrições. Assim, me cadastrei na Oracle Cloud e comecei a usá-lo. Desde então, já se passaram aproximadamente quatro a cinco anos em que venho utilizando o serviço gratuitamente.

![oracle.com/in/cloud/free/](https://cdn-images-1.medium.com/max/2798/1*kyMpGfp0rcJSuwOh0GG3Fg.png)

## Aqui está um guia completo para começar a usar a Oracle Cloud

O primeiro passo é criar uma conta na Oracle Cloud, para isso, você precisa de um e-mail válido e um cartão de crédito. O processo leva alguns minutos, e será cobrado um valor entre US$ 1 e US$ 2 para verificação do cartão. Não se preocupe, esse valor é reembolsado em poucos dias.

1. Acesse: [**https://signup.oraclecloud.com/**](https://signup.oraclecloud.com/)
2. **Preencha o formulário de cadastro corretamente**
3. **Verifique seu e-mail**
4. **Forneça informações válidas, incluindo os dados de pagamento (você não será cobrado) e conclua o processo de cadastro.**

![signup.oraclecloud.com/](https://cdn-images-1.medium.com/max/2454/1*uSZF7ia6Bi_30mkQnk5RvA.png)

## Criando uma instância gratuita

Após concluir o cadastro, faça login na sua conta Oracle Cloud. No painel, selecione **Compute > Instances**.

![](https://cdn-images-1.medium.com/max/2000/1*d7AYtwi-VXbZlGOcwfEOng.png)

Clique no botão **Create Instance** —

![](https://cdn-images-1.medium.com/max/2000/1*SNOW-rr7C2nZx-InrZvtXg.png)

Na próxima tela, escolha os recursos marcados como **Always Free**. Por exemplo, se você quiser usar o Ubuntu, edite a imagem e a configuração, selecionando a imagem Ubuntu marcada como sempre gratuita.

![](https://cdn-images-1.medium.com/max/2484/1*aGUaQiTL80W7dM2aeo73DA.png)

No próximo passo, baixe as chaves pública e privada necessárias para conectar-se ao servidor via SSH. Em seguida, anexe o volume de inicialização com até 200 GB e clique em **Create**.

Levará alguns minutos, e você estará pronto para usar sua instância gratuita.

> **Nota:** Para arquitetura baseada em AMD, você receberá 1 GB de RAM com 1 CPU, enquanto para ARM você terá 24 GB de RAM com 4 CPUs.

![Estatísticas do Meu Servidor](https://cdn-images-1.medium.com/max/2026/1*5bsicTj2-FDtE4h2SfA5VQ.png)

## Conectando-se ao Servidor via SSH

Para gerenciar a nova instância criada, você precisa acessar o servidor usando SSH (Secure Shell), que oferece acesso à linha de comando. Use as chaves baixadas (server.key) durante a criação da instância. Talvez seja necessário alterar as permissões do arquivo de chave com o comando:

```bash
chmod 600 path/to/server.key
ssh -i path/to/server.key ubuntu@seu-ip-público
```

Após alguns segundos, você conseguirá acessar seu servidor, visualizando algo assim:

![](https://cdn-images-1.medium.com/max/2000/1*NB6U21ypo0xjYwoQobUfvA.png)