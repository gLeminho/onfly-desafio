Então estou no oitavo periodo da faculdade de CC, já realizei o curso focado em orietado a objetos do proffesor Nélio Alves na Udemy, e estou em busca de emprego e em uma oportunidade passei para o teste técnico, porém pelo que vi é em Python e não tenho intimidade

Parabéns por ter passado para a fase técnica! E a boa notícia é que a sua base de orientação a objetos pesa bastante: Python é uma das linguagens mais fáceis de aprender para quem já sabe programar. O que muda é principalmente a sintaxe, não o raciocínio.

O que você já sabe e vai se traduzir direto

Variáveis, if, for, while, funções e classes funcionam com a mesma lógica, só com sintaxe diferente.
Herança, polimorfismo e encapsulamento existem em Python (de forma mais flexível).

As diferenças principais (se você veio de Java/C#)

Não há chaves {}: a indentação define os blocos.
Tipagem dinâmica: você não declara tipos (x = 10).
Classes usam __init__ no lugar do construtor e self no lugar de this (e self aparece explicitamente nos métodos).
Não existe private de verdade: usa-se convenção (_atributo).
Não há new: pessoa = Pessoa("Ana").

O que mais costuma cair em testes técnicos (e vale priorizar)

Listas, dicionários, sets e tuplas, que são a base de quase tudo em Python.
List comprehensions ([x*2 for x in lista if x > 0]).
Strings, laços e funções.
Leitura/escrita de arquivos e tratamento de exceções (try/except).
Algoritmos básicos (ordenação, busca, contagem) usando as estruturas acima.
Se a vaga pedir, noções de pandas, APIs com requests ou testes com pytest.

Como estudar pouco tempo bem

Faça um tutorial rápido focado em quem já programa (o tutorial oficial em python.org e o site W3Schools servem bem).
Pratique em plataformas como HackerRank, Exercism ou LeetCode, resolvendo problemas simples em Python.
Refaça em Python exercícios que você já resolveu em Java: a lógica você já tem, então só treina a sintaxe.

Se você me contar qual é o prazo do teste e o que a empresa disse que vai cobrar (algoritmos, API, banco de dados, etc.), eu monto um plano de estudo sob medida e podemos até praticar com exercícios aqui.

então ela jpa me mandou o desafio e quero sua ajuda para realiza-lo e entender também

Fechado, vamos fazer juntos! Só que o desafio não chegou aqui: não vejo texto nem arquivo anexado na sua mensagem.

Pode colar o enunciado completo aqui no chat (ou anexar o arquivo/PDF, se veio assim). Se tiver, mande também:

o prazo de entrega,
qualquer instrução extra (como entregar, se precisa de testes, se pode usar bibliotecas, etc.).

Como vou te ajudar

Primeiro, a gente destrincha o enunciado e eu explico o que ele está pedindo, em termos que você já conhece de Java/OO.
Depois, montamos a lógica em etapas e eu te mostro a sintaxe Python de cada parte, explicando o porquê de cada linha.
Você escreve (ou adapta) o código e eu reviso, aponto erros e sugiro melhorias.

Assim você entrega algo que realmente entende e consegue explicar caso a empresa peça uma conversa técnica sobre a solução depois, o que costuma acontecer.

Boa leitura de terminal! Esse pytest -x te mostrou três coisas úteis:

A ordem dos testes ajuda a conferir o progresso. Eles rodam em ordem alfabética: currency, nights, regression e só depois status. Como o -x parou aqui, os três primeiros passaram. Se ainda não fez o commit do bug das noites, faça agora (git add ., git commit -m "Corrige cálculo de noites", git push).
A seta > marca a primeira linha que falhou. As linhas acima dela passaram. Aqui, as contagens (total_reservations, confirmed, cancelled, no_show) estão certas. Só o total_amount_brl está errado.
O defeito não está na contagem. Ele está em quais reservas entram nos valores.
Pistas

Pista 1. O esperado é 100 e deu 120. Dos valores 100, 50 e 20, qual combinação dá 120? Isso diz exatamente quais reservas o código está tratando como faturáveis. Compare com a regra do README: “Só CONFIRMED é faturável”.

Pista 2. Abra o status_policy.py e procure a função que responde algo como “esta reserva é faturável?”. Olhe a condição dela: quantos status ela aceita, e quais? Preste atenção na diferença entre “é igual a X” e “não é igual a Y”.

Pista 3. Uma regra pode estar certa e mesmo assim não ser usada onde deveria. Depois de corrigir a função, pergunte-se: quem chama essa função? Busque no projeto por status_policy ou pelo nome da função (Ctrl+Shift+F). Tudo o que a regra diz que só CONFIRMED entra (noites, valores, by_month, top_hotels) depende de ela ser aplicada no lugar certo.

Seu turno
Tente achar o trecho e escrever a correção.
Rode pytest -x --tb=short e veja se o teste de status passa.
Se travar, cole o conteúdo do status_policy.py e me diga o que já tentou. Aí vem a próxima pista.