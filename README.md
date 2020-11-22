# Teste para vaga de front-end na Gendo.com.br

Este repositório tem como fim testar os candidatos para vaga de front-end developer na empresa [Gendo](https://gendo.com.br).

> Para esta vaga buscamos alguém apaixonado por HTML, CSS, JavaScript e atento aos detalhes!

## Instruções Básicas

1. Faça um fork deste repositório
2. Implemente o HTML e CSS de forma que fique fiel ao layout
3. Atenção com espaçamentos e tamanhos de fonte
4. Qualquer contribuição para melhorar o resultado será bem vinda!
5. O usuário do GitHub utilizado no exemplo pode ser qualquer um de sua escolha
6. Ao finalizar, atualize o README.md no seu repositório com as instruções para instalar e executar sua entrega

## Desafio (opcional para Junior), a página deve:

1. Carregar os dados de forma dinâmica utilizando a [API do GitHub](https://developer.github.com/v3/)
2. Carregar os repositórios do usuário inicialmente
3. Carregar os favoritos do usuário ao acessar a tab **Starred**
4. Fazer uma busca ao digitar e fazer o submit com "Enter"

## O que esperamos no teste

- HTML Semântico
- CSS de fácil leitura e reutilização
- Uso de pré-processadores CSS como Sass, Less ou Stylus
- Uso de algum _task runner_ para gerar os arquivos minificados (Grunt, Gulp, Webpack, etc.)

## Stack

### Preferível

- Utilizar Sass como pré-processador
- Mobile First

### Bônus

- AngularJS, Angular (2+), React, VueJS ou Javascript puro e organizado
- CSS transitions
- [BEM](https://tableless.com.br/bem-um-novo-metodo-para-seu-css/) (Block, Element Modifier) nas nomenclaturas do CSS

## Material

Todo o layout está hospedado no Zeplin neste link:
https://scene.zeplin.io/project/5b48f7870acff10844983114

## Envio do teste

1. Suba o repositório no seu Github e envie o link com o assunto: **Teste Front-End** para Juliano Baladão [jbaladao@gendo.com.br](mailto:jbaladao@gendo.com.br)

# Instruções do Projeto

- Após fazer a cópia local do projeto execute o comando `npm i` para instalar as dependencias.
- Após instalação execute o comando `npm run dev` e acesse o projeto no endereço [http://localhost:8080](http://localhost:8080)

- O projeto utiliza usuarios aleátorios filtrados da API.
- São carregados os 30(trinta) primeiros repositórios do usuario e os 30(trinta) primeiros repositórios que ele favotirou.
- É possivel realizar uma busta por palavras chaves nos repositórios carregados com base nos campos 'name' e 'description'
