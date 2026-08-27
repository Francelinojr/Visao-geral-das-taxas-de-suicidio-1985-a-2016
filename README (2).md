# Visão geral das taxas de suicídio (1985–2016)

[![Python](https://img.shields.io/badge/Python-3.10%2B-3776AB?logo=python&logoColor=white)](https://www.python.org/)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?logo=jupyter&logoColor=white)](https://jupyter.org/)
[![Status](https://img.shields.io/badge/status-estudo%20explorat%C3%B3rio-2E7D32)](#status-do-projeto)

## Sobre o projeto

Este projeto apresenta uma análise exploratória de dados sobre **taxas de suicídio por país, ano, sexo, faixa etária e geração**, utilizando registros de 1985 a 2016. O objetivo é praticar um fluxo completo de análise de dados: entendimento do problema, inspeção da qualidade dos dados, agregação de indicadores, visualização e comunicação de resultados.

O trabalho foi desenvolvido originalmente como um projeto acadêmico de introdução à Ciência de Dados por **Ana Paula Cardoso de Castro Kendall, Francelino Teotonio Júnior e Vivianny Khatly Medeiros Pereira**. Esta versão reorganiza o material para facilitar a leitura, a reprodução e a avaliação técnica por recrutadores.

> **Nota de responsabilidade:** este é um estudo observacional e exploratório de saúde pública. Os resultados não estabelecem causalidade, não substituem estudos epidemiológicos e não devem ser usados para avaliar ou diagnosticar indivíduos.

## Principais perguntas

| Pergunta | Abordagem |
| --- | --- |
| Como as taxas variam entre os sexos ao longo do tempo? | Taxa agregada por ano e sexo, calculada como suicídios / população × 100.000. |
| Quais faixas etárias apresentam maiores taxas? | Agregação ponderada por população, preservando a diferença entre contagem e taxa. |
| Como as taxas se comportam entre gerações? | Comparação temporal por geração e ano, quando há dados suficientes. |
| Como lidar com valores ausentes e distribuições assimétricas? | Auditoria de nulos, conversão de tipos e transformação logarítmica apenas quando apropriada. |

## Resultados exploratórios

A análise original sugere diferenças relevantes entre grupos de sexo e idade. A interpretação deve ser feita com **taxas**, e não apenas com números absolutos, porque os grupos possuem populações diferentes. O notebook revisado recalcula os indicadores de forma ponderada e deixa explícitas as limitações do dataset.

Entre as limitações estão a cobertura desigual entre países e anos, a natureza agregada dos registros, a ausência de uma estratégia causal e a dependência de uma fonte secundária. Assim, as visualizações devem ser entendidas como evidências descritivas para gerar hipóteses, não como conclusões definitivas sobre os determinantes do suicídio.

## Estrutura do repositório

```text
.
├── data/
│   ├── master.csv                 # Dataset utilizado na análise
│   └── README.md                 # Documentação dos dados
├── notebooks/
│   └── analise_exploratoria.ipynb # Notebook principal, revisado e reproduzível
├── reports/
│   └── figures/                  # Gráficos exportados pelo notebook
├── archive/                      # Notebooks originais preservados para referência
├── .gitignore
├── requirements.txt
└── README.md
```

## Como executar

Clone o repositório e crie um ambiente virtual:

```bash
git clone https://github.com/SEU_USUARIO/Visao-geral-das-taxas-de-suicidio-1985-a-2016.git
cd Visao-geral-das-taxas-de-suicidio-1985-a-2016
python -m venv .venv
# Linux/macOS
source .venv/bin/activate
# Windows PowerShell: .venv\Scripts\Activate.ps1
pip install -r requirements.txt
```

O arquivo `master.csv` já está incluído em `data/`. Consulte [`data/README.md`](data/README.md) para conhecer a fonte e as observações sobre os dados. Em seguida, abra o notebook:

```bash
jupyter notebook notebooks/analise_exploratoria.ipynb
```

Os gráficos gerados são salvos automaticamente em `reports/figures/`.

## Competências demonstradas

**Python e pandas** para leitura, limpeza, validação e agregação de dados; **visualização de dados** com Matplotlib e Seaborn; **estatística descritiva** para resumir distribuições; **engenharia de análise** com taxas ponderadas pela população; **comunicação analítica** por meio de perguntas, limitações e conclusões reproduzíveis; e **organização de projeto** com estrutura clara, dependências declaradas e documentação de execução.

## Status do projeto

O projeto está em fase de **estudo exploratório**. Próximas melhorias possíveis incluem comparar a fonte secundária com bases oficiais, documentar a cobertura por país, adicionar testes automatizados para o cálculo das taxas e separar análises descritivas de modelos estatísticos.

## Fonte dos dados

O dataset utilizado é o **Suicide Rates Overview 1985 to 2016**, disponibilizado por Russell Yates no Kaggle [1]. A cópia usada pelo notebook está em [`data/master.csv`](data/master.csv), acompanhada de suas observações em [`data/README.md`](data/README.md).

## Autores

- Ana Paula Cardoso de Castro Kendall
- Francelino Teotonio Júnior
- Vivianny Khatly Medeiros Pereira

## Referências

[1]: https://www.kaggle.com/datasets/russellyates88/suicide-rates-overview-1985-to-2016 "Suicide Rates Overview 1985 to 2016 — Kaggle"
