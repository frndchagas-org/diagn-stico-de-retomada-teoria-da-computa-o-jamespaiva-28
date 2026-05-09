[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/zHqjFsRx)
# Diagnóstico de retomada - Teoria da Computação

Esta atividade serve para mapear o que você já domina sobre linguagens formais, autômatos, gramáticas e computabilidade.

Responda individualmente. Use suas palavras. Se usar IA depois da primeira tentativa, registre o uso na seção 7.

## 1. Mapa do que eu lembro

Marque cada tópico como: lembro bem, lembro parcialmente, não lembro, nunca vi ou não tenho certeza.

- alfabeto: lembro bem
- cadeia: lembro bem
- linguagem: lembro bem
- gramática: lembro bem
- autômato finito: lembro bem
- linguagem regular: lembro bem
- linguagem livre de contexto: lembro parcialmente
- linguagem sensível ao contexto: lembro parcialmente
- linguagem irrestrita: não lembro
- hierarquia de Chomsky: não tenho certeza
- computabilidade: não tenho certeza
- máquina de Turing: lembro parcialmente

## 2. Definições com exemplo

Explique, com suas palavras e com um exemplo simples, usando o alfabeto `Sigma = {a, b}`.

1. O que é um alfabeto? conjunto finito de símbolos
2. O que é uma cadeia? sequência de símbolos do alfabeto
3. O que é uma linguagem? basicamente um conjunto de cadeias
4. O que é uma gramática? o conjunto de regras como gerar as cadeias

## 3. Linguagens

Considere as linguagens:

```text
L1 = { w em {0,1}* | w termina com 01 }
L2 = { a^n b^n | n >= 0 }
L3 = { a^n b^n c^n | n >= 0 }
```

Para cada linguagem:


L1:
1. escreva três palavras que pertencem à linguagem; 01, 101, 111101
2. escreva duas palavras que não pertencem; 00 110 ou seja termina em 0
3. diga, se souber, em qual classe ela provavelmente se encaixa; regular
4. explique o motivo em linguagem simples. NÃO ENTENDE A PERGUNTA


L2:
1. escreva três palavras que pertencem à linguagem; vazio, ab, aaabbb
2. escreva duas palavras que não pertencem; abb, ba
3. diga, se souber, em qual classe ela provavelmente se encaixa; Livre de Contexto
4. explique o motivo em linguagem simples. NÃO ENTENDE A PERGUNTA

L3:
1. escreva três palavras que pertencem à linguagem; vazio, abc, aabbcc
2. escreva duas palavras que não pertencem; aabbc *falta o c, abcc * falta um b
3. diga, se souber, em qual classe ela provavelmente se encaixa; Sensível ao Contexto
4. explique o motivo em linguagem simples. NÃO ENTENDE A PERGUNTA

Não há problema em dizer "não sei". Nesse caso, escreva o que te deixou em dúvida.

## 4. Autômato finito

Considere o autômato abaixo, sobre o alfabeto `{0,1}`:

```text
Estados: q0, q1, q2
Estado inicial: q0
Estado final: q2

Transições:
q0 --0--> q1
q0 --1--> q0
q1 --0--> q1
q1 --1--> q2
q2 --0--> q1
q2 --1--> q0
```

Responda:

1. Qual linguagem esse autômato parece reconhecer? reconhece cadeias com sequencia 01
2. Execute manualmente as cadeias abaixo e diga se aceita ou rejeita:
   - `01` ACEITA
   - `101` ACEITA
   - `100` REJEITA
   - `1101` ACEITA
   - `111` REJEITA
3. Monte uma tabela curta mostrando o caminho dos estados para pelo menos duas cadeias.

Cadeia: 101 (ACEITA)
+---------+---------+-----------+----------------+

| Entrada | Origem  | Símbolo   | Estado Destino |
+---------+---------+-----------+----------------+

| (início)|    -    |     -     |       q0       |
|    1    |   q0    |     1     |       q0       |
|    2    |   q0    |     0     |       q1       |
|    3    |   q1    |     1     |       q2       |
+---------+---------+-----------+----------------+
Resultado Final: q2 (Estado de Aceitação)

Cadeia: 110 (REJEITADA)
+---------+---------+-----------+----------------+

| Entrada | Origem  | Símbolo   | Estado Destino |
+---------+---------+-----------+----------------+

| (início)|    -    |     -     |       q0       |
|    1    |   q0    |     1     |       q0       |
|    2    |   q0    |     1     |       q0       |
|    3    |   q0    |     0     |       q1       |
+---------+---------+-----------+----------------+
Resultado Final: q1 (Não é estado de aceitação)


## 5. Gramática

Considere a gramática:

```text
S -> aS
S -> b
```

Responda:

1. Gere cinco cadeias produzidas por essa gramática.
   
b (Aplicando S -> b diretamente)
ab (Aplicando S -> aS e depois S -> b)
aab (Aplicando S -> aS, S -> aS, e depois S -> b)
aaab (Aplicando S -> aS três vezes e depois S -> b)
aaaab (Aplicando S -> aS quatro vezes e depois S -> b)

2. Descreva a linguagem em palavras.
   A linguagem é formada por todas as cadeias que contêm zero ou mais letras 'a', seguidas obrigatoriamente por uma única letra 'b' no final
   
3. Essa gramática parece regular, livre de contexto ou outra classe? Justifique de forma simples.

Regular
seguem um padrão fixo, sem precisar "contar" ou "equilibrar" letras. É só repetir o 'a' e fechar com 'b'


## 6. Ponto de dificuldade

Escolha um tópico da lista inicial e escreva: Hierarquia de Chomsky

1. o que você entende dele; Apenas que divide as linguagens em 4 níveis
2. onde você se confunde; TUDO
3. que tipo de explicação ajudaria: desenho, exemplo, exercício guiado, analogia, prova passo a passo ou lista curta: Analogia e Lista Curta.

## 7. Uso de IA, se houver

Se você usou IA depois da primeira tentativa, registre:

```text
Pergunta feita: Monte uma tabela curta mostrando o caminho dos estados para pelo menos duas cadeias (101 e 110)
Resumo da resposta: IA gerou duas tabelas de rastreamento
Como eu verifiquei:  passo a passo manualmente seguindo as regras de transição e bati os resultados com a tabela.
O que eu alterei na minha resposta: Ajustei a formatação visual das tabelas para ficarem mais legíveis em texto puro
O que ainda não entendi: dúvida sobre como desenhar o diagrama de estados sem me perder quando a cadeia é longa mais complexa
```

## Submissão no Moodle

Depois de finalizar, copie no Moodle:

```text
Repositório:
Commit final:
Autoavaliação: nível atual, maior dificuldade e tópico que precisa ser retomado.
```
