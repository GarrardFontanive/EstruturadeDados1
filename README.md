# Estrutura de Dados

Repositório de estudos da disciplina de Estruturas de Dados I, com implementações em Java, exercícios de aula e trabalhos práticos.

## Conteúdos

| Pasta | Conteúdo de estudo |
| --- | --- |
| `src/nodo` | Nós simples e duplos utilizados nas estruturas encadeadas. |
| `src/encadeada` | Lista simplesmente encadeada. |
| `src/duplamenteencadeada` | Lista duplamente encadeada. |
| `src/circulares` | Lista circular. |
| `src/pilha` | Pilhas estática e dinâmica, com exemplo de inversão de texto. |
| `src/fila` | Filas estática e dinâmica, inversão de fila e sistema de caixas de supermercado. |
| `src/Hash` | Tabelas hash e tratamento de colisões, incluindo encadeamento. |
| `src/ordenacao` | Exercícios de ordenação, métricas e pré-processamento. |
| `src/work` | Trabalho 1: simulação de aeroporto com filas de aviões. |
| `src/work2` | Trabalho 2: comparação de sete algoritmos de ordenação. |

## Compilação e execução

É necessário ter um JDK instalado, com os comandos `java` e `javac` disponíveis. A configuração do IntelliJ IDEA utiliza o JDK 26.

Na raiz do projeto, em um terminal Bash com `rg` (ripgrep), compile todas as classes:

```bash
mkdir -p out
rg --files src -g '*.java' > out/fontes.txt
javac -encoding UTF-8 -d out @out/fontes.txt
java -cp out app.Main
```

Para executar os exemplos, substitua `app.Main` por uma destas classes:

```bash
java -cp out nodo.TesteNodo
java -cp out encadeada.TesteListaEncadeada
java -cp out duplamenteencadeada.TesteDuplamenteEncadeada
java -cp out circulares.TesteListaCircular
java -cp out pilha.TestePilha
java -cp out fila.TesteFila
java -cp out work.Main
```

No IntelliJ IDEA, abra o projeto, configure o JDK e execute o método `main` da classe desejada. Os exemplos são programas de demonstração dos conteúdos estudados.

## Trabalho 2: algoritmos de ordenação

O pacote `work2` implementa Bubble Sort, Insertion Sort, Selection Sort, Merge Sort, Quick Sort, Heap Sort e Shell Sort. A interface `Sorter` padroniza a execução dos algoritmos, enquanto `SortMetrics` registra comparações, movimentações e tempo de execução.

O `ExecutorTestesOrdenacao` utiliza cópias dos mesmos vetores para comparar os algoritmos. São consideradas entradas ordenadas, invertidas e aleatórias, com 100.000 e 1.000.000 de elementos e três execuções por cenário. A geração aleatória utiliza uma semente fixa para permitir a reprodução das entradas.

Para executar a comparação completa:

```bash
java -cp out work2.Main
```

A execução grava `resultados.csv` e `medias.csv` no diretório de execução. Com esses tamanhos, os algoritmos quadráticos podem levar bastante tempo para concluir os testes.

Materiais do trabalho:

- [Enunciado](src/work2/pdf/Trabalho%202%20-%20Algoritmos%20de%20Ordena%C3%A7%C3%A3o.pdf).
- [Relatório técnico e análise dos resultados](src/work2/pdf/work2.pdf).
- [Resultados individuais já coletados](src/work2/exports/resultados.csv).
- [Médias já calculadas](src/work2/exports/medias.csv).

## Roteiro de estudo

1. Comece pelos nós e acompanhe como as listas mantêm os vínculos entre os elementos.
2. Execute os exemplos de pilhas e filas, observando a ordem de inserção e remoção.
3. Estude o tratamento de colisões nas tabelas hash e o uso de filas na simulação do aeroporto.
4. Compare as implementações de ordenação e acompanhe onde são contadas as comparações e movimentações.
5. Consulte os resultados e o relatório do Trabalho 2 para relacionar o desempenho observado ao tamanho e à organização das entradas.
