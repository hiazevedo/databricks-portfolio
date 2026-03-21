# Databricks Data Engineering Portfolio

> Portfólio de projetos práticos de Engenharia de Dados e Machine Learning com Databricks, Delta Lake e MLflow

![Databricks](https://img.shields.io/badge/Databricks-FF3621?style=for-the-badge&logo=databricks&logoColor=white)
![Apache Spark](https://img.shields.io/badge/Apache_Spark-E25A1C?style=for-the-badge&logo=apachespark&logoColor=white)
![MLflow](https://img.shields.io/badge/MLflow-0194E2?style=for-the-badge&logo=mlflow&logoColor=white)
![Delta Lake](https://img.shields.io/badge/Delta_Lake-003366?style=for-the-badge&logo=delta&logoColor=white)
![Unity Catalog](https://img.shields.io/badge/Unity_Catalog-0194E2?style=for-the-badge&logo=databricks&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)

---

## Projetos

| # | Repositório | Tema |
|---|-------------|------|
| 1 | [fuel-price-pipeline-br](https://github.com/hiazevedo/fuel-price-pipeline-br) | Batch · Medallion · ANP |
| 2 | [earthquake-streaming-pipeline](https://github.com/hiazevedo/earthquake-streaming-pipeline) | Streaming · Auto Loader · USGS |
| 3 | [earthquake-ml-pipeline](https://github.com/hiazevedo/earthquake-ml-pipeline) | ML · MLflow · Spark ML |
| 4 | [weather-dlt-pipeline](https://github.com/hiazevedo/weather-dlt-pipeline) | DLT · Workflows · Open-Meteo |
| 5 | [weather-ml-rain-forecast](https://github.com/hiazevedo/weather-ml-rain-forecast) | ML Avançado · Previsão de Chuva |
| 6 | [brazil-education-pipeline](https://github.com/hiazevedo/brazil-education-pipeline) | Educação · ENEM · ML · GitHub Actions |
| 7 | [brazilian-retail-lakehouse](https://github.com/hiazevedo/brazilian-retail-lakehouse) | Lakehouse Completo · Kafka · dbt · ML · Observabilidade |

---

### [fuel-price-pipeline-br](https://github.com/hiazevedo/fuel-price-pipeline-br)

Pipeline batch com **Medallion Architecture** processando 120.823 registros de preços de combustíveis brasileiros (ANP 2004–2021).

**Destaques:**
- Bronze → Silver → Gold com Delta Lake
- Window Functions (RANK, LAG) para análises temporais
- Tratamento de sentinelas de dados ausentes da ANP (-99999)
- 22/22 quality checks automatizados
- Dashboard Databricks SQL com 6 queries e KPIs

**Stack:** PySpark · Delta Lake · Unity Catalog · Databricks Asset Bundles · Databricks SQL · Matplotlib/Seaborn

---

### [earthquake-streaming-pipeline](https://github.com/hiazevedo/earthquake-streaming-pipeline)

Pipeline de **streaming em tempo real** coletando dados sísmicos da API USGS com Auto Loader e Structured Streaming.

**Destaques:**
- Auto Loader com schema explícito (cloudFiles)
- Structured Streaming com watermark e deduplicação
- Sistema de alertas com Risk Score calculado em tempo real
- Enriquecimento geográfico em 7 regiões globais
- 29/29 quality checks automatizados
- Loop de micro-batches para simular streaming contínuo

**Stack:** Auto Loader · Structured Streaming · Delta Lake · Unity Catalog · Databricks Asset Bundles · USGS API · Matplotlib/Seaborn

---

### [earthquake-ml-pipeline](https://github.com/hiazevedo/earthquake-ml-pipeline)

Pipeline completo de **Machine Learning** com 28.700 eventos sísmicos reais, feature engineering avançado e registro de modelos no MLflow.

**Destaques:**
- Feature engineering com encoding cíclico, log transform e flags geográficas
- 5 modelos treinados e comparados com MLflow tracking
- RandomForest: **F1 0.9888** (classificação) e **R² 0.9881** (regressão)
- Matriz de confusão e Feature Importance por classe
- Modelos registrados no MLflow (experiment tracking)
- Batch inference em 28.700 registros com predições salvas em Delta

**Stack:** Spark ML · MLflow · RandomForest · Delta Lake · Unity Catalog · Databricks Asset Bundles · Matplotlib/Seaborn

---

### [weather-dlt-pipeline](https://github.com/hiazevedo/weather-dlt-pipeline)

Pipeline meteorológico com **Delta Live Tables** coletando 87 anos de dados históricos (1940→2026) e previsão em tempo real para Birigui-SP, com Workflow automatizado rodando 4x por dia.

**Destaques:**
- **87 anos de histórico** — 755.684 registros horários
- Delta Live Tables com 5 tabelas e 7 expectations de qualidade
- Tendência climática detectada: +1.41°C em 86 anos, -3.9mm/ano de chuva
- Workflow agendado às 00h, 06h, 12h, 18h (Brasília)
- Dashboard SQL com previsão do dia atualizada automaticamente

**Stack:** Delta Live Tables · Databricks Workflows · Open-Meteo API · Unity Catalog · Databricks Asset Bundles · Databricks SQL

---

### [weather-ml-rain-forecast](https://github.com/hiazevedo/weather-ml-rain-forecast)

Modelo de **Machine Learning para previsão de chuvas** em Birigui-SP treinado com 87 anos de dados, comparando XGBoost, RandomForest e Prophet, com retreinamento mensal automático e inferência integrada ao pipeline de dados.

**Destaques:**
- 31 features engenheiradas (lag, rolling, delta, cíclicas, flags sazonais)
- RandomForest vencedor: **AUC-ROC 0.9318** | **Recall 73.7%**
- Threshold otimizado em 0.65 para maximizar F1
- Split temporal (treino 1940–2022, teste 2024–2026) — sem data leakage
- Retreinamento mensal automático via Job separado
- Predições integradas ao dashboard em tempo real

**Stack:** Scikit-learn · MLflow · Prophet · RandomForest · XGBoost · Unity Catalog · Databricks Asset Bundles · Databricks Workflows

---

### [brazil-education-pipeline](https://github.com/hiazevedo/brazil-education-pipeline)

Pipeline end-to-end cruzando **ENEM, Censo Escolar e IDEB** para revelar os fatores que mais impactam o desempenho educacional no Brasil, com 8 tabelas Gold analíticas, classificador ML e clustering de municípios.

**Destaques:**
- Ingestão automática anual via **GitHub Actions** (download INEP → Volume UC)
- 8 tabelas Gold: desigualdade regional, vulnerabilidade municipal, aluno improvável, gap de gênero e mais
- `infra_score` composto de 5 indicadores do Censo Escolar (energia, água, biblioteca, laboratório, internet)
- RandomForestClassifier registrado no MLflow (experiment tracking)
- K-Means agrupando ~5.500 municípios em 5 perfis educacionais
- 13 visualizações Matplotlib/Seaborn com análise narrativa

**Stack:** PySpark · Scikit-learn · MLflow · Delta Lake · Unity Catalog · Databricks Asset Bundles · GitHub Actions · Matplotlib/Seaborn

---

### [brazilian-retail-lakehouse](https://github.com/hiazevedo/brazilian-retail-lakehouse)

**Capstone do portfólio** — plataforma lakehouse end-to-end simulando o ecossistema de dados de uma rede de varejo brasileira com múltiplos domínios, desenvolvida em 6 etapas evolutivas que cobrem desde a ingestão em tempo real até operacionalização de modelos de ML com monitoramento contínuo.

**Destaques:**
- **Eventos em tempo real** — ShadowTraffic publica em 4 tópicos Kafka (vendas, estoque, clientes, pagamentos) simulando horários de pico
- **Medallion Architecture completa** — Bronze/Silver via Delta Live Tables com validações de qualidade, Gold via dbt com modelo dimensional (fct + dims + marts)
- **Contratos de dados** — 4 contratos YAML com schema, SLAs e regras de qualidade; violações CRITICAL bloqueiam o pipeline automaticamente
- **Plataforma de ML** — 2 modelos LightGBM (previsão de demanda e detecção de fraude) com Feature Store, Batch Scoring em ~750K transações e A/B test champion vs challenger
- **Observabilidade** — Health Score por domínio, SLA report e PSI drift monitoring nas features dos modelos
- **3 jobs consolidados** orquestram 15 notebooks com dependências encadeadas

**Resultados dos modelos:**

| Modelo | Algoritmo | Métricas |
|--------|-----------|---------|
| `demand_forecast` | LightGBM Regressor | RMSE=6.54 · R²=0.9999 |
| `fraud_detector` | LightGBM Classifier | F1=0.982 · AUC-ROC=1.0 · Precision=0.967 |

**Stack:** Apache Kafka · Confluent Cloud · Delta Live Tables · dbt · LightGBM · MLflow · ShadowTraffic · Unity Catalog · Databricks Asset Bundles · Databricks Workflows · Python

---

## Evolução das skills ao longo dos projetos

```
Projeto 1     Projeto 2         Projeto 3        Projeto 4         Projeto 5         Projeto 6         Projeto 7
────────      ────────          ────────         ────────          ────────          ────────          ────────
Batch         Streaming         ML               Delta Live        ML Avançado       Dados Públicos    Lakehouse Completo
Medallion     Auto Loader       Feature Eng.     Tables            Séries Temp.      GitHub Actions    Kafka + DLT + dbt
SQL Analytics Watermark/Dedup   MLflow Track.    DLT Expectations  Retreinamento     Multi-source Join Contratos de Dados
Window Funcs  Risk Score        Model Registry   Workflows 4x/dia  Threshold Opt.    Clustering        Observabilidade
Quality Chks  Alertas RT        Batch Inference  Dashboard RT      Auto. Mensal      Vulnerabilidade   Feature Store
Asset Bundles Asset Bundles     Asset Bundles    Asset Bundles     Asset Bundles     Asset Bundles     A/B Test · PSI Drift
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

Todos os projetos incluem um `databricks.yml` com **Databricks Asset Bundles** para deploy e orquestração como código.

---

## Skills demonstradas

| Skill | Projeto(s) |
|-------|-----------|
| Medallion Architecture | 1, 2, 3, 6, 7 |
| Delta Lake (ACID, Time Travel) | 1, 2, 3, 4, 5, 6, 7 |
| Unity Catalog + Volumes | 1, 2, 3, 4, 5, 6, 7 |
| Databricks Asset Bundles | 1, 2, 3, 4, 5, 6, 7 |
| PySpark (DataFrames, Window Functions) | 1, 2, 3, 4, 5, 6, 7 |
| Auto Loader (cloudFiles) | 2, 3 |
| Structured Streaming + Watermark | 2 |
| Delta Live Tables + Expectations | 4, 7 |
| Databricks Workflows (agendamento) | 4, 5, 7 |
| GitHub Actions (ingestão automática) | 6 |
| Feature Engineering | 3, 5, 6, 7 |
| MLflow Tracking | 3, 5, 6, 7 |
| Spark ML Pipelines | 3 |
| Scikit-learn (RF, XGBoost, KMeans) | 5, 6 |
| LightGBM (Regressor + Classifier) | 7 |
| Prophet (séries temporais) | 5 |
| Retreinamento automático | 5, 7 |
| Clustering não supervisionado | 6 |
| Multi-source join (3 fontes) | 6 |
| dbt (modelo dimensional) | 7 |
| Apache Kafka + Confluent Cloud | 7 |
| Contratos de Dados (YAML + validação) | 7 |
| Feature Store + Batch Scoring | 7 |
| A/B Test (champion vs challenger) | 7 |
| PSI Drift Monitoring | 7 |
| Quality Checks automatizados | 1, 2, 3, 7 |
| Databricks SQL + Dashboards | 1, 4, 5 |
| Visualizações (Matplotlib/Seaborn) | 1, 2, 3, 4, 6 |

---

Portfólio desenvolvido com foco em projetos práticos que cobrem o ciclo completo de engenharia de dados: ingestão → transformação → qualidade → streaming → analytics → machine learning → automação → observabilidade.
