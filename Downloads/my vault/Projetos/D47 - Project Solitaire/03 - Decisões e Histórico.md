---
projeto: D47 - Project Solitaire
atualizado: 2026-09-23
tags:
  - d47
---

# Decisões e Histórico // Project Solitaire

---

### [2026-09-23] Pivot de Direção: De Cassino Genérico para Simulação Humana Profunda
- **Problema:** A ideia inicial de criar mini-jogos de cassino / roletas em ELIX foi rejeitada por ser genérica, batida e desprovida de alma ou interesse.
- **Insight do Usuário:** *"eu gosto da ideia de expandir o usuário, tipo, quase introduzir um personagem ao usuário, no qual ele pudesse pedir joias customizadas, exibir suas coisas... mas precisa ter profundidade, muito além dos jogos usuais de simulação, com interações que sejam humanas ou ajam como humanas."*
- **Decisão:** Abandonar o modelo de cassino raso e focar em uma experiência de drama pessoal, artesanato de alta joalheria e psicologia de status social no Diamond District (47th Street).
- **Filosofia de Entrega:** O projeto deve ser desenvolvido **capítulo por capítulo, devagar, sem fragmentação — onde cada entrega é um todo completo e refinado**.

### [2026-09-23] Definição da Arquitetura Técnica
- **Motor de Banco de Dados:** SQLite nativo do Node.js (`node:sqlite`) em modo WAL com transações ACID.
- **Liquidação:** D47 Partner API (`https://d47-server-production.up.railway.app`) para buy-ins (`transfer-requests`) com deep-links e payouts imediatos (`/api/v1/payouts`).
- **Verificação Criptográfica:** Webhooks assinados com HMAC-SHA256 e proteção contra replay attack (janela de 300 segundos).
- **IA Cognitiva:** Motor de diálogo e monólogo interior para Vesper com memória persistente de conversas anteriores.
