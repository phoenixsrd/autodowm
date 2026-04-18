# Auto Down

Projeto web estático para listar releases de repositórios GitHub e facilitar o download de assets sem precisar navegar manualmente pela página de releases.

## Funcionalidades atuais

- Busca de releases via API do GitHub (`/releases?per_page=100`).
- Suporte a múltiplos repositórios configuráveis por URL:
  - `?owner=SEU_OWNER&repo=SEU_REPO`
- Barra de configuração para trocar `owner/repo` em tempo real.
- Busca por texto (nome, tag e descrição).
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
