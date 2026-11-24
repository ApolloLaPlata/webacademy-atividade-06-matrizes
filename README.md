# Atividade 6 — Estruturas de Dados Básicas: Matrizes

**Curso:** Web Academy UFAC  
**Disciplina:** Algoritmos e Lógica de Programação  
**Aluno:** Vinicius Miranda de Farias

## Questão 1 — Multiplicar matriz 4 x 3 por um número n

Lê n, gera a matriz 4 x 3 com valores aleatórios de 1 a 20, imprime a matriz original e depois imprime a matriz resultante da multiplicação de cada elemento por n.

```
programa {
    inclua biblioteca Util --> u
    funcao inicio() {
        const inteiro LIN = 4, COL = 3
        inteiro M[LIN][COL], R[LIN][COL]
        inteiro n
        escreva("Digite o valor de n: ")
        leia(n)
        para (inteiro i = 0; i < LIN; i++) {
            para (inteiro j = 0; j < COL; j++) {
                M[i][j] = u.sorteia(1, 20)
            }
        }
        escreva("Matriz original:")
        para (inteiro i = 0; i < LIN; i++) {
            para (inteiro j = 0; j < COL; j++) {
                escreva(M[i][j], " ")
            }
            escreva("\n")
        }
        para (inteiro i = 0; i < LIN; i++) {
            para (inteiro j = 0; j < COL; j++) {
                R[i][j] = M[i][j] * n
            }
        }
        escreva("Matriz apos multiplicar por ", n, ":")
        para (inteiro i = 0; i < LIN; i++) {
            para (inteiro j = 0; j < COL; j++) {
                escreva(R[i][j], " ")
            }
            escreva("\n")
        }
    }
}
```

## Questão 2 — Cartela 5 x 5 sem números repetidos

Sorteia números de 0 a 99. Um vetor auxiliar `usado` controla quais números já foram sorteados, garantindo que a cartela 5 x 5 tenha 25 valores distintos.

```
programa {
    inclua biblioteca Util --> u
    funcao inicio() {
        const inteiro TAM = 5
        inteiro cartela[TAM][TAM]
        inteiro usado[100]
        para (inteiro k = 0; k < 100; k++) {
            usado[k] = 0
        }
        para (inteiro i = 0; i < TAM; i++) {
            para (inteiro j = 0; j < TAM; j++) {
                inteiro numero
                faca {
                    numero = u.sorteia(0, 99)
                } enquanto (usado[numero] == 1)
                usado[numero] = 1
                cartela[i][j] = numero
            }
        }
        escreva("Cartela gerada:")
        para (inteiro i = 0; i < TAM; i++) {
            para (inteiro j = 0; j < TAM; j++) {
                escreva(cartela[i][j], " ")
            }
            escreva("\n")
        }
    }
}
```

## Questão 3 — Nota dos alunos a partir do gabarito

A matriz 5 x 10 guarda as respostas (de A a E) dos cinco alunos. Para cada aluno, compara-se cada resposta com o gabarito; cada acerto vale 1 ponto.

```
programa {
    funcao inicio() {
        cadeia gabarito[10]
        cadeia respostas[5][10]
        para (inteiro q = 0; q < 10; q++) {
            escreva("Gabarito da questao ", q + 1, ": ")
            leia(gabarito[q])
        }
        para (inteiro a = 0; a < 5; a++) {
            para (inteiro q = 0; q < 10; q++) {
                escreva("Aluno ", a + 1, " - questao ", q + 1, ": ")
                leia(respostas[a][q])
            }
        }
        para (inteiro a = 0; a < 5; a++) {
            inteiro nota = 0
            para (inteiro q = 0; q < 10; q++) {
                se (respostas[a][q] == gabarito[q]) {
                    nota = nota + 1
                }
            }
            escreva("Aluno ", a + 1, " - nota: ", nota)
        }
    }
}
```
