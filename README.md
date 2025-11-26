# Atividade-7---Perceptron-

# 🧠 Perceptron Simples - Relatório de Treinamento

Este documento detalha o processo de treinamento de uma rede neural **Perceptron de Camada Única** (Single Layer Perceptron), resolvendo o exercício de classificação binária proposto em aula.

## 📋 Definição do Problema

O objetivo é classificar se um aluno foi **Aprovado (1)** ou **Reprovado (0)** com base em dois atributos de entrada.

### Base de Dados

| Aluno | Bias ($x_0$) | Estudou ($x_1$) | Fez Trabalho ($x_2$) | **Passou? ($y$)** |
| :--- | :---: | :---: | :---: | :---: |
| **Joãozinho** | 1 | 0 | 0 | **0** (Não) |
| **Huguinho** | 1 | 0 | 1 | **0** (Não) |
| **Zezinho** | 1 | 1 | 0 | **1** (Sim) |
| **Luizinho** | 1 | 1 | 1 | **1** (Sim) |

### Parâmetros de Configuração
* **Vetor de Pesos Inicial ($W$):** `[0.0, 0.0, 0.0]` (Bias, $x_1$, $x_2$)
* **Taxa de Aprendizado ($\alpha$):** `0.1`
* **Função de Ativação:** Degrau (Step Function)
    * Se Soma > 0 → Saída 1
    * Se Soma ≤ 0 → Saída 0

---

## 🚀 Log de Execução (Passo a Passo)

Abaixo está o rastreamento das atualizações dos pesos sinápticos durante as duas épocas de treinamento solicitadas.

### 🔄 ÉPOCA 1

1.  **Aluno: Joãozinho** (Entrada: `[1, 0, 0]`)
    * Soma: $0.00$ ➔ Saída $h(x): 0$
    * Erro ($0 - 0$): `0`
    * *Ação: Nenhuma atualização.*

2.  **Aluno: Huguinho** (Entrada: `[1, 0, 1]`)
    * Soma: $0.00$ ➔ Saída $h(x): 0$
    * Erro ($0 - 0$): `0`
    * *Ação: Nenhuma atualização.*

3.  **Aluno: Zezinho** (Entrada: `[1, 1, 0]`)
    * Soma: $0.00$ ➔ Saída $h(x): 0$
    * Esperado: $1$ ➔ **Erro: 1**
    * **⚠️ ATUALIZAÇÃO DE PESOS:**
        > $W_{novo} = [0.0, 0.0, 0.0] + (0.1 \times 1 \times [1, 1, 0])$
        >
        > **Novo $W$:** `[0.1, 0.1, 0.0]`

4.  **Aluno: Luizinho** (Entrada: `[1, 1, 1]`)
    * Soma: $0.20$ ➔ Saída $h(x): 1$ (Pois $0.2 > 0$)
    * Erro ($1 - 1$): `0`
    * *Ação: Nenhuma atualização.*

**📌 Status Fim da Época 1:** `[0.1, 0.1, 0.0]`

---

### 🔄 ÉPOCA 2

1.  **Aluno: Joãozinho** (Entrada: `[1, 0, 0]`)
    * Soma: $0.10$ ➔ Saída $h(x): 1$
    * Esperado: $0$ ➔ **Erro: -1**
    * **⚠️ ATUALIZAÇÃO DE PESOS:**
        > $W_{novo} = [0.1, 0.1, 0.0] + (0.1 \times -1 \times [1, 0, 0])$
        >
        > **Novo $W$:** `[0.0, 0.1, 0.0]`

2.  **Aluno: Huguinho** (Entrada: `[1, 0, 1]`)
    * Soma: $0.00$ ➔ Saída $h(x): 0$
    * Erro ($0 - 0$): `0`
    * *Ação: Nenhuma atualização.*

3.  **Aluno: Zezinho** (Entrada: `[1, 1, 0]`)
    * Soma: $0.10$ ➔ Saída $h(x): 1$
    * Erro ($1 - 1$): `0`
    * *Ação: Nenhuma atualização.*

4.  **Aluno: Luizinho** (Entrada: `[1, 1, 1]`)
    * Soma: $0.10$ ➔ Saída $h(x): 1$
    * Erro ($1 - 1$): `0`
    * *Ação: Nenhuma atualização.*

**📌 Status Fim da Época 2:** `[0.0, 0.1, 0.0]`

---

## ✅ Resultado Final

Após 2 ciclos de treinamento, os pesos convergirão para os seguintes valores:

| Parâmetro | Valor Final | Interpretação |
| :--- | :---: | :--- |
| **Bias ($\theta_0$)** | **0.0** | Limiar de ativação neutro. |
| **Peso Estudou ($\theta_1$)** | **0.1** | O atributo "Estudou" tem peso positivo decisivo na aprovação. |
| **Peso Trabalho ($\theta_2$)** | **0.0** | O atributo "Fez Trabalho" terminou irrelevante para a classificação neste estágio. |
