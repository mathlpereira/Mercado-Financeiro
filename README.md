# Primeiro Passo

**Educação financeira para quem está começando a investir, com dados oficiais atualizados automaticamente.**

🔗 **Site:** https://mathlpereira.github.io/Mercado-Financeiro/

---

## O problema

Quem quer começar a investir encontra dois extremos: conteúdo superficial ou linguagem técnica demais, quase sempre sem números atualizados. Conceitos como Selic, CDI, Tesouro Direto e CDB costumam ser confundidos, e a decisão mais importante (onde o dinheiro rende mais *hoje*, já com imposto) exige contas que poucas pessoas sabem fazer.

## A solução

Um site gratuito, sem cadastro, organizado em três áreas:

- **Investimentos:** um mapa interativo com 14 tipos de investimento, posicionados por risco, potencial de retorno e liquidez, e uma trilha de 9 módulos (do "por que investir" ao "monte seu plano").
- **Bolsa:** um globo 3D com o dia e a noite reais e as principais bolsas do mundo, abertas ou fechadas no momento, e uma trilha de 5 módulos sobre ações, dividendos, índices, ETFs, fundos imobiliários e câmbio.
- **Simuladores:** reserva de emergência, comparação entre poupança, Tesouro Selic, CDB e LCI/LCA com imposto e taxas descontados, objetivos com inflação e quanto cada caminho teria rendido no passado.

Cada módulo tem explicação em linguagem simples, exemplo com números, um simulador com dados reais, um teste rápido e as fontes oficiais para conferir.

## Dados que se atualizam sozinhos

Um robô no **GitHub Actions** roda a cada 30 minutos nos dias úteis:

1. busca as séries oficiais do **Banco Central (SGS)**: meta Selic, CDI, IPCA, poupança e dólar PTAX;
2. busca bolsas, ações, moedas e commodities no **Yahoo Finance**;
3. grava tudo em `mercado.json`, que o site lê.

Cada fonte é independente: se uma falhar, as outras continuam, e o relatório da execução mostra o que funcionou.

## Regras de cálculo (conferidas em outubro de 2026)

- Imposto de Renda regressivo na renda fixa (22,5% a 15%) e IOF em resgates com menos de 30 dias
- LCI e LCA isentas para pessoa física, com prazo mínimo de 6 meses
- Taxa de custódia de 0,20% ao ano no Tesouro Direto, isenta até R$ 10 mil no Tesouro Selic
- Garantia do FGC de até R$ 250 mil por CPF e instituição
- Come-cotas semestral nos fundos (15% ou 20%)

Referências: ANBIMA (Como Investir), Banco Central, Tesouro Direto, B3, FGC, CVM e IBGE. Os textos são próprios; nenhum conteúdo foi copiado.

## Tecnologias

HTML, CSS e JavaScript puros, Three.js (globo 3D), Python (coleta de dados), GitHub Actions (automação) e GitHub Pages (hospedagem). Sem servidor e sem custo.

## Estrutura

```
index.html                       o site completo
terra-*.jpg / terra-*.png        imagens da Terra (NASA)
mercado.json                     dados gerados pelo robô
atualizar.py                     robô de coleta
.github/workflows/atualizar.yml  agendamento do robô
```

## Aviso

Conteúdo educativo. Não é recomendação de investimento e não substitui a orientação de um profissional certificado.

---

Criado por **Matheus** · [LinkedIn](https://www.linkedin.com/in/matheusloupe04)
