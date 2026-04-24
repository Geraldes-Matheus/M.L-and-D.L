# 🔬 Predição da Temperatura Crítica de Supercondutores com Machine Learning

[![Python 3.9+](https://img.shields.io/badge/python-3.9+-blue.svg)](https://www.python.org/downloads/)
[![TensorFlow](https://img.shields.io/badge/TensorFlow-2.13-orange.svg)](https://tensorflow.org)
[![XGBoost](https://img.shields.io/badge/XGBoost-1.7-brightgreen.svg)](https://xgboost.ai)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Code style: black](https://img.shields.io/badge/code%20style-black-000000.svg)](https://github.com/psf/black)

**Autor:** Matheus da Costa Geraldes  
**Trabalho de graduação** – Estado Sólido, Instituto de Física Armando Dias Tavares (UERJ)  
**Repositório GitHub:** [Geraldes-Matheus/M.L-and-D.L](https://github.com/Geraldes-Matheus/M.L-and-D.L)

---

## 🎯 Visão Geral

A descoberta de novos materiais supercondutores é um processo caro e demorado. Este projeto aplica técnicas de **Machine Learning** e **Deep Learning** para prever a **temperatura crítica (Tc)** de um supercondutor a partir apenas de sua **fórmula química**, funcionando como um filtro computacional que acelera a pesquisa experimental.

✅ **Resultado principal:** O modelo **XGBoost** atinge **RMSE de 9.8 K** e **R² de 0.92**, superando a regressão linear e redes neurais.

---

## 📊 Dataset

- **Fonte:** [UCI Machine Learning Repository – Superconductivity Data](https://archive.ics.uci.edu/dataset/464/superconductivity+data)  
- **Tamanho:** 21.263 supercondutores, 81 features numéricas  
- **Features:** Estatísticas de propriedades dos elementos químicos (massa atômica, raio atômico, condutividade térmica, valência, etc.)  
- **Alvo:** `critical_temp` – Temperatura Crítica em Kelvin

---

## 🧠 Modelos Avaliados

| Modelo | RMSE (K) | MAE (K) | R² | CV-RMSE (5-fold) |
|--------|----------|---------|----|------------------|
| Regressão Linear (baseline) | 18.12 | 10.45 | 0.72 | 18.30 |
| **XGBoost** | **9.80** | **5.92** | **0.92** | **9.95** |
| MLP (Rede Neural) | 13.29 | 7.83 | 0.85 | — |

> O XGBoost supera consistentemente os outros modelos, tanto em teste quanto em validação cruzada.

---

## 🔍 Principais Insights

- A feature mais importante para predizer a Tc é `range_ThermalConductivity` (faixa de condutividade térmica dos elementos químicos).
- A transformação logarítmica da variável alvo (`log(1+Tc)`) reduz a assimetria da distribuição e melhora o desempenho.
- SHAP values revelam que materiais com alta variabilidade na condutividade térmica tendem a ter Tc mais elevada.

---
