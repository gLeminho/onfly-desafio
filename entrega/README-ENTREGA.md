# Relatório de Entrega — Onfly Consolidador de Reservas

## 1. Defeitos corrigidos

### 1.1. Cálculo de noites entre datas

**Arquivo:** `stay_calculator.py`

**Causa raiz:** O cálculo utilizava apenas o dia do mês (`.day`), causando resultados incorretos quando a hospedagem atravessava a virada de mês ou ano.

**Correção:** Utilização da diferença entre as datas completas, considerando a propriedade `.days` do resultado da subtração.

### 1.2. Regra de faturamento dos status

**Arquivo:** `status_policy.py`

**Causa raiz:** A implementação permitia que reservas com status `NO_SHOW` fossem consideradas faturáveis.

**Correção:** Alteração da condição para considerar exclusivamente reservas com status `CONFIRMED`.

### 1.3. Ordenação do ranking de hotéis

**Arquivo:** `report_builder.py`

**Causa raiz:** O ranking era ordenado pelo faturamento em ordem crescente, apresentando primeiro os hotéis com menor valor.

**Correção:** Ajuste da expressão lambda utilizada na ordenação para classificar o faturamento em ordem decrescente, preservando o desempate pelo identificador do hotel em ordem crescente.

### 1.4. Conversão de moedas

**Arquivo:** `currency_converter.py`

**Causa raiz:** A implementação anterior não seguia corretamente a regra de multiplicação pela taxa de câmbio e utilizava conversão para `float`, comprometendo a precisão dos valores monetários.

**Correção:** Utilização de `Decimal` e multiplicação do valor pela taxa de câmbio correspondente, preservando a precisão decimal.

## 2. Investigação e abordagem

A investigação foi realizada por meio da execução dos testes automatizados fornecidos no projeto.

Os erros foram analisados individualmente, identificando os arquivos responsáveis e comparando os resultados obtidos com as regras de negócio descritas no enunciado.

As correções foram implementadas individualmente e validadas por meio da execução dos testes.

## 3. Como validar

Executar os testes automatizados:

```bash
pytest -q
```

Executar o CLI utilizando a amostra de validação:

```bash
PYTHONPATH=src python -m onfly_report \
  --input data/exemplo-validacao.csv \
  --rates data/taxas_cambio.csv \
  --output output/exemplo.json
```

## 4. Resultado dos testes

**Resultado final:**

```text
5 passed in 0.76s
```

A amostra de validação também foi executada para conferir os totais financeiros, as noites ocupadas e o ranking dos hotéis.