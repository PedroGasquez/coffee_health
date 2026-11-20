# Estudo de Caso — Consumo de Café, Sono e Saúde

## Contextualização

Uma equipe de análise de dados deseja investigar padrões de consumo de café e suas possíveis associações com sono, estresse e indicadores de saúde. Para isso, será utilizado o arquivo `synthetic_coffee_health_10000.csv`, que contém registros **sintéticos** de pessoas, com informações demográficas, comportamentais e relacionadas à saúde.

O objetivo da atividade é aplicar os conceitos de **análise exploratória de dados (EDA)** utilizando Python no Jupyter Notebook. Também será realizada uma atividade introdutória de classificação com Machine Learning. Os resultados devem ser interpretados como **associações presentes em dados sintéticos**, e não como comprovação de causa e efeito ou evidência clínica.

## Dicionário de dados

| Variável | Descrição |
|---|---|
| `ID` | Identificador de cada registro. Não é uma medida de saúde. |
| `Age` | Idade da pessoa, em anos. |
| `Gender` | Gênero informado: `Male` (masculino), `Female` (feminino) ou `Other` (outro). |
| `Country` | País associado ao registro. |
| `Coffee_Intake` | Quantidade registrada de consumo de café (valor numérico). A unidade não é explicitada no próprio arquivo CSV. |
| `Caffeine_mg` | Quantidade de cafeína, em miligramas (mg). |
| `Sleep_Hours` | Quantidade de horas de sono. |
| `Sleep_Quality` | Qualidade do sono: `Poor` (ruim), `Fair` (razoável), `Good` (boa) ou `Excellent` (excelente). |
| `BMI` | Índice de Massa Corporal (IMC). |
| `Heart_Rate` | Frequência cardíaca registrada, normalmente expressa em batimentos por minuto. |
| `Stress_Level` | Nível de estresse: `Low` (baixo), `Medium` (médio) ou `High` (alto). |
| `Physical_Activity_Hours` | Quantidade de horas de atividade física registradas. O período de referência não está explicitado no CSV. |
| `Health_Issues` | Grau de problemas de saúde registrado: `Mild` (leve), `Moderate` (moderado) ou `Severe` (grave). Há valores ausentes; **não presumir que ausência significa ausência de problemas de saúde**. |
| `Occupation` | Categoria de ocupação: `Other` (outra), `Service` (serviços), `Office` (escritório), `Student` (estudante) ou `Healthcare` (saúde). |
| `Smoking` | Indicador binário de tabagismo, com valores `0` e `1` (convencionalmente, não e sim). |
| `Alcohol_Consumption` | Indicador binário de consumo de álcool, com valores `0` e `1` (convencionalmente, não e sim). |

> **Observação:** este é um conjunto de dados sintético. As definições dos indicadores binários e das unidades não documentadas devem ser confirmadas na descrição da fonte original, quando disponível.

## Questões — Análise de Dados e Big Data

1. **Conhecendo o dataset:** quantos registros e quantas colunas existem? Quais são os tipos de dados das variáveis? Apresente as cinco primeiras linhas e um resumo estatístico das colunas numéricas.

2. **Qualidade dos dados:** o dataset possui valores ausentes ou registros duplicados? Identifique as colunas com valores ausentes, apresente a quantidade em cada uma e explique como esses valores poderiam ser tratados sem modificar o arquivo original.

3. **Perfil das pessoas:** qual é a distribuição dos registros por gênero (`Gender`)? Qual é a média de idade (`Age`) em cada gênero? Apresente os resultados em uma tabela ou gráfico.

4. **Consumo de café:** qual é o valor médio, mínimo e máximo de `Coffee_Intake`? Quais são os cinco países (`Country`) com maior média de consumo de café no dataset?

5. **Café e cafeína:** existe relação entre `Coffee_Intake` e `Caffeine_mg`? Calcule a correlação e represente as variáveis em um gráfico de dispersão. Explique o resultado.

6. **Consumo de café e sono:** qual é a média de `Coffee_Intake` para cada categoria de `Sleep_Quality`? Os registros classificados com sono `Poor` apresentam consumo médio maior ou menor do que aqueles com sono `Excellent`?

7. **Sono e estresse:** qual é a média de horas de sono (`Sleep_Hours`) em cada nível de estresse (`Stress_Level`)? Apresente um gráfico comparativo e descreva o padrão encontrado.

8. **Classificação com Machine Learning:** utilizando uma **Árvore de Decisão** (`DecisionTreeClassifier`), crie um modelo simples para prever a categoria `Sleep_Quality` a partir de `Coffee_Intake`, `Caffeine_mg`, `Age`, `BMI`, `Heart_Rate` e `Physical_Activity_Hours`. Separe os dados em treinamento e teste e apresente a **acurácia** do modelo. O identificador `ID` não deve ser utilizado como atributo preditor.

9. **Análise conjunta de consumo, sono e estresse:** agrupe os registros por `Stress_Level` e `Sleep_Quality` e calcule, para cada combinação, a quantidade de pessoas, a média de `Coffee_Intake` e a média de `Sleep_Hours`. Quais combinações apresentam o maior consumo médio de café? Interprete os resultados considerando também a quantidade de registros em cada grupo.

10. **Investigando possíveis associações com problemas de saúde:** considerando **somente os registros em que `Health_Issues` está preenchido**, compare, para cada categoria (`Mild`, `Moderate` e `Severe`), a quantidade de registros, as médias de `Coffee_Intake`, `Caffeine_mg`, `BMI` e `Heart_Rate`, e a distribuição percentual de `Smoking`. Quais diferenças são observadas? Elas permitem afirmar que o consumo de café causa problemas de saúde? Justifique.
