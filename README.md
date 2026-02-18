# 🛑 Teste A/B: Análise de Nova Landing Page de E-commerce

## 📋 Sobre o Projeto
Uma empresa de e-commerce desenvolveu uma nova página de destino (*landing page*) com o objetivo de aumentar a taxa de conversão de vendas. Antes de realizar a mudança global, foi executado um Teste A/B para validar estatisticamente se a nova versão (Grupo de Tratamento) superava a versão antiga (Grupo de Controlo).

**Resultado Final:** A análise indicou que a nova página **não** obteve um desempenho superior, recomendando-se a manutenção da página original.

## 🛠️ Tecnologias Utilizadas
* **Python:** Linguagem principal.
* **Pandas:** Limpeza e manipulação de dados (Data Wrangling).
* **Statsmodels:** Testes estatísticos (Z-Test para proporções).
* **Matplotlib:** Visualização de dados e Intervalos de Confiança.

## 🔍 O Processo de Análise

### 1. Tratamento de Dados (Data Cleaning)
O *dataset* original continha cerca de 294.000 registos. Durante a fase de exploração, identificaram-se inconsistências graves:
* **Mismatch de Grupos:** Foram removidas **3.893 linhas** onde o utilizador do grupo de controlo visualizou a página nova (ou vice-versa), o que invalidaria o teste.
* **Duplicados:** Remoção de IDs de utilizadores repetidos para garantir a independência das amostras.

### 2. Análise Exploratória
Após a limpeza, as taxas de conversão observadas foram:
* **Grupo Controlo (A):** 12.04%
* **Grupo Tratamento (B):** 11.88%

A uma primeira vista, a nova página apresentou um desempenho inferior à original.

### 3. Validação Estatística
Aplicou-se um **Z-Test para Proporções** (Unilateral à Direita) com um nível de confiança de 95% ($\alpha = 0.05$).

* **Hipótese Nula ($H_0$):** $p_{novo} \leq p_{antigo}$ (A nova página não é melhor).
* **Hipótese Alternativa ($H_1$):** $p_{novo} > p_{antigo}$ (A nova página é melhor).

## 📊 Resultados e Conclusão

| Métrica | Valor |
| :--- | :--- |
| **Z-Score** | -1.3109 |
| **P-Valor** | 0.9051 |

### Interpretação
O **P-Valor de 0.9051** é muito superior ao nível de significância de 0.05. Isto significa que **falhamos em rejeitar a Hipótese Nula**. Não há evidências estatísticas de que a nova página gere mais conversões. Pelo contrário, existe uma probabilidade alta de que o resultado inferior seja apenas fruto do acaso ou que a página seja, de facto, pior.

## 🚀 Recomendação de Negócio
Com base nos dados, a recomendação estratégica para a direção é:

1.  **Não implementar a nova Landing Page:** A mudança não traria aumento de receita e poderia reduzir ligeiramente a conversão.
2.  **Manter a Página Atual:** A versão original continua a ser a mais eficiente.
3.  **Economia de Recursos:** Esta análise evitou o custo de implementação e manutenção de uma funcionalidade ineficiente.

---
*Autor: Agatha Barros*
