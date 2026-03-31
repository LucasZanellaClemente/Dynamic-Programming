# 📦 Checkpoint 1 — FIAP — Eng. Software — Dynamic Programming

> Simulação de um centro de distribuição logístico com priorização de pedidos por urgência, utilizando estruturas de dados em Python.

---

## 📋 Sobre o Projeto

Este projeto simula um **centro de distribuição logístico no Brasil**, onde pedidos são organizados em uma fila de prioridade com base na urgência de entrega. A solução foi desenvolvida em Python, aplicando conceitos de estruturas de dados, ordenação, recursão e análise de eficiência (Big O).

---

## 👥 Integrantes

| Nome | Rm |
| Lucas Zanella | 563880 |
| Daniel Oliveira | NS |
| João Pedro Marcilio | NS |
| Ben Hur Lung | NS |
| Felipe Campos | NS |

---

## 🗂️ Estruturas de Dados Utilizadas

### 📌 Tuplas
Cada linha do CSV é convertida em uma **tupla imutável**, representando um pedido completo:
```
(pedido_id, cidade_destino, produto, categoria, quantidade, valor_unitario, urgencia, tempo_estimado_horas, modal, status_pagamento)
```
Tuplas foram escolhidas por serem **imutáveis** — os dados de um pedido não devem ser alterados após o carregamento.

### 📌 Listas
A lista `pedidos_tuplas` armazena todas as tuplas de pedidos, permitindo ordenação e fatiamento para a recursão (`pedidos[1:]`).

### 📌 Dicionários
Os dados brutos vêm do CSV como dicionários via `pd.read_csv()`, sendo depois convertidos em tuplas para processamento.

### 📌 Deque
A `deque` (double-ended queue) é a estrutura central da fila de prioridade:
- `appendleft(item)` → pedidos de urgência **alta** vão para o **início**
- `append(item)` → pedidos de urgência **média/baixa** vão para o **final**

Ambas as operações são **O(1)**, tornando a deque mais eficiente que uma lista comum para esse caso.

### 📌 DataFrame (Pandas)
Usado para carregar o CSV, gerar agrupamentos e alimentar os gráficos de análise.

---

## 🔁 Recursão

A função `organizar_fila` é **recursiva**:

```python
def organizar_fila(pedidos, fila):
    if len(pedidos) == 0:   # caso base
        return fila
    item = pedidos[0]
    if item[URGENCIA_IDX] == "alta":
        fila.appendleft(item)
    else:
        fila.append(item)
    return organizar_fila(pedidos[1:], fila)  # caso recursivo
```

- **Caso base:** lista vazia → retorna a fila montada
- **Caso recursivo:** processa o primeiro pedido e chama para o restante

---

## 📊 Análise de Complexidade (Big O)

| Operação | Complexidade | Justificativa |
|----------|-------------|---------------|
| Carregamento do CSV | O(n) | Percorre todas as n linhas uma vez |
| Conversão para tuplas | O(n) | Uma tupla criada por linha |
| Ordenação dos pedidos | O(n log n) | Algoritmo Timsort do Python |
| Organização da fila (recursão) | O(n) | Cada pedido é processado uma única vez |
| Inserção na deque | O(1) | `appendleft` e `append` são constantes |
| Geração dos gráficos | O(n) | Percorre o DataFrame uma vez por gráfico |

---

## 📈 Gráficos Gerados

1. **Quantidade de Pedidos por Urgência** — gráfico de barras mostrando a distribuição entre alta, média e baixa
2. **Valor Total por Cidade de Destino** — gráfico de barras com o valor agregado por cidade
3. **Distribuição de Quantidade por Pedido** — gráfico de pizza com a proporção de cada pedido

---

## 🚀 Como Rodar o Projeto

### Pré-requisitos
- Python 3.10+
- pip

### Instalação das dependências

```bash
pip install pandas seaborn matplotlib
```

### Estrutura de arquivos esperada

```
📁 projeto/
├── exercicio.py
├── Check_point_1_dados_logistica_RA_final_par.csv
└── README.md
```

### Executando

```bash
python exercicio.py
```

Os gráficos serão exibidos em sequência e o terminal mostrará:
- O DataFrame original
- Os pedidos convertidos em tuplas
- Os pedidos ordenados por valor unitário
- A fila organizada por urgência

---

## 🛠️ Tecnologias

![Python](https://img.shields.io/badge/Python-3.10+-blue?logo=python)
![Pandas](https://img.shields.io/badge/Pandas-2.x-150458?logo=pandas)
![Seaborn](https://img.shields.io/badge/Seaborn-0.13-4C72B0)
![Matplotlib](https://img.shields.io/badge/Matplotlib-3.x-orange)

---

## 🏫 Informações Acadêmicas

- **Instituição:** FIAP
- **Curso:** Engenharia de Software
- **Disciplina:** Dynamic Programming
- **Checkpoint:** 1 — Enunciado A (RA PAR)
