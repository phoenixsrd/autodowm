# Auto Down

Projeto web estático para listar releases de repositórios GitHub e facilitar o download de assets sem precisar navegar manualmente pela página de releases.

## Funcionalidades atuais

- Busca de releases via API do GitHub (`/releases?per_page=100`).
- Suporte a múltiplos repositórios configuráveis por URL:
  - `?owner=SEU_OWNER&repo=SEU_REPO`
- Barra de configuração para trocar `owner/repo` em tempo real.
- Busca por texto (nome, tag e descrição).
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
- Paginação para listas grandes (6 releases por página).
- Resumo dinâmico com:
  - Repositório atual
  - Total de releases exibidas
  - Total de arquivos
  - Total de downloads
  - Página atual
- Cache local com `localStorage` (TTL de 5 minutos) para reduzir chamadas na API.
- Botão “Copiar link” em cada asset.
- Tema claro/escuro com alternância manual e persistência em `localStorage`.
- Resumo com total de releases, arquivos e downloads.

## Como usar

1. Abra o `index.html` no navegador.
2. Opcionalmente, já abra com parâmetros de URL:

```text
index.html?owner=phoenixsrd&repo=autodowm
```

3. Use a barra superior para:
   - Trocar `owner/repo`
   - Buscar e ordenar releases
   - Incluir pré-releases
   - Alternar entre tema claro/escuro
4. Clique em **Carregar** para atualizar o repositório alvo.

> O repositório precisa ser público para a API retornar as releases sem autenticação.
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
