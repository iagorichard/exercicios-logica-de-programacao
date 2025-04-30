## Desafio 01 - Validador de Triângulo

### Enunciado:
Dado três números inteiros positivos `a`, `b` e `c`, represente os comprimentos de três lados.

Você deve **determinar se esses lados podem formar um triângulo válido**, e se sim, **classificá-lo como**:
- **Equilátero** (todos os lados iguais),
- **Isósceles** (dois lados iguais),
- **Escaleno** (todos os lados diferentes).

Se os lados não puderem formar um triângulo, retorne a string `"Não é um triângulo"`.

### Regras para formar um triângulo:
Os valores `a`, `b`, `c` formam um triângulo se:
- a < b + c
- b < a + c
- c < a + b


### Entrada:
Três números inteiros positivos `a`, `b` e `c`.

### Saída:
Uma string que será:
- `"Equilátero"`  
- `"Isósceles"`  
- `"Escaleno"`  
- ou `"Não é um triângulo"`

### Exemplos:

#### Exemplo 1:
Entrada:  
`a = 3, b = 3, c = 3`  
Saída:  
`"Equilátero"`

#### Exemplo 2:
Entrada:  
`a = 3, b = 4, c = 5`  
Saída:  
`"Escaleno"`

#### Exemplo 3:
Entrada:  
`a = 1, b = 2, c = 3`  
Saída:  
`"Não é um triângulo"`

#### Exemplo 4:
Entrada:  
`a = 2, b = 2, c = 3`  
Saída:  
`"Isósceles"`

## Desafio 02 - Classificador de Pontuação de Prova

### Enunciado:
Você está desenvolvendo um sistema para classificar o desempenho de um aluno em uma prova composta por 4 questões, cada uma valendo no máximo 25 pontos.

Você deve receber 4 valores inteiros `q1`, `q2`, `q3`, `q4`, representando as notas obtidas em cada questão.

Com base na soma total da pontuação, e em regras específicas, seu programa deve classificar o desempenho do aluno da seguinte forma:

- `"Inválido"` se qualquer nota for negativa ou maior que 25.
- `"Reprovado"` se a soma for menor que 50.
- `"Regular"` se a soma estiver entre 50 (inclusive) e 74 (inclusive), **mas nenhuma das notas for zero**.
- `"Bom"` se a soma estiver entre 75 (inclusive) e 89 (inclusive), e **pelo menos uma das questões tiver nota máxima (25)**.
- `"Excelente"` se a soma for **90 ou mais**, **e nenhuma das notas for menor que 20**.

Caso nenhuma das condições acima se aplique, classifique como `"Desempenho indefinido"`.

### Entrada:
Quatro números inteiros `q1`, `q2`, `q3`, `q4`, representando as notas de cada questão.

### Saída:
Uma string representando o desempenho do aluno.

### Exemplos:

#### Exemplo 1:
Entrada:  
`q1 = 20, q2 = 25, q3 = 20, q4 = 25`  
Saída:  
`"Excelente"`

#### Exemplo 2:
Entrada:  
`q1 = 25, q2 = 25, q3 = 25, q4 = 10`  
Saída:  
`"Bom"`

#### Exemplo 3:
Entrada:  
`q1 = 10, q2 = 15, q3 = 20, q4 = 5`  
Saída:  
`"Regular"`

#### Exemplo 4:
Entrada:  
`q1 = 25, q2 = 25, q3 = 25, q4 = 26`  
Saída:  
`"Inválido"`

#### Exemplo 5:
Entrada:  
`q1 = 0, q2 = 25, q3 = 25, q4 = 25`  
Saída:  
`"Reprovado"`

## Desafio 03 - Sistema de Avaliação de Risco para Empréstimo

### Enunciado:
Você está implementando um sistema de avaliação de risco para concessão de empréstimos. O sistema avalia quatro critérios do solicitante:

- `idade` (inteiro em anos)
- `salario_mensal` (float em mil reais)
- `tempo_emprego` (inteiro em meses)
- `possui_dividas` (booleano: `true` ou `false`)

Com base nesses critérios, o sistema deve classificar o risco do solicitante como:

#### Regras:
- Se **qualquer critério for inválido** (idade < 18 ou > 100, salário < 0, tempo_emprego < 0), retorne `"Dados inválidos"`.
- Se `possui_dividas` for `true` **e** o `tempo_emprego` for menor que 12 meses, risco é `"Alto"`.
- Se o `salario_mensal` for menor que 2 **e** o `tempo_emprego` menor que 6, risco é `"Alto"`.
- Se a `idade` estiver entre 18 e 25 **e** o `salario_mensal` for menor que 3, risco é `"Moderado"`.
- Se a `idade` for maior que 60 **e** o `tempo_emprego` for menor que 24, risco é `"Moderado"`.
- Se `possui_dividas` for `true` **mas** tempo_emprego for **acima de 36 meses**, risco é `"Moderado"`.
- Se o `salario_mensal` for maior ou igual a 5 **e** o `tempo_emprego` maior ou igual a 36 **e** `possui_dividas` for `false`, risco é `"Baixo"`.
- Caso nenhuma condição acima seja satisfeita, retorne `"Risco Indefinido"`.

### Entrada:
- `idade` (inteiro)
- `salario_mensal` (float)
- `tempo_emprego` (inteiro)
- `possui_dividas` (booleano)

### Saída:
Uma string indicando o risco: `"Alto"`, `"Moderado"`, `"Baixo"`, `"Dados inválidos"` ou `"Risco Indefinido"`

### Exemplos:

#### Exemplo 1:
Entrada:  
`idade = 22`  
`salario_mensal = 2.5`  
`tempo_emprego = 10`  
`possui_dividas = false`  
Saída:  
`"Moderado"`

#### Exemplo 2:
Entrada:  
`idade = 30`  
`salario_mensal = 5.5`  
`tempo_emprego = 40`  
`possui_dividas = false`  
Saída:  
`"Baixo"`

#### Exemplo 3:
Entrada:  
`idade = 65`  
`salario_mensal = 4.0`  
`tempo_emprego = 12`  
`possui_dividas = false`  
Saída:  
`"Moderado"`

#### Exemplo 4:
Entrada:  
`idade = 27`  
`salario_mensal = 1.5`  
`tempo_emprego = 3`  
`possui_dividas = true`  
Saída:  
`"Alto"`

#### Exemplo 5:
Entrada:  
`idade = 17`  
`salario_mensal = 2.0`  
`tempo_emprego = 6`  
`possui_dividas = false`  
Saída:  
`"Dados inválidos"`

