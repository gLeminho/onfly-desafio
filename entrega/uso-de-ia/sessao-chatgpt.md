# Registro de utilização — ChatGPT

## Contexto

Utilização do ChatGPT como ferramenta de apoio durante o teste técnico Onfly — Consolidador de Reservas de Hotel.

**Ferramenta:** ChatGPT  
**Modelo:** GPT-6

## Principais interações

### 1. Análise inicial do desafio

**Solicitação:** Análise do enunciado do teste técnico em Python, considerando que meu conhecimento principal é em Java.

**Apoio recebido:** Orientações sobre a estrutura do projeto, regras de negócio e conceitos de Python relacionados à experiência prévia com Java.

### 2. Correção do cálculo de noites

**Solicitação:** Ajuda para compreender a falha no teste `test_nights_across_month_boundary`, que retornava -28 noites em vez de 3.

**Apoio recebido:** Explicação sobre a diferença entre a propriedade `day` de uma data e a propriedade `days` do objeto `timedelta`, gerado pela subtração de duas datas.

**Minha participação:** Identifiquei o trecho incorreto, alterei manualmente a implementação para utilizar a diferença entre as datas completas e executei o teste.

### 3. Correção da regra de faturamento dos status

**Solicitação:** Orientação para corrigir o teste `test_status_rules_exclude_cancelled_and_no_show`.

**Apoio recebido:** Explicação sobre comparações de strings, operadores booleanos e a regra de que somente reservas `CONFIRMED` devem ser faturáveis.

**Minha participação:** Analisei a condição existente e alterei manualmente a função para considerar exclusivamente o status `CONFIRMED`.

### 4. Correção da ordenação dos hotéis

**Solicitação:** Ajuda para compreender a falha no teste `test_top_hotels_are_ranked_descending`.

**Apoio recebido:** Explicações sobre a função `sorted()`, expressões `lambda`, ordenação por múltiplos critérios e utilização do operador negativo para inverter a ordenação numérica.

**Minha participação:** Identifiquei a expressão responsável pelo ranking e alterei manualmente a chave de ordenação, preservando a ordem crescente do identificador dos hotéis em caso de empate.

### 5. Documentação e validação

**Solicitação:** Orientações para preparar o README de entrega, executar o CLI e organizar a documentação de uso de IA.

**Apoio recebido:** Sugestões de estrutura documental, comandos de execução e explicações para solucionar problemas de localização do módulo Python no Windows.

**Minha participação:** Criei e revisei os arquivos no VS Code, executei os comandos de validação e conferi os resultados.

## Observação

O ChatGPT foi utilizado como ferramenta de apoio técnico e aprendizado. As alterações no projeto foram realizadas manualmente por mim, com base na análise dos problemas e nas orientações recebidas.