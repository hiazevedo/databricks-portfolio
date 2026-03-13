# Databricks Data Engineering Portfolio

> Portfólio de projetos práticos de Engenharia de Dados e Machine Learning com Databricks, Delta Lake e MLflow

![Databricks](https://img.shields.io/badge/Databricks-FF3621?style=for-the-badge&logo=databricks&logoColor=white)
![Apache Spark](https://img.shields.io/badge/Apache_Spark-E25A1C?style=for-the-badge&logo=apachespark&logoColor=white)
![MLflow](https://img.shields.io/badge/MLflow-0194E2?style=for-the-badge&logo=mlflow&logoColor=white)
![Delta Lake](https://img.shields.io/badge/Delta_Lake-003366?style=for-the-badge&logo=delta&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)

---

## Projetos

### [Semana 1 — fuel-price-pipeline-br](./fuel-price-pipeline-br)

Pipeline batch com **Medallion Architecture** processando 120.823 registros de preços de combustíveis brasileiros (ANP 2004–2021).

**Destaques:**
- Bronze → Silver → Gold com Delta Lake
- Window Functions (RANK, LAG) para análises temporais
- Tratamento de sentinelas de dados ausentes da ANP
- 22/22 quality checks automatizados
- Dashboard Databricks SQL com 6 queries e KPIs

**Stack:** PySpark · Delta Lake · Unity Catalog · Databricks SQL · Matplotlib/Seaborn

---

### [Semana 2 — earthquake-streaming-pipeline](./earthquake-streaming-pipeline)

Pipeline de **streaming em tempo real** coletando dados sísmicos da API USGS com Auto Loader e Structured Streaming.

**Destaques:**
- Auto Loader com schema explícito (cloudFiles)
- Structured Streaming com watermark e deduplicação
- Sistema de alertas com Risk Score calculado em tempo real
- Enriquecimento geográfico em 7 regiões globais
- 29/29 quality checks automatizados
- Loop de micro-batches para simular streaming contínuo

**Stack:** Auto Loader · Structured Streaming · Delta Lake · USGS API · Matplotlib/Seaborn

---

### [Semana 3 — earthquake-ml-pipeline](./earthquake-ml-pipeline)

Pipeline completo de **Machine Learning** com 28.700 eventos sísmicos reais, feature engineering avançado e registro de modelos no MLflow.

**Destaques:**
- Feature engineering com encoding cíclico, log transform e flags geográficas
- 5 modelos treinados e comparados com MLflow tracking
- RandomForest: **F1 0.9888** (classificação) e **R² 0.9881** (regressão)
- Matriz de confusão e Feature Importance por classe
- Modelos registrados no MLflow Registry (v1)
- Batch inference em 28.700 registros com predições salvas em Delta

**Stack:** Spark ML · MLflow · RandomForest · Delta Lake · Feature Store · Matplotlib/Seaborn

---

## Evolução das skills ao longo dos projetos

```
Semana 1        Semana 2              Semana 3
────────        ────────              ────────
Batch           Streaming             Machine Learning
Medallion       Auto Loader           Feature Engineering
SQL Analytics   Structured Stream     MLflow Tracking
Window Funcs    Watermark/Dedup       Model Registry
Quality Checks  Risk Score/Alerts     Batch Inference
```

---

## Ambiente

Todos os projetos foram desenvolvidos e testados no **Databricks Free Edition** com as seguintes configurações:

| Configuração | Valor |
|-------------|-------|
| Compute | Serverless (AWS) |
| Catalog | Unity Catalog |
| Spark | 3.5+ |
| Python | 3.12 |
| Delta Lake | 3.x |
| MLflow | 2.x |

---

## Skills demonstradas

| Skill | Projeto(s) |
|-------|-----------|
| Medallion Architecture | Semana 1, 2, 3 |
| Delta Lake (ACID, Time Travel) | Semana 1, 2, 3 |
| Unity Catalog + Volumes | Semana 1, 2, 3 |
| PySpark (DataFrames, Window Functions) | Semana 1, 2, 3 |
| Auto Loader (cloudFiles) | Semana 2, 3 |
| Structured Streaming + Watermark | Semana 2 |
| Feature Engineering | Semana 3 |
| MLflow Tracking + Registry | Semana 3 |
| Spark ML Pipelines | Semana 3 |
| Quality Checks automatizados | Semana 1, 2, 3 |
| Databricks SQL + Dashboards | Semana 1 |
| Visualizações (Matplotlib/Seaborn) | Semana 1, 2, 3 |

---
