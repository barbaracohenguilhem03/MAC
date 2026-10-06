---
atualizado: 2026-10-06
tags:
  - indice
---

# Início

Mapa do vault: cada área tem o seu índice ou é gerida por um plugin.

| Área | Entrada | O que é |
| --- | --- | --- |
| Projetos | [[Projetos/00 - Índice de projetos\|Índice de projetos]] | documentação dos projetos de código (o código fica fora do vault) |
| Ferramentas | [[Tools/00 - Ferramentas\|Ferramentas]] | ferramentas e apps salvos da web, e o guia do Goko |
| Plugins e temas | [[Tools/Plugins e temas do Obsidian\|Plugins e temas do Obsidian]] | inventário dos plugins, temas, atalhos e do Claude Code/MCP configurados neste vault |
| Recortes | pasta `Clippings/` — abrir pelo mural do Goko (ícone na barra lateral) | recortes da web gerenciados pelo Goko; as imagens ficam em `Attachments/Clippings/` |

## Inbox

Notas novas caem aqui; processar e mover para a área certa.

```base
filters:
  and:
    - file.inFolder("Inbox")
views:
  - type: table
    name: Inbox
    order:
      - file.name
      - file.mtime
```

Pendente de triagem (06/10/2026): [[Inbox/Ideias\|Ideias]], [[Inbox/Gravações 2026-10-06\|Gravações 2026-10-06]] e [[Inbox/First Note\|First Note]] — esta última contém chaves de API em texto puro: rotacionar e apagar.

## Convenções

- Notas novas, inclusive as de nota única (`AAAAMMDDHHmm`): `Inbox/`
- Imagens, anexos e gravações do gravador de áudio (⌥⌘O): `Attachments/`
- Ao mover ou renomear notas dentro do Obsidian, os links são atualizados automaticamente
- Pastas que plugins usam — não mover nem renomear: `Clippings/` e `Attachments/Clippings/` (Goko)
- Links internos com o caminho completo (`[[Projetos/...]]`), como já é o padrão nas notas de projeto
- Propriedades: `atualizado` e `tags` nas notas do vault (`projeto` nas de projeto); `title`, `source` e `tags` nas notas vindas da web
- Tags: `indice`, `ferramenta`, `clippings`, `ideia`, `gravacao` e uma por projeto (`app-mamae`, `d47`, `linen`…)

## Histórico

- 06/10/2026 — reorganização: índices e frontmatter normalizados, inventário de plugins criado. No mesmo dia os plugins Exo Agent, WhatsApp Bridge e Momoan Todo foram removidos junto com as pastas `_exo/`, `WhatsApp/` e `Momoan Todo/`; a pasta `_system/` (fila antiga do Exo) também saiu.
- 29/09/2026 — estrutura atual do vault (Projetos, Tools, Clippings, Inbox) e índices criados.
