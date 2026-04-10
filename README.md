


# 📦 FIAP — Eng. Software — Dynamic Programming (Checkpoint 1)

> Simulação de um Centro de Distribuição Logístico e de um Sistema de Fretes/Entregas utilizando estruturas de dados avançadas e algoritmos de ordenação em Python.

🔗 **Links Rápidos:**
- [Acessar Notebook do Projeto](INSERIR_LINK_DO_NOTEBOOK_AQUI)
- [Acessar Relatório Técnico (PDF)](INSERIR_LINK_DO_RELATORIO_AQUI)

---

## 📋 Sobre o Projeto

Este projeto propõe uma solução em Python para dois cenários logísticos reais, implementados de acordo com os requisitos (Par e Ímpar) da avaliação:

1. **Centro de Distribuição Logístico (PAR):** Fila de priorização de pedidos com base no nível de urgência (Alta, Média, Baixa) e valor unitário.
2. **Sistema de Fretes e Entregas (ÍMPAR):** Organização de cargas utilizando ordenação multicritério (Prioridade VIP/Normal, Prazos Curtos e Valor do Frete).

*Nota: Para detalhes aprofundados sobre as decisões de design, justificativas de complexidade e prints dos resultados, consulte nosso [Relatório Técnico](INSERIR_LINK_DO_RELATORIO_AQUI).*

---

## 👥 Integrantes

| Nome | RM | RA |
| :--- | :---: | :---: |
| Lucas Zanella | 563880 | PAR |
| Daniel Oliveira | 566284 | PAR |
| João Pedro Marcilio | 561603 | ÍMPAR |
| Ben Hur Lung | 561564 | PAR |
| Felipe Campos | 562752 | PAR |

---

## 🛠️ Tecnologias e Estruturas Utilizadas

A aplicação foca em eficiência e uso manual de conceitos computacionais de baixo nível, evitando funções de ordenação prontas do Python (como `.sort()`):

- **Linguagem & Análise Gráfica:** Python 3.10+, Pandas, Seaborn, Matplotlib.
- **Estruturas de Dados:** `Tuplas` (para garantir imutabilidade dos registros logísticos), `Listas` (fatiamento), `Dicionários` (mapeamento e categorização de dados) e `Deque` (garantindo inserções ponta-a-ponta eficientes).
- **Algoritmos Base:** Implementação de **Merge Sort** estável e customizado (para múltiplos critérios simultâneos) e organização da fila por meio de **Recursão**.

### 📊 Análise de Complexidade (Resumo)

| Operação Principal | Complexidade (Big O) |
|--------------------|----------------------|
| Leitura dos CSVs e conversão para Tuplas | O(n) |
| Ordenação de Pedidos/Cargas (Merge Sort) | O(n log n) |
| Organização Categórica (Recursão) | O(n) |
| Inserção de prioridades na Fila (Deque) | O(1) |

---

## 🚀 Como Rodar o Projeto

### 1. Requisitos
Certifique-se de ter o Python 3 instalado. Baixe as bibliotecas necessárias executando no terminal:
```bash
pip install pandas seaborn matplotlib
```

### 2. Estrutura de Arquivos
Baixe o repositório e certifique-se de que os arquivos de dados e o script estão no mesmo diretório:
- `Dynamic_Programing.ipynb` (ou o script `.py`)
- `Check_point_1_dados_logistica_RA_final_par.csv`
- `Check_point_1_dados_logistica_RA_final impar.csv`

### 3. Execução
Se estiver usando o **Jupyter Notebook** (ou Google Colab), basta executar todas as células sequencialmente.

Caso tenha exportado para **script Python (`.py`)**, rode no terminal:
```bash
python nome_do_script.py
```
O console exibirá todo o rastreamento das filas estruturadas de pedidos e de cargas. Ao final de cada processamento, janelas com os *Dashboards* gráficos serão abertas.