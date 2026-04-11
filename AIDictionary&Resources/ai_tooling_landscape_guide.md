# AI / Data / MLOps Tooling Landscape

## Core Programming & Data Tools

| Tool / Framework | Open Source? | Objective | Example Outcomes |
|------------------|-------------|----------|-----------------|
| Python | Yes | General-purpose programming | Build APIs, ML models, automation scripts |
| Pandas | Yes | Data manipulation & analysis | Clean datasets, generate reports |
| NumPy | Yes | Numerical computations | Matrix operations, ML preprocessing |
| MySQL | Yes | Relational database | Store app data, analytics backend |
| Jupyter Notebook | Yes | Interactive coding & experiments | ML experiments, tutorials |
| GitHub | Partially | Version control & collaboration | Portfolio, CI/CD workflows |
| Matplotlib | Yes | Data visualization | Charts, plots |
| Seaborn | Yes | Advanced visualization | Heatmaps, distribution plots |
| Plotly | Yes (core) | Interactive dashboards | Web dashboards |
| Scikit-learn | Yes | Machine learning | Classification/regression models |

---

## ML / Deep Learning

| Tool / Framework | Open Source? | Objective | Example Outcomes |
|------------------|-------------|----------|-----------------|
| XGBoost | Yes | Gradient boosting | High-performance prediction models |
| LightGBM | Yes | Fast gradient boosting | Large-scale ML models |
| TensorFlow | Yes | Deep learning | Image/NLP models |
| PyTorch | Yes | Deep learning research & production | LLM training, CV models |
| Hugging Face | Partially | Pretrained models & NLP | Chatbots, transformers |

---

## LLM / Agent Frameworks

| Tool / Framework | Open Source? | Objective | Example Outcomes |
|------------------|-------------|----------|-----------------|
| LlamaIndex | Yes | RAG data indexing | Q&A over documents |
| LangGraph | Yes | Stateful AI workflows | Multi-step AI agents |
| CrewAI | Yes | Multi-agent collaboration | Autonomous workflows |
| AutoGen | Yes | Conversational agents | AI teams solving tasks |
| LangChain | Yes | LLM pipelines | Chatbots, RAG apps |

---

## Cloud / DevOps / Infrastructure

| Tool / Framework | Open Source? | Objective | Example Outcomes |
|------------------|-------------|----------|-----------------|
| AWS | No | Cloud infrastructure | Deploy scalable apps |
| Docker | Yes | Containerization | Microservices deployment |
| OpenAI | No | LLM APIs | GPT-based apps |
| Streamlit | Yes | Data apps UI | ML dashboards |
| Apache Airflow | Yes | Workflow orchestration | ETL pipelines |
| MLflow | Yes | ML lifecycle management | Model versioning |

---

## AWS Data & ML Ecosystem

| Tool / Framework | Open Source? | Objective | Example Outcomes |
|------------------|-------------|----------|-----------------|
| Amazon S3 | No | Object storage | Data lakes |
| AWS Glue | No | Data integration | Data pipelines |
| Amazon Redshift | No | Data warehouse | BI dashboards |
| Amazon SageMaker | No | ML platform | Train/deploy models |
| AWS Lambda | No | Serverless compute | API backends |
| AWS Bedrock | No | Foundation models | GenAI apps |

---

## Backend / DevOps / APIs

| Tool / Framework | Open Source? | Objective | Example Outcomes |
|------------------|-------------|----------|-----------------|
| FastAPI | Yes | API development | High-speed APIs |
| GitHub Actions | Partially | Automation pipelines | Auto testing & deploy |
| Terraform | Yes | Infrastructure as Code | Cloud automation |

---

## Vector Databases / AI Infra

| Tool / Framework | Open Source? | Objective | Example Outcomes |
|------------------|-------------|----------|-----------------|
| Chroma | Yes | Embedding storage | RAG systems |
| Pinecone | No | Managed vector DB | Semantic search |
| Weaviate | Yes | AI-native database | Hybrid search |
| Weights & Biases | Partially | Experiment tracking | Model dashboards |

---

## AI Providers / APIs

| Tool / Framework | Open Source? | Objective | Example Outcomes |
|------------------|-------------|----------|-----------------|
| Anthropic | No | LLM APIs (Claude) | AI assistants |
| Google APIs | No | AI + services | Vision, speech apps |

---

## Suggested Stack Architecture (AI-First)

- **Frontend/UI** → Streamlit
- **Backend APIs** → FastAPI
- **Agents** → LangChain + CrewAI + AutoGen
- **RAG** → LlamaIndex + Chroma/Pinecone
- **ML Models** → PyTorch + Hugging Face
- **Infrastructure** → Docker + AWS + Terraform
- **Observability** → MLflow + Weights & Biases

---
