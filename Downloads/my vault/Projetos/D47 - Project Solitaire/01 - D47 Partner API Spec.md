---
projeto: D47 - Project Solitaire
atualizado: 2026-09-23
tags:
  - d47
---

# D47 Partner API Specification

> **Base URL:** `https://d47-server-production.up.railway.app`
> **Dashboard:** `dev.d47.io`
> **Segurança:** As chaves de API (`x-app-key`, `x-app-secret`) rodam exclusivamente no servidor backend e nunca são expostas ao cliente.

---

## 1. Modelo Mental

O **D47** é a camada de liquidação definitiva para a economia do jogo Diamond District.
Nosso site **nunca** armazena senhas ou logins de jogadores. Solicitamos movimentação de valor entre contas reais in-game através da API do parceiro.

### Moedas
- **ELIX (`kind="elix"`):** A moeda base da rede.
- **Tokens Obsidian DEX (`kind="token"`):** Tokens emitidos por jogadores (ex.: `ZERO`, `CLOAK`, `DIAMOND`).

### Direções de Valor
- **Buy-in (Jogador -> Parceiro):** Requer aprovação do jogador no app D47. Criamos uma requisição de transferência e exibimos um deep link (`d47://confirm?tx=<id>`).
- **Payout (Parceiro -> Jogador):** Executado imediatamente via `POST /api/v1/payouts` a partir dos fundos da conta parceira, sem confirmação do jogador.

---

## 2. Endpoints Principais

### POST `/api/v1/transfer-requests`
Cria uma requisição de buy-in com expiração de 5 minutos.
- **Body:** `{ amount, kind, ticker, external_ref, memo, callback_url }`
- **Retorno:** `{ id, status: "pending", deepLink, universalLink, expiresAt }`

### GET `/api/v1/transfer-requests/:id`
Consulta o status de uma requisição pendente (`pending`, `confirmed`, `denied`, `expired`).

### POST `/api/v1/payouts`
Envia valor imediatamente para a conta do jogador.
- **Header recomendado:** `Idempotency-Key: <unique-key>`
- **Body:** `{ toPlayFabId, amount, kind, ticker, external_ref, memo }`

### GET `/api/v1/players/:playFabId/balance`
Lê o saldo em carteira de um jogador no D47.

### GET `/api/v1/tokens/:ticker/price`
Retorna a cotação spot em ELIX e a liquidez da pool na Obsidian DEX.

---

## 3. Webhooks & Assinatura HMAC-SHA256

- **Headers:** `X-D47-Timestamp`, `X-D47-Signature: v1=<hex>`
- **Cálculo da Chave:** `key = SHA-256(appSecret)`
- **Assinatura Esperada:** `HMAC-SHA256("<timestamp>.<rawBody>", key)`
- **Janela de Replay:** Máximo 300 segundos de tolerância.
