[README.md](https://github.com/user-attachments/files/33943864/README.md)
# Modelo de Linguagem Simples

Um modelo de linguagem de bigrama de caracteres em Python puro, feito para aprender como tudo começa: **prever a próxima letra dado o contexto anterior**.

Ele lê um texto, conta quais letras costumam vir depois de quais outras e usa essas contagens para gerar texto novo, letra por letra.

## Exemplo de saída

```
ara pide sa ca lom e ela a ra
orege dapape posa pe sa arosto aroresa pomesarrta prapa paposare rrdastoreguichol
```

Não faz sentido como frase, mas repare que ele imita o "jeito" do texto de treino (combinações como `ra`, `or`, `co`). Isso é o que o modelo aprendeu por contagem.

## Como rodar

Só precisa de Python 3.8 ou superior. Não há dependências externas.

```bash
python modelo_linguagem_simples.py
```

Opções:

| Opção | O que faz | Padrão |
|---|---|---|
| `--arquivo` | Treina com o seu próprio arquivo `.txt` | texto de exemplo |
| `--inicio` | Letra com que o texto gerado começa | `a` |
| `--tamanho` | Quantidade de letras geradas | `200` |
| `--semente` | Número fixo para repetir sempre o mesmo resultado | aleatório |

Exemplos:

```bash
# Mais letras, resultado repetível
python modelo_linguagem_simples.py --tamanho 300 --semente 42

# Treinando com outro texto
python modelo_linguagem_simples.py --arquivo meu_texto.txt --inicio m
```

Quanto maior e mais variado o texto de treino, mais parecido com a língua original fica o resultado.

## Como funciona

1. **Treino** (`treinar`): percorre o texto e conta, para cada letra, quais letras vieram logo depois e quantas vezes.
2. **Sorteio** (`escolher_proxima_letra`): dada a letra atual, sorteia a próxima, com mais chance para as que apareceram mais vezes.
3. **Geração** (`gerar_texto`): repete o sorteio várias vezes, usando sempre a última letra gerada como base.

## Licença

[MIT](LICENSE)
