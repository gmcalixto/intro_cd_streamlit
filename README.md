# intro_cd_streamlit

Projeto didático de **Ciência de Dados com Streamlit** usando **Pandas** para carregar um CSV, aplicar filtros e gerar visualizações **nativas do Streamlit**. Inclui também exemplos de **correlação** e **K-means** para explorar padrões em variáveis numéricas.

Repositório: https://github.com/gmcalixto/intro_cd_streamlit

---

## ✅ Pré-requisitos

- **Python 3.10+** (recomendado 3.11/3.12)
- `pip`
- (Recomendado) ambiente virtual (`venv`)

---

## 📦 Instalação

### 1) Clonar o repositório
```bash
git clone https://github.com/gmcalixto/intro_cd_streamlit.git
cd intro_cd_streamlit
```

### 2) Criar e ativar ambiente virtual

**Windows (PowerShell):**
```bash
python -m venv env
.\env\Scripts\Activate.ps1
```

**Linux/Mac:**
```bash
python -m venv env
source env/bin/activate
```

### 3) Instalar dependências

Se existir `requirements.txt`:
```bash
pip install -r requirements.txt
```

Se ainda não existir, um conjunto mínimo para este exemplo é:
```bash
pip install streamlit pandas scikit-learn matplotlib
```

> `matplotlib` é usado apenas na visualização opcional do K-means com centróides via `st.pyplot()`.

---

## 📄 Dados (CSV)

O app lê um arquivo CSV (exemplo utilizado nas aulas):

- `StudentPerformanceFactors.csv`

Coloque o arquivo **na raiz do projeto** (mesma pasta do `app.py`) ou ajuste o caminho no código:
```python
ARQUIVO = "StudentPerformanceFactors.csv"
```

---

## ▶️ Como executar

Na pasta do projeto, execute:
```bash
streamlit run app.py
```

O Streamlit vai exibir no terminal um endereço como:
- http://localhost:8501

---

## 🧭 O que o app faz

### 1) Carregamento e visão geral
- Lê o CSV com Pandas (`pd.read_csv`)
- Exibe amostra (`head`) e estatísticas descritivas

### 2) Filtros simples (sidebar)
- 1 filtro categórico (seleção de coluna e valor)
- 1 filtro numérico (slider de intervalo)

### 3) Visualizações nativas do Streamlit
- `st.bar_chart()`  
  - média de métrica numérica por categoria  
  - ranking de correlações com variável alvo
- `st.line_chart()`  
  - tendência/variação de uma coluna numérica (série ordenada)
- `st.scatter_chart()`  
  - dispersão X × Y  
  - dispersão X × Y colorida por cluster (K-means)

### 4) Correlação
- Matriz de correlação em tabela (`df.corr()`)
- Ranking das correlações absolutas com uma variável alvo (bar chart)

### 5) K-means (clusterização)
- Seleção de duas variáveis numéricas (X e Y)
- Escolha de `k` (número de clusters)
- Padronização com `StandardScaler` (recomendado)
- Visualização:
  - `st.scatter_chart` (nativo) colorindo por cluster
  - (Opcional) Matplotlib para destacar centróides

---

## 🗂️ Estrutura sugerida do projeto

```text
intro_cd_streamlit/
├─ app.py
├─ StudentPerformanceFactors.csv
├─ requirements.txt
└─ README.md
```

