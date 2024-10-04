# Descrição do Projeto

Este repositório é dedicado a um estudo sobre as campanhas finalizadas na plataforma [Catarse](https://www.catarse.me/), uma das principais plataformas de financiamento coletivo no Brasil.

# Como Utilizar

Para utilizar este repositório, recomenda-se criar um ambiente virtual ou utilizar um gerenciador de dependências, como o Poetry. Abaixo, estão as instruções para ambas as abordagens:

### Usando Poetry

1. Instale o Poetry via pipx:

   ```bash
   pipx install poetry
   ```
   
2. Navegue até o diretório do projeto:

   ```bash
   cd caminho/para/o/projeto
   ```
   
3. Instale as dependências:

   ```bash
   poetry install
   ```

### Usando Ambiente Virtual

1. Crie um ambiente virtual:
   ```bash
   python -m venv ambiente_virtual
   ```
   
2. Ative o ambiente virtual:
   - Em Linux ou macOS:

     ```bash
     source ambiente_virtual/bin/activate
     ```

   - Em Windows:

     ```bash
     ambiente_virtual\Scripts\activate
     ```
   
3. Instale as dependências:

   ```bash
   pip install -r requirements.txt
   ```

### **Atenção**:

Antes de rodar os notebooks, utilize o repositório `get_data_catarse` para gerar o Dataset, depois disso, mova o arquivo `index_project_details.pkl` para a pasta [database](catarse\databases).

# Índice

- [Descrição do Projeto](#descrição-do-projeto)
- [Como Utilizar](#como-utilizar)
    - [Usando Poetry](#usando-poetry)
    - [Usando Ambiente Virtual](#usando-ambiente-virtual)
- [Objetivos](#objetivos)
- [Notebooks](#notebooks)
- [Dataset](#dataset)
    - [Tabela de Definição dos Dados](#tabela-de-definição-dos-dados)

# Objetivos

Este repositório tem como objetivo analisar o comportamento e as características das campanhas de financiamento coletivo no Brasil, além de desenvolver modelos estatísticos que possam prever os possíveis resultados dessas campanhas.

# Notebooks

Os notebooks deste projeto estão divididos em dois arquivos principais:

- *[Explore_catarse](#explore_catarse):* Contém uma análise exploratória inicial dos dados, incluindo a descrição visual dos mesmos através de gráficos e anotações explicativas.
  
- *[Models](#models):* Focado no desenvolvimento dos modelos preditivos e na avaliação de suas métricas. O desempenho dos modelos também pode ser consultado no relatório [REPORTS](./REPORTS.MD).

# Dataset

O dataset utilizado possui 29 colunas e 37.192 registros, abrangendo projetos finalizados entre 2011 e 2014.

## Tabela de Definição dos Dados

Abaixo está a descrição das colunas contidas no arquivo [project_details.pkl](./catarse/databases/project_details.pkl):

| #  | Coluna                 | Tipo de Dado           | Descrição                                                                                                          |
|----|------------------------|------------------------|--------------------------------------------------------------------------------------------------------------------|
| 0  | project_id             | int64                  | ID do projeto                                                                                                      |
| 1  | id                     | int64                  | ID geral do banco de dados                                                                                         |
| 2  | name                   | object                 | Nome do projeto                                                                                                    |
| 3  | budget                 | object                 | Justificativa para o uso do financiamento. Exemplo: "13% - Taxas do Catarse, 60% para produção do conteúdo..."      |
| 4  | goal                   | float64                | Meta de financiamento                                                                                              |
| 5  | about_html             | object                 | Informações sobre o projeto em formato HTML, incluindo texto, imagens, links, etc.                                 |
| 6  | category_id            | int64                  | ID da categoria do projeto                                                                                         |
| 7  | progress               | float64                | Progresso do valor a ser financiado                                                                                |
| 8  | pledged                | float64                | Valor efetivamente financiado                                                                                      |
| 9  | total_contributions    | int64                  | Total de contribuições (um mesmo usuário pode contribuir várias vezes)                                             |
| 10 | total_contributors     | int64                  | Total de contribuintes únicos                                                                                      |
| 11 | state                  | object                 | Estado do projeto (successful, failed, waiting_funds)                                                        |
| 12 | mode                   | object                 | Modalidade de financiamento (aon - tudo ou nada, flex - campanha flexível)                                      |
| 13 | state_order            | object                 | Estado da publicação (finished, published)                                                                     |
| 14 | expires_at             | datetime64[ns]         | Data de finalização da campanha                                                                                    |
| 15 | online_days            | float64                | Duração da campanha em dias                                                                                        |
| 16 | posts_count            | int64                  | Quantidade de postagens na página do projeto                                                                       |
| 17 | total_posts            | int64                  | Total de páginas de postagens do projeto                                                                           |
| 18 | contributed_by_friends | bool                   | Indica se o projeto recebeu contribuições de amigos                                                                |
| 19 | tag_list               | object                 | Lista de tags associadas ao projeto                                                                                |
| 20 | is_adult_content       | bool                   | Indica se o projeto é voltado para conteúdo adulto                                                                 |
| 21 | content_rating         | int64                  | Classificação indicativa (1 - livre, 18 - adulto)                                                                  |
| 22 | recommended            | bool                   | Indica se o projeto foi recomendado pelo Catarse                                                                   |
| 23 | video_embed_url        | bool                   | Indica se o projeto possui vídeo embutido na página                                                                |
| 24 | video_url              | bool                   | Indica se o projeto possui URL de vídeo                                                                            |
| 25 | thumb_image            | bool                   | Indica se o projeto possui uma imagem de capa                                                                      |
| 26 | city                   | object                 | Cidade dos donos do projeto                                                                                        |
| 27 | state_acronym          | object                 | UF da cidade dos donos do projeto                                                                                  |
| 28 | online_date_convert    | datetime64[ns]         | Data de lançamento do projeto                                                                                      |

---