# Coffee & Health

Projeto semestral (A3) da UC **Análise de Dados e Big Data**, 2026/2.
Análise exploratória de um dataset **sintético** sobre consumo de café, sono, estresse e saúde.

Os resultados indicam associações nos dados sintéticos, não relações de causa e efeito nem evidência clínica.

## Integrantes

| Nome | RA |
|---|---|
| | |
| | |

## Estrutura

```
data/        dataset original (não deve ser alterado)
docs/        enunciado e dicionário de dados (Read_Dataset_Coffee_Health.md) e trilha do projeto (trilha_projeto.csv)
notebooks/   notebook com a análise
```

## Requisitos

- Python 3.10 ou superior
- Jupyter (VSCode, Jupyter Lab ou Google Colab)

## Como rodar

1. Crie um ambiente virtual e instale as dependências:

   ```
   python -m venv .venv
   .venv\Scripts\activate
   pip install -r requirements.txt
   ```

2. Copie `.env.example` para `.env`. Os valores fixos do projeto (caminho do CSV, semente aleatória, proporção de teste) ficam lá.

3. Abra `notebooks/analise_coffee_health.ipynb` e execute **Restart & Run All**.

No Google Colab, envie o CSV para a sessão e ajuste `DATA_PATH` na célula de configuração.

## Entregas

- 28/11 às 23:59, pelo Classroom: notebook (`.ipynb`) e apresentação em PowerPoint. Só um integrante envia.
- 30/11: apresentação, por ordem de chegada.
- Documento de análise impresso.

## Trilha do projeto

A versão editável fica em [docs/trilha_projeto.csv](docs/trilha_projeto.csv); atualize o status lá e nesta tabela.

Divisão sugerida: **A** = qualidade/ETL · **B** = Q3 a Q7 · **C** = Q9 + hipóteses · **D** = Q10, LGPD e revisão.

| Etapa | Atividade | Prazo | Responsável | Status | Detalhes |
|---|---|---|---|---|---|
| 0 · Organização | Formar o grupo e anotar nomes e RAs | 21/11 | Grupo | Concluído | De 2 a 4 integrantes. Nome e RA vão na capa do PPT. |
| 0 · Organização | Dividir as tarefas entre os integrantes | 21/11 | Grupo | Em andamento | Vira slide. |
| 0 · Organização | Escolher o ambiente (Colab ou VSCode) | 21/11 | Grupo | Concluído | Se for Colab, baixar o `.ipynb` no fim. |
| 1 · Estrutura do notebook | Criar as seções em Markdown | 21/11 | A | A fazer | Introdução → bibliotecas → carga do CSV → Q1 → Q2/ETL → EDA → hipóteses → conclusões. |
| 1 · Estrutura do notebook | Importar as bibliotecas e carregar o CSV | 21/11 | A | A fazer | pandas e matplotlib/seaborn; arquivo `synthetic_coffee_health_10000.csv`. |
| 2 · Conhecer o dataset (Q1) | Registros, colunas, tipos, 5 primeiras linhas e resumo estatístico | 21/11 | A | A fazer | `shape`, `dtypes`, `head()`, `describe()`. |
| 2 · Conhecer o dataset (Q1) | Classificar cada coluna pelo tipo de dado | 21/11 | A | A fazer | Numéricas contínuas/discretas, categóricas, ordinais (Sleep_Quality, Stress_Level, Health_Issues) e binárias (Smoking, Alcohol). Conteúdo da aula de 21/09. |
| 3 · Qualidade e ETL (Q2) | Contar valores ausentes e duplicados | 21/11 | A | A fazer | `isnull().sum()` e `duplicated()`. |
| 3 · Qualidade e ETL (Q2) | Tratar os vazios de Health_Issues | 21/11 | A | A fazer | Vazio não significa "sem problema": usar "Não informado" ou filtrar. |
| 3 · Qualidade e ETL (Q2) | Trabalhar sempre numa cópia dos dados | 21/11 | A | A fazer | `df.copy()`; nunca alterar o CSV original. |
| 3 · Qualidade e ETL (Q2) | Desenhar o fluxo ETL | 21/11 | A | A fazer | Extração (CSV) → Transformação (duplicados, ausentes, categorias, ordem dos ordinais, anonimização) → Carga (DataFrame limpo). |
| 4 · EDA | Q3 – Perfil por gênero | 24/11 | B | A fazer | `value_counts()` + média de Age por Gender + gráfico de barras. |
| 4 · EDA | Q4 – Consumo de café | 24/11 | B | A fazer | Média, mínimo e máximo de Coffee_Intake + top 5 países por média. |
| 4 · EDA | Q5 – Café × cafeína | 24/11 | B | A fazer | `corr()` + gráfico de dispersão; explicar o que o valor significa. |
| 4 · EDA | Q6 – Café × qualidade do sono | 24/11 | B | A fazer | `groupby('Sleep_Quality')`; comparar Poor e Excellent. |
| 4 · EDA | Q7 – Sono × estresse | 24/11 | B | A fazer | Média de Sleep_Hours por Stress_Level + gráfico comparativo. |
| 4 · EDA | Q9 – Análise conjunta estresse × sono | 24/11 | C | A fazer | `groupby([Stress_Level, Sleep_Quality])` com contagem e médias; comentar os grupos pequenos. |
| 4 · EDA | Q10 – Associações com problemas de saúde | 24/11 | D | A fazer | Só registros com Health_Issues preenchido; médias + % de fumantes; correlação não é causalidade (dados sintéticos). |
| 4 · EDA | Comparar média e mediana onde fizer sentido | 24/11 | B | A fazer | Mostra o efeito dos outliers (aula de 21/09). |
| 6 · LGPD e ética | Identificar os dados pessoais sensíveis | 25/11 | D | A fazer | Dados de saúde: Health_Issues, Smoking, Alcohol_Consumption, BMI, Heart_Rate. |
| 6 · LGPD e ética | Descrever os riscos | 25/11 | D | A fazer | Reidentificação cruzando Age + Gender + Country + Occupation; discriminação (ex.: seguradoras). |
| 6 · LGPD e ética | Definir as medidas de proteção | 25/11 | D | A fazer | Pseudonimizar ou remover o ID, faixas etárias, minimização, finalidade, consentimento, controle de acesso. Lembrar que o dataset é sintético. |
| 7 · Hipóteses | Hipótese 1 | 25/11 | C | A fazer | Enunciado → análise → resultado → conclusão. Ideia: fumantes têm frequência cardíaca maior? |
| 7 · Hipóteses | Hipótese 2 | 25/11 | C | A fazer | Enunciado → análise → resultado → conclusão. Ideia: quem faz mais atividade física dorme mais? |
| 7 · Hipóteses | Hipótese 3 | 25/11 | C | A fazer | Enunciado → análise → resultado → conclusão. Ideia: alguma ocupação consome mais café? |
| 7 · Hipóteses | Hipótese 4 | 25/11 | C | A fazer | Enunciado → análise → resultado → conclusão. Ideia: quem consome álcool tem pior qualidade de sono? |
| 8 · Documento impresso | Escrever o documento de análise | 27/11 | D | A fazer | Descrição do dataset, procedimentos (ETL + EDA), respostas às questões (sem a Q8), H1 a H4 com validação, LGPD e conclusão. |
| 8 · Documento impresso | Revisar o português e imprimir | 27/11 | D | A fazer | Norma culta é critério de avaliação. |
| 9 · PowerPoint | Montar a apresentação | 27/11 | Grupo | A fazer | Capa (nome + RA) → introdução → divisão de tarefas → ferramentas → etapas da EDA/ETL → respostas → hipóteses → LGPD → conclusão. |
| Entrega | Revisão final e envio no Classroom | 28/11 | Grupo | A fazer | Até 23:59. Só um integrante envia: `.ipynb` (ou `.py`) + PPT. |
| 10 · Ensaio | Rodar o notebook inteiro sem erro | 29/11 | Grupo | A fazer | Restart & Run All. |
| 10 · Ensaio | Cada integrante explica e altera o código | 29/11 | Grupo | A fazer | Treinar mudanças pequenas: trocar uma coluna, adicionar um gráfico. O professor pode pedir na hora. |
| Apresentação | Apresentar o projeto | 30/11 | Grupo | A fazer | Ordem de chegada; usar o mesmo PPT enviado no dia 28. |
