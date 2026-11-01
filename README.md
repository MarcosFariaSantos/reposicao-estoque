# Reposição de estoque (moto peças)

Dashboard que mostra quantos dias cada peça dura no estoque e o que comprar primeiro. Nasceu de um problema real da rotina de compras de uma loja de moto peças.

## O que já está pronto

- Dashboard em HTML, CSS e JavaScript puros (sem backend), com filtro por situação (crítico, atenção, em dia).
- Regras de reposição: cobertura em dias, situação do item e sugestão de compra.
- Leitura de um `dados.json` opcional, para trocar os dados de exemplo pelos seus.

## Dados

Os produtos e números do `index.html` são **fictícios**, só para demonstração. Formato do `dados.json`:

```json
[
  { "produto": "Pastilha de freio", "estoque": 4, "minimo": 10, "vendas30": 42, "analise_ia": "texto opcional" }
]
```

O campo `analise_ia` é opcional. Quando existe, aparece sob o produto.

## Regras de cálculo

- Consumo diário = vendas dos últimos 30 dias ÷ 30
- Cobertura = estoque ÷ consumo diário
- Crítico: estoque menor ou igual ao mínimo. Atenção: menos de 15 dias de cobertura.
- Sugestão de compra = vendas de 30 dias + estoque mínimo − estoque atual

## Em andamento

Automação no Make que lê a planilha de estoque e vendas e consulta a API de um modelo de IA para gerar a análise de cada item. A integração com o modelo ainda está sendo concluída.

## Como rodar

Abra o `index.html` no navegador. Para publicar, ative o GitHub Pages no repositório.
