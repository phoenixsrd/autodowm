# 📦 Auto Dowm

O **Auto Dowm** é uma página web estática que transforma a API de releases do GitHub em um painel de consulta e download. Ele é útil quando você quer encontrar rapidamente uma versão, seus assets, notas e links diretos sem navegar manualmente por várias páginas do GitHub.

## O que ele faz

- Consulta todas as releases públicas de um repositório, com paginação automática da API.
- Permite trocar o `owner/repo` pela interface ou pela URL.
- Pesquisa por nome, tag e descrição da release.
- Ordena por data, quantidade de arquivos ou total de downloads.
- Inclui ou oculta pré-releases.
- Exibe seis releases por página, com resumo de arquivos e downloads.
- Oferece download direto de cada asset e botão para copiar o link.
- Mantém cache local por cinco minutos para reduzir chamadas à API.
- Persiste o tema claro/escuro no `localStorage`.
- Mostra mensagens de erro quando o repositório não é público ou a API falha.

## Fluxo de dados

O `index.html` lê os parâmetros `owner` e `repo`, chama `https://api.github.com/repos/{owner}/{repo}/releases`, percorre as páginas de 100 itens e guarda o resultado no cache do navegador. Os filtros e a ordenação são aplicados localmente, sem backend ou banco de dados.

```text
URL/parâmetros → GitHub Releases API → cache local → filtros/ordenação → cards e paginação
```

## Uso rápido

```bash
git clone https://github.com/phoenixsrd/autodowm.git
cd autodowm
python3 -m http.server 8080
```

Abra uma destas URLs:

```text
http://localhost:8080/
http://localhost:8080/?owner=phoenixsrd&repo=autodowm
```

Também é possível abrir `index.html` diretamente no navegador, mas um servidor HTTP é recomendado para reproduzir o ambiente de deploy.

## Interface

1. Informe o proprietário e o nome do repositório.
2. Clique em **Carregar**.
3. Use a busca, a ordenação e o filtro de pré-releases.
4. Clique no nome da release para abrir sua página no GitHub ou em um asset para baixá-lo.
5. Use **Copiar link** para compartilhar o endereço direto do arquivo.

## Estrutura

```text
index.html  # Aplicação completa: HTML, CSS e JavaScript
favicon.ico # Ícone do site
.github/    # Configurações auxiliares do GitHub
```

## Limitações

- A API pública do GitHub possui limite de requisições por IP.
- Apenas repositórios públicos funcionam sem autenticação.
- O aplicativo não hospeda os arquivos: os downloads vêm diretamente do GitHub.
- O cache pode exibir dados antigos por até cinco minutos; carregue novamente para atualizar.
