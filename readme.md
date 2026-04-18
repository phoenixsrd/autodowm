# Auto Down

Projeto web estático para listar releases de um repositório GitHub e facilitar o download de assets sem precisar navegar manualmente pela página de releases do GitHub.

## Funcionalidades atuais

- Busca automática de releases via API do GitHub.
- Exibição de nome, tag, data de publicação e notas da release.
- Links diretos para download dos assets.
- Filtro por texto (nome, tag e descrição).
- Ordenação por:
  - Mais recentes
  - Mais antigas
  - Mais arquivos
  - Mais downloads
- Opção para incluir/excluir pré-releases.
- Resumo com total de releases, arquivos e downloads.

## Como usar

1. Abra o `index.html` no navegador.
2. Se quiser apontar para outro repositório, altere:

```js
const repoOwner = 'SeuNome';
const repoName = 'SeuRepositorio';
```

> O repositório precisa ser público para a API retornar as releases sem autenticação.

## Melhorias sugeridas (próximos passos)

- Paginação para repositórios com muitas releases.
- Cache local com `localStorage` para reduzir chamadas na API.
- Botão para copiar link do asset com um clique.
- Tema claro/escuro com alternância manual.
- Suporte a múltiplos repositórios configuráveis pela URL (`?owner=&repo=`).
