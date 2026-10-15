# Análise exploratória do Cadastro Único (amostra de 2018)

Trabalho de análise de dados em Python sobre uma amostra (10%) de microdados do Cadastro Único (MDS), com foco em renda, mercado de trabalho, escolaridade e pessoas com deficiência. Inclui tratamento de dados, análises descritivas, visualizações e uma proposta de enriquecimento com base externa municipal.

- **Disciplina:** Tecnologias para Data Science
- **Dupla:** Tiago Maia e Caio Gabriel
- **Notebook principal:** `analiseCadUnico.ipynb` (o relatório com os principais resultados está no início)

## Tecnologias utilizadas

| Tecnologia | Uso no projeto |
|---|---|
| Python 3 | Linguagem do projeto |
| pandas | Manipulação, limpeza e análise dos dados |
| NumPy | Classificações condicionais e operações numéricas |
| Matplotlib | Criação e configuração dos gráficos |
| Seaborn | Gráficos estatísticos (barras, boxplot) |
| PySpark | Leitura do arquivo CSV, que é grande (a análise é feita em pandas) |
| Jupyter / Google Colab | Ambiente de desenvolvimento |
| Git e GitHub | Versionamento e entrega |

## Dados

- **Fonte:** Cadastro Único para Programas Sociais do Governo Federal (MDS), dados administrativos com uma linha por pessoa.
- **Referência:** ano de 2018.
- **Base externa:** Produto Interno Bruto (PIB) Municipal de 2018, conectado à base via código IBGE do município
- Os dados não estão no repositório pelo tamanho e por serem dados pessoais. O notebook lê o arquivo `amostras.csv`.

## O que o projeto faz

- Análise demográfica por sexo, cor/raça e faixa etária.
- Classificação do trabalho em formal e informal e cálculo da renda do trabalho.
- Análise da renda e da informalidade por nível de escolaridade.
- Cálculo da renda familiar per capita e análise de pessoas com deficiência por faixa de renda.
- Análise da ocupação de mães responsáveis familiares, com e sem crianças pequenas.
- Enriquecimento dos dados com uma base pública municipal.
- Visualizações dos principais resultados.

## Como executar

1. Clone o repositório ou baixe os arquivos.
2. Instale as dependências:
   ```bash
   pip install pandas numpy matplotlib seaborn pyspark
   ```
3. Ajuste o caminho do arquivo 'amostras.csv' na célula de carregamento de dados. No Colab, monte o Drive antes de ler o arquivo.
4. Execute as células na ordem, de cima para baixo.

## Principais decisões

- **Valores ausentes:** nulos nas colunas de trabalho e renda indicam, na maior parte, que a pergunta não se aplica (em geral crianças). Eles ficam fora dessas análises e não são convertidos em zero.
- **Classificação formal e informal:** segue o critério definido pela professora, com base na remuneração de emprego e na renda bruta de 12 meses.
- **Limpeza:** idades improváveis e datas inválidas foram tratadas como nulas.
- **Faixas de renda e etárias:** definidas conforme o dicionário de dados e o enunciado do trabalho.

## Limitações

- A análise é exploratória e descritiva, então os resultados indicam associações, não causalidade.
- Algumas variáveis, como a renda dos informais e a data de referência (dia e mês), são estimadas.
- O CadÚnico cobre famílias de baixa renda, e os resultados não refletem a realidade de toda a população.

## Estrutura

```
.
├── analiseCadUnico.ipynb
├── README.md
```
