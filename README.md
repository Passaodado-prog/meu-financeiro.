# Meu Financeiro — vencimento editável das faturas

Esta versão corrige o vencimento padrão das faturas e permite editar a data de uma fatura específica.

## Arquivos para GitHub Pages

Envie para a raiz do repositório:
- `index.html`
- `manifest.webmanifest`
- `service-worker.js`
- pasta `icons/`

## Comportamento

- O vencimento padrão de cada fatura usa o dia configurado no cadastro do cartão, aplicado ao mês de vencimento da fatura.
- Ao abrir uma fatura, o campo **Data de vencimento desta fatura** permite alterar somente aquela fatura.
- A alteração fica salva por cartão e mês e é incluída no backup JSON.
- O botão **Usar vencimento do cartão** remove a alteração individual e restaura o dia cadastrado no cartão.
- Alterar o vencimento não muda a competência da fatura nem a data das compras individuais.

Cache PWA: v18.
