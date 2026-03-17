# 📊 Databricks Data Engineering Portfolio

> Portfólio de projetos práticos de Engenharia de Dados e Machine Learning com Databricks, Delta Lake e MLflow

![Databricks](https://img.shields.io/badge/Databricks-FF3621?style=for-the-badge&logo=databricks&logoColor=white)
![Apache Spark](https://img.shields.io/badge/Apache_Spark-E25A1C?style=for-the-badge&logo=apachespark&logoColor=white)
![MLflow](https://img.shields.io/badge/MLflow-0194E2?style=for-the-badge&logo=mlflow&logoColor=white)
![Delta Lake](https://img.shields.io/badge/Delta_Lake-003366?style=for-the-badge&logo=delta&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)

---

## 🗂️ Projetos

### 🛢️ [fuel-price-pipeline-br](https://github.com/hiazevedo/fuel-price-pipeline-br)

Pipeline batch com **Medallion Architecture** processando 120.823 registros de preços de combustíveis brasileiros (ANP 2004–2021).

**Destaques:**
- Bronze → Silver → Gold com Delta Lake
- Window Functions (RANK, LAG) para análises temporais
- Tratamento de sentinelas de dados ausentes da ANP (-99999)
- 22/22 quality checks automatizados
- Dashboard Databricks SQL com 6 queries e KPIs

**Stack:** PySpark · Delta Lake · Unity Catalog · Databricks SQL · Matplotlib/Seaborn

---

### 🌍 [earthquake-streaming-pipeline](https://github.com/hiazevedo/earthquake-streaming-pipeline)

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

### 🤖 [earthquake-ml-pipeline](https://github.com/hiazevedo/earthquake-ml-pipeline)

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

### 🌦️ [weather-dlt-pipeline](https://github.com/hiazevedo/weather-dlt-pipeline)

Pipeline meteorológico com **Delta Live Tables** coletando 87 anos de dados históricos (1940→2026) e previsão em tempo real para Birigui-SP, com Workflow automatizado rodando 4x por dia.

**Destaques:**
- **87 anos de histórico** — 755.684 registros horários
- Delta Live Tables com 5 tabelas e 4 expectations de qualidade
- Tendência climática detectada: +1.41°C em 86 anos, -3.9mm/ano de chuva
- Workflow agendado às 00h, 06h, 12h, 18h (Brasília)
- Dashboard SQL com previsão do dia atualizada automaticamente

**Stack:** Delta Live Tables · Databricks Workflows · Open-Meteo API · Unity Catalog · Databricks SQL

---

### 🌧️ [weather-ml-rain-forecast](https://github.com/hiazevedo/weather-ml-rain-forecast)

Modelo de **Machine Learning para previsão de chuvas** em Birigui-SP treinado com 87 anos de dados, comparando XGBoost, RandomForest e Prophet, com retreinamento mensal automático e inferência integrada ao pipeline de dados.

**Destaques:**
- 31 features engenheiradas (lag, rolling, delta, cíclicas, flags sazonais)
- RandomForest vencedor: **AUC-ROC 0.9318** | **Recall 73.7%**
- Threshold otimizado em 0.65 para maximizar F1
- Split temporal (treino 1940–2022, teste 2024–2026) — sem data leakage
- Retreinamento mensal automático via Job separado
- Predições integradas ao dashboard em tempo real

**Stack:** Scikit-learn · MLflow · Prophet · RandomForest · XGBoost · Databricks Workflows

---

## 📈 Evolução das skills ao longo dos projetos

```
Projeto 1     Projeto 2         Projeto 3        Projeto 4         Projeto 5
────────      ────────          ────────         ────────          ────────
Batch         Streaming         ML               Delta Live        ML Avançado
Medallion     Auto Loader       Feature Eng.     Tables            Séries Temp.
SQL Analytics Watermark/Dedup   MLflow Track.    DLT Expectations  Retreinamento
Window Funcs  Risk Score        Model Registry   Workflows 4x/dia  Auto. Mensal
Quality Chks  Alertas RT        Batch Inference  Dashboard RT      Threshold Opt.
```

---

## 🏗️ Ambiente

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

## 🛠️ Skills demonstradas

| Skill | Projeto(s) |
|-------|-----------|
| Medallion Architecture | Projeto 1, 2, 3 |
| Delta Lake (ACID, Time Travel) | Projeto 1, 2, 3, 4, 5 |
| Unity Catalog + Volumes | Projeto 1, 2, 3, 4, 5 |
| PySpark (DataFrames, Window Functions) | Projeto 1, 2, 3, 4, 5 |
| Auto Loader (cloudFiles) | Projeto 2, 3 |
| Structured Streaming + Watermark | Projeto 2 |
| Delta Live Tables + Expectations | Projeto 4 |
| Databricks Workflows (agendamento) | Projeto 4, 5 |
| Feature Engineering | Projeto 3, 5 |
| MLflow Tracking + Registry | Projeto 3, 5 |
| Spark ML Pipelines | Projeto 3 |
| Scikit-learn (RF, XGBoost) | Projeto 5 |
| Prophet (séries temporais) | Projeto 5 |
| Retreinamento automático | Projeto 5 |
| Quality Checks automatizados | Projeto 1, 2, 3 |
| Databricks SQL + Dashboards | Projeto 1, 4, 5 |
| Visualizações (Matplotlib/Seaborn) | Projeto 1, 2, 3, 4 |

---

Portfólio desenvolvido com foco em projetos práticos que cobrem o ciclo completo de engenharia de dados: ingestão → transformação → qualidade → streaming → analytics → machine learning → automação.
