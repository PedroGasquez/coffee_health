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
docs/        enunciado e dicionário de dados (Read_Dataset_Coffee_Health.md)
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
