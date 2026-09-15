# GraphOps

## Análise de Resiliência em Malhas de Microsserviços

O **GraphOps** é um projeto desenvolvido para a disciplina de **Computabilidade e Complexidade de Algoritmos**, com o objetivo de aplicar conceitos de **teoria dos grafos e análise de complexidade** a um problema real de sistemas distribuídos.

A proposta é analisar uma arquitetura de microsserviços como um **grafo dirigido**, permitindo identificar serviços críticos, pontos únicos de falha (**SPOFs**) e avaliar o impacto causado pela indisponibilidade de um serviço.

## Objetivo

O objetivo principal do GraphOps é desenvolver uma ferramenta capaz de:

* Modelar uma arquitetura de microsserviços como um grafo dirigido;
* Identificar serviços estruturalmente críticos;
* Calcular **Betweenness Centrality** utilizando o algoritmo de Brandes;
* Simular falhas em serviços;
* Analisar possíveis falhas em cascata;
* Calcular o impacto da indisponibilidade de um serviço sobre o restante da arquitetura;
* Aplicar e analisar algoritmos estudados na disciplina em um cenário prático.

## Como funciona

Cada microsserviço da arquitetura é representado como um **vértice** do grafo.

As dependências entre os serviços são representadas pelas **arestas direcionadas**.

A partir desse modelo, o GraphOps utiliza principalmente dois algoritmos:

### Betweenness Centrality

A centralidade de intermediação permite identificar serviços que aparecem com frequência nos caminhos entre outros serviços.

Esses serviços podem representar pontos críticos da arquitetura, pois sua indisponibilidade pode afetar diversas outras partes do sistema.

O projeto utiliza o **algoritmo de Brandes** para realizar esse cálculo.

**Complexidade:** `O(V · E)`

Onde:

* `V` representa o número de vértices;
* `E` representa o número de arestas.

### BFS — Busca em Largura

A **Breadth-First Search (BFS)** é utilizada na simulação das falhas para verificar quais serviços podem ser afetados ou ficar inacessíveis após a remoção de determinado vértice.

**Complexidade:** `O(V + E)`

Com isso, o sistema consegue estimar o impacto de uma falha sobre a malha de microsserviços.

## Tecnologias utilizadas

* Python 3.10+
* Teoria dos Grafos
* Algoritmo de Brandes
* Breadth-First Search (BFS)
* JSON para representação dos grafos
* Git
* GitHub

O projeto foi desenvolvido utilizando apenas recursos da **biblioteca padrão do Python**, sem necessidade de dependências externas para o núcleo da aplicação.

## Estrutura do projeto

A organização do repositório separa os principais componentes da aplicação, incluindo:

* Implementação do grafo;
* Cálculo de Betweenness Centrality;
* Simulação de falhas em cascata;
* Dados de exemplo;
* Testes automatizados.

Um exemplo de malha de microsserviços utilizada pelo projeto está disponível em:

`data/exemplo_microsservicos.json`

Também existem testes específicos para os principais algoritmos, incluindo:

`tests/test_betweenness.py`

`tests/test_cascade.py`

## Integrantes

| Integrante                               | RA       |
| ---------------------------------------- | -------- |
| Fernando Januário                        | 38772752 |
| Luis Henrique Palacio da Conceição Silva | 37620932 |
| Gabriel Henrique Alves de Lima           | 38561310 |

## Informações acadêmicas

**Disciplina:** Computabilidade e Complexidade de Algoritmos

**Projeto:** GraphOps — Análise de Resiliência em Malhas de Microsserviços

**Orientadora:** Profa. Dra. Andréa Ono Sakai

## Status do projeto

O projeto encontra-se em desenvolvimento.

O núcleo responsável pela representação do grafo, cálculo de **Betweenness Centrality** e simulação de falhas utilizando **BFS** já foi implementado.

As próximas etapas incluem evolução das funcionalidades, geração de grafos para testes e aprimoramento da apresentação e exportação dos resultados.

---

**GraphOps — Aplicando teoria dos grafos à análise de resiliência de arquiteturas de microsserviços.**
