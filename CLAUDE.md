# Contador de Recesso — ANDRITZ Brasil

## O que é este repositório
Uma página estática única: `index.html`. Contador regressivo até **23/12/2026 17:25 (horário de Brasília, UTC-3)**,
com tema dia/noite alternando a cada 15 s, fogos de artifício, luzes de Natal e cenário de praia.

`index.html` é um **arquivo compilado e autocontido** (~555 KB, todo o CSS/JS embutido, sem dependências externas
além de fontes do Google). Não reformate, não minifique, não divida em arquivos e não "limpe" o código.
Para mudanças de conteúdo, use apenas edições pontuais por busca-e-substituição (ver abaixo).

## Tarefa: publicar no GitHub Pages
1. `git init` (se necessário), commit de todos os arquivos desta pasta.
2. Criar repositório público no GitHub (sugestão de nome: `contador-recesso`) via `gh repo create`.
3. `git push` para a branch `main`.
4. Habilitar GitHub Pages: `gh api -X POST repos/{owner}/{repo}/pages -f source[branch]=main -f source[path]=/`
   (ou instruir o usuário: Settings → Pages → Deploy from a branch → `main` → `/ (root)`).
5. Confirmar a URL final `https://<owner>.github.io/<repo>/` e reportá-la ao usuário.

O arquivo `.nojekyll` já está incluído — mantenha-o.

## Edições comuns (busca-e-substituição literal em index.html)
- **Data/hora alvo**: trocar todas as ocorrências de `2026-12-23T17:25:00-03:00` pela nova data ISO com fuso `-03:00`.
- **Texto da data no subtítulo**: `17h25 de 23 de dezembro`.
- **Título**: `Recesso de<br />fim de ano 2026` (aparece como `Recesso de<br/>fim de ano 2026` após compilação — busque por `fim de ano`).
- **Horas por dia** do contador de jornada: valor padrão `8.5`.
- **Intervalo do ciclo dia/noite**: `15` segundos (`cicloTema`).

Feriados considerados no contador de horas úteis: nacionais + Paraná (19/12) + Curitiba (08/09 e Corpus Christi),
mais os móveis calculados pela Páscoa. Para adicionar um feriado, inclua a string `'MM-DD'` na lista de `fixos`.

## Não fazer
- Não adicionar build tools, package.json, framework ou CI.
- Não alterar textos, cores ou layout sem pedido explícito do usuário.
- Não remover o easter egg (3 cliques no sol revelam "Patrocinado pelo Claudio").
