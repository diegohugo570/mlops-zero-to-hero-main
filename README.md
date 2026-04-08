# 🚀 MLOps Zero to Hero — Pipeline Completo com MLflow + Kubeflow

Projeto prático focado em **MLOps (Machine Learning Operations)** que demonstra como construir, treinar, versionar e disponibilizar modelos de Machine Learning em produção.

O projeto cobre o ciclo completo de ML — desde ingestão de dados até deploy e monitoramento — com possibilidade de evolução para orquestração avançada com **Kubeflow**.

---

## 🧠 Conceitos Abordados

- 🔄 Pipeline end-to-end de Machine Learning  
- 📊 Preparação e validação de dados  
- 🧪 Treinamento e avaliação de modelos  
- 📦 Versionamento de modelos  
- 🚀 Deploy de modelos  
- 📈 Monitoramento e observabilidade  
- ⚙️ Orquestração de pipelines (Kubeflow - opcional)  

---

## 🚀 Tecnologias Utilizadas

### 🧪 Machine Learning
- Python 3.10+  
- Scikit-learn  
- Pandas  
- NumPy  

### ⚙️ MLOps & Infra
- MLflow (tracking e versionamento)  
- Docker  
- DVC *(opcional)*  
- Git  

### ☸️ Orquestração (Avançado)
- Kubeflow *(pipelines e automação em Kubernetes)*  

### 🌐 Serving
- FastAPI  
- Uvicorn  

---

## ⚙️ Como Rodar o Projeto Localmente

### 1️⃣ Clonar o Repositório

```bash
git clone <url-do-repositorio>
cd mlops-zero-to-hero-main
```
2️⃣ Criar Ambiente Virtual

python -m venv venv
source venv/bin/activate  # Linux/Mac

Windows:
```
venv\Scripts\activate
```

3️⃣ Instalar Dependências
```
pip install -r requirements.txt
```
4️⃣ Executar Pipeline de Treinamento
```
python src/train.py
```
Esse processo inclui:

- Carregamento de dados
- Feature engineering
- Treinamento do modelo
- Avaliação de métricas
- Salvamento de artefatos

5️⃣ Executar MLflow
```
mlflow ui
```
Acesse:
```
👉 http://localhost:5000
```
6️⃣ Rodar API de Inferência
```
uvicorn app.main:app --reload
```
Acesse:
```
👉 http://localhost:8000
````

☸️ Execução com Kubeflow (Opcional / Avançado)

Caso queira evoluir para um ambiente de produção com pipelines orquestrados:

1️⃣ Instalar Kubeflow

Via Kubernetes (minikube, kind ou cloud):
```
kubectl apply -k "github.com/kubeflow/pipelines/manifests/kustomize/cluster-scoped-resources?ref=stable"
```
2️⃣ Criar Pipeline

O pipeline pode incluir etapas como:

ingestão de dados
preprocessing
treino
avaliação
deploy

3️⃣ Executar Pipeline

Via UI do Kubeflow:
```
👉 http://localhost:8080
```

---

📡 Endpoints Principais
🔹 Predição
POST /predict

Body:

{
  "feature1": 10,
  "feature2": 5
}

Resposta:

{
  "prediction": 1
}
🔹 Health Check
GET /health

---

🧠 Arquitetura do Projeto
```
.
├── src/                # Pipeline de ML
│   ├── data/
│   ├── features/
│   ├── models/
│   ├── train.py
│   └── evaluate.py
├── app/                # API de inferência
│   ├── main.py
│   ├── routes/
│   └── schemas/
├── models/             # Modelos treinados
├── notebooks/          # Exploração
├── Dockerfile
├── requirements.txt
└── README.md
```

---

📦 Funcionalidades Implementadas
📊 Pipeline de treinamento
🧪 Avaliação de modelos
📈 Tracking com MLflow
🚀 API de inferência
📦 Versionamento de modelos
☸️ Estrutura pronta para Kubeflow
🐳 Docker

---

Build
```
docker build -t mlops-app .
Run
docker run -p 8000:8000 mlops-app
```
---

🚀 Deploy

- Cloud (AWS / GCP / Azure)
- Deploy via Docker
- Kubernetes (recomendado com Kubeflow)

🔐 Boas Práticas de MLOps

- Versionamento de dados e modelos
- Reprodutibilidade
- Separação treino vs inferência
- Monitoramento contínuo
- Automação de pipelines

📈 Possíveis Evoluções

- 🔄 CI/CD com GitHub Actions
- ☸️ Kubeflow Pipelines completo
- 📊 Monitoramento de drift
- 🧠 Feature Store
- ⚡ Cache de inferência
- 🔍 Observabilidade (Prometheus + Grafana)

---

🎯 Objetivo do Projeto

- Aprender MLOps na prática
- Criar pipelines escaláveis
- Preparar modelos para produção
- Evoluir para arquitetura enterprise com Kubernetes

---

📚 Referências
- https://mlflow.org/docs
- https://www.kubeflow.org
- https://scikit-learn.org
- https://fastapi.tiangolo.com
---
