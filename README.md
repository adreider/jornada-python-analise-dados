# 📊 Jornada Python: Análise de Dados (Previsão de Churn)

> **Case de Negócio:** Fui contratado por uma empresa de grande porte com uma base de mais de 800.000 clientes. Recentemente, a diretoria percebeu que a maioria da base total de clientes tornou-se inativa (cancelou o serviço). O objetivo deste projeto é analisar essa base histórica para identificar os principais motivos de cancelamento (Churn) e propor ações eficientes para reduzir esse número ao mínimo.

---

## 🛠️ Tecnologias e Bibliotecas Utilizadas
* **Python** (Lógica de programação e automação analítica)
* **Pandas** (Tratamento, limpeza e manipulação de grandes volumes de dados)
* **Plotly Express** (Criação de gráficos interativos e análise visual/diagnóstica)
* **OpenPyXL / NBFormat** (Suporte para leitura de arquivos e renderização de notebooks)

---

## 🚀 Estrutura do Passo a Passo do Projeto

### 📥 Passo 1: Importação da Base de Dados
Utilização da biblioteca `pandas` para ler e carregar o arquivo `cancelamentos.csv` contendo o histórico dos 800 mil clientes.

### 🔍 Passo 2: Visualização e Exploração dos Dados
Mapeamento das colunas disponíveis através do método `.info()` para entender os tipos de variáveis e identificar inconsistências estruturais na base de dados.

### 🔧 Passo 3: Tratamento de Dados (Data Cleaning)
Identificação de registros nulos e dados vazios. Realizei a limpeza removendo dados ausentes com o comando `dropna()` e eliminei colunas que não geravam valor preditivo direto (como IDs de clientes), garantindo a integridade dos cálculos.

### 📈 Passo 4: Análise Inicial (Métrica de Churn)
Gerei a volumetria absoluta e percentual de clientes ativos vs. inativos. 
> 💡 **Nota Técnica de Analytics:** Apliquei a formatação de exibição das porcentagens mantendo o dado original como numérico (Float) em vez de convertê-lo precocemente em String (texto), preservando a base intacta para futuros cálculos matemáticos ou modelos de Machine Learning.

### 🔬 Passo 5: Análise Detalhada e Diagnóstica
Para otimizar o processo, criei uma estrutura de repetição `for` para automatizar a geração de gráficos de histograma com a biblioteca **Plotly Express**, cruzando cada variável da base com o status de cancelamento (`color="cancelou"`), gerando múltiplos gráficos interativos com poucas linhas de código.

```python
# Automação da análise visual de todas as colunas
for coluna in tabela.columns:
    grafico = px.histogram(tabela, x=coluna, color="cancelou", text_auto=True)
    grafico.show()
```
<img width="1920" height="1022" alt="Captura de Tela (34)" src="https://github.com/user-attachments/assets/4af86f73-7963-4b5d-a50b-14dca3e92a69" />

