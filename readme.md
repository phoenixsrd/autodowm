# Auto Down

Este é um simples projeto web que exibe as releases de um repositório GitHub diretamente em uma página HTML. Ele foi desenvolvido para facilitar o acesso aos assets das releases sem a necessidade de navegar diretamente pelo GitHub.

## Funcionalidades

Busca automática das releases de um repositório GitHub.
Exibição do nome das releases.
Links diretos para download dos assets de cada release.

## Como funciona

O código JavaScript integrado à página HTML realiza uma requisição à API do GitHub para buscar as releases do repositório especificado. Em seguida, as informações das releases são exibidas na página, com links para download dos arquivos.

## Como usar

Para utilizar este código, basta alterar os valores das constantes `repoOwner` e `repoName` para o proprietário e o nome do repositório desejado.

const repoOwner = 'Seu Nome De Usuário';
const repoName = 'Nome Do Seu Repositório';

## Atenção 

Para a API buscar seus arquivos, deixe seu repositório público.
