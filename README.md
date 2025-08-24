# 📊 Case 5: Temporal Causal Analysis — Profile Shifts vs Purchase Behavior

[![Python](https://img.shields.io/badge/Python-3.9%2B-blue)](https://www.python.org/)
[![Apache Spark](https://img.shields.io/badge/Apache%20Spark-3.x-orange)](https://spark.apache.org/)
[![Databricks](https://img.shields.io/badge/Platform-Databricks-red)](https://databricks.com/)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

---

## 📑 Índice

1. [Visão Geral](#visão-geral)
2. [Problema e Motivação](#problema-e-motivação)
3. [Metodologia](#metodologia)
4. [Arquitetura do Pipeline](#arquitetura-do-pipeline)
5. [Instruções de Uso](#instruções-de-uso)
6. [Resultados Esperados](#resultados-esperados)
7. [Próximos Passos](#próximos-passos)
8. [Licença](#licença)

---

## 🚀 Visão Geral

Este repositório apresenta o **Case 5 da série “5 Cases Avançados de Data Science na Prática”**.
O foco é a **Análise Causal Temporal em séries temporais**, investigando como **mudanças de perfis de clientes (clusterização dinâmica)** impactam o **comportamento de compra** ao longo do tempo.

---

## 🎯 Problema e Motivação

📌 Desafio: Em ambientes dinâmicos, clientes podem mudar de perfil (ex.: “alto ticket” → “baixo ticket”) ao longo do tempo.
❓ Pergunta: Essas mudanças **causam impacto real** no comportamento de compra ou são apenas correlação espúria?

Este case aplica técnicas avançadas de **inferência causal temporal** para responder a essa questão.

---

## 🧩 Metodologia

* **Clusterização Dinâmica** (RFMT + PCA + KMeans)
* **Tracking Temporal** de perfis por cliente
* **Inferência Causal Temporal** via:

  * Granger Causality
  * CausalImpact (Bayesian Structural Time Series)
  * Placebo Tests para validação robusta

---

## 🏗 Arquitetura do Pipeline

1. Pré-processamento (Spark-native, DBFS)
2. Extração de atributos comportamentais
3. Clusterização dinâmica (perfis latentes)
4. Tracking temporal de transições de perfis
5. Modelagem causal: efeito do shift de perfil sobre compras
6. Visualizações e métricas finais

---

## ⚡ Instruções de Uso

### 🔹 Pré-requisitos

* Databricks Runtime 12.x (ou Spark 3.3+)
* Python 3.9+
* Bibliotecas: `pyspark`, `pandas`, `numpy`, `statsmodels`, `matplotlib`, `scipy`, `mlflow`

### 🔹 Execução no Databricks

1. Clone o repositório no seu workspace:

   ```bash
   git clone https://github.com/seu-usuario/case5-temporal-causal-analysis.git
   ```
2. Abra o notebook `Case5_Temporal_Causal_Analysis.ipynb` no Databricks.
3. Configure os caminhos do DBFS para entrada/saída.
4. Execute as células sequencialmente.

---

## 📈 Resultados Esperados

* **Causalidade validada**: identificação de perfis cuja transição **impacta estatisticamente** o comportamento de compra.
* **Visualizações robustas**: gráficos de causal impact mostrando mudanças antes/depois.
* **Cenários de negócio**: insights sobre **qual perfil “puxa” maior LTV** ou **risco de churn** após mudança.
