# Sequência de Collatz

Este projeto implementa a Conjectura de Collatz, que propõe que, ao aplicar uma regra específica a qualquer número inteiro positivo, eventualmente se chega ao número 1. O programa calcula a sequência de Collatz para todos os números entre 1 e 100.000 e determina qual número gera a sequência mais longa.

## Como Funciona

A Conjectura de Collatz, também conhecida como problema 3n + 1, é simples: 

1. Se o número é par, divide-se por 2.
2. Se o número é ímpar, multiplica-se por 3 e adiciona-se 1.
3. Repete-se o processo até chegar ao número 1.

O programa consiste em duas partes principais: uma função que gera a sequência de Collatz para um número dado e um loop que percorre todos os números de 1 a 100.000, calculando o comprimento da sequência para cada um.

### Código

```python
def collatz(n):
    seq = [n]
    while n != 1:
        if n % 2 == 0:
            n //= 2
        else:
            n = 3 * n + 1
        seq.append(n)
    return seq

max_len = 0
max_num = 0
for i in range(1, 100001):
    seq_len = len(collatz(i))
    if seq_len > max_len:
        max_len = seq_len
        max_num = i

print("Maior sequência de Collatz para um número entre 1 e 100000 é", max_len, "para o número", max_num)
