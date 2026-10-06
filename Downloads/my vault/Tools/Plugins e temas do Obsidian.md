---
atualizado: 2026-10-06
tags:
  - indice
  - obsidian
---

# Plugins e temas do Obsidian

Inventário do que está instalado neste vault (`.obsidian/`): para que serve cada plugin, em que pastas ele escreve e o estado de configuração. Conferido em 06/10/2026 às 11h45, a partir dos `manifest.json` e `data.json` de cada plugin.

## Plugins da comunidade (9)

| Plugin | Versão | Para que serve | Pastas e arquivos que usa no vault | Estado |
| --- | --- | --- | --- | --- |
| Goko | 1.0.10 | Mural visual de recortes da web (links, imagens, vídeos, PDFs) | `Clippings/` (notas) e `Attachments/Clippings/` (mídia); subpastas de `Clippings/` viram grids | Em uso. Guia: [[Tools/Goko — start here\|Goko — start here]] |
| Notekit Edit | 0.3.0 | Seleciona um trecho, descreve a mudança e o Claude/Codex reescreve na nota | — | Configurado (3 provedores) |
| Sidebar Terminal | 0.1.5 | Shell em abas nativas com painéis divididos | — | Em uso (há scrollback salvo) |
| Vault Pet | 1.2.1 | Gato pixel que ganha XP conforme você escreve | — (estado em `data.json`) | Em uso |
| Just Simple Calendar | 1.4.1 | Views de calendário (mensal, infinito, anual) em Bases | arquivos `.base` | Instalado |
| Visual Gallery | 0.1.10 | Galeria visual de canvases e notas | — | Instalado |
| Notion Selection Toolbar | 1.0.1 | Barra flutuante de formatação ao selecionar texto | — | Instalado |
| Checkbox Styles | 1.0.1 | Estilos visuais para cada checkbox de tarefa | — | Instalado |
| Typography as You Type | 0.3.1 | Aspas curvas, travessões e reticências automáticos ao digitar | — | Instalado |

### Removidos em 06/10/2026

Treze plugins saíram no mesmo dia da reorganização, junto com as pastas que mantinham no vault: **Exo Agent** (`_exo/` e a fila antiga `_system/`), **WhatsApp Bridge** (`WhatsApp/`), **Momoan Todo** (`Momoan Todo/`), Harbor Tab, Black Hole Graph, Second Brain Lab 3D, Focus Modes, Web Browser, Everyday Wisdom, Note Site Builder, SSH Terminal, Remote SSH e Syncher.

## Plugins principais (core)

Ativos: explorador de arquivos, busca, switcher, grafo, backlinks, canvas, links de saída, painel de tags, notas de rodapé, propriedades, pré-visualização, **daily notes**, templates, note composer, paleta de comandos, comandos com barra, status do editor, favoritos, importador de Markdown, **prefixador Zettelkasten** (pasta `Inbox/`, formato `AAAAMMDDHHmm`), outline, contador de palavras, **gravador de áudio**, workspaces, recuperação de arquivos, Publish, Sync, **Bases** e visualizador web.
Desativados: nota aleatória e slides.

## Configuração do app

- Anexos → `Attachments/`; notas novas → `Inbox/`; links atualizados automaticamente ao mover ou renomear dentro do Obsidian.
- Tema ativo: **Claude Synapse**, translucidez ligada, cor de destaque `#b3a9cb`.
- Atalho personalizado: **⌥⌘O** inicia o gravador de áudio.
- Propriedades registradas em `types.json`: `aliases`, `cssclasses`, `tags`, `Category` (a nota Proof passou a usar `categories`, em minúsculas, como o Goko).

## Temas

**177 temas** instalados em `.obsidian/themes/` (a maior parte adicionada em 01/10 e 06/10); só o Claude Synapse está em uso. Cada tema são dois arquivos pequenos, mas a lista no seletor fica inutilizável — vale apagar os que não interessam em *Configurações → Aparência → Temas → Gerenciar*.

## Claude Code e MCP no vault

- `.claude/skills/hatch-pet/` — skill para criar pets animados compatíveis com o Codex (spritesheets 8×11, com scripts e testes).
- `.claude/skills/playwright/` — skill para automatizar um navegador real pelo terminal via `playwright-cli`.
- `.mcp.json` — servidores MCP: `devpost` (HTTP), `wpcom-mcp` (WordPress.com, HTTP) e `node_repl` (binário dentro do app ChatGPT). `.claude/settings.local.json` habilita `node_repl` e `wpcom-mcp`.

## Git

O vault está dentro do repositório git da pasta pessoal (`/Users/MAC`), onde o Exo Agent fazia auto-commits até ser removido. O `.gitignore` na raiz do vault deixa de fora `workspace.json`, logs e caches de plugins, `node_modules/` e a nota `Inbox/First Note.md` (contém chaves de API).
