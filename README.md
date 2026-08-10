# Desigualdade Educacional no ENEM (2020-2023)

Projeto acadêmico da disciplina "Fundamentos da Ciência de Dados" (2026.1).

Programa de Pós-Graduação em Informática (PPGI), Universidade Federal do Rio de Janeiro (UFRJ). 

**Artigo:** *Desigualdade Educacional no ENEM: quais fatores socioeconômicos mais impactam o desempenho do estudante?* - [📄 leia o PDF](docs/Artigo%20Projeto.pdf)

## Sumário
- [Resumo](#resumo)
- [Autoria e Orientação](#autoria-e-orientação)
- [Estrutura do Repositório](#estrutura-do-repositório)
- [Artefatos Relevantes](#artefatos-relevantes)
- [Como Citar Este Repositório](#como-citar-este-repositório)
- [Licença](#licença)
- [Uso de IA Generativa](#uso-de-ia-generativa)
 
## Resumo
 
Este projeto investiga como fatores socioeconômicos — renda familiar, tipo de escola (pública/privada), raça, escolaridade dos pais, entre outros — se relacionam com o desempenho dos candidatos no Exame Nacional do Ensino Médio (ENEM).

A análise utiliza os **microdados públicos do INEP referentes às edições de **2020 a 2023**, com granularidade individual (entre 3,4 e 5,8 milhões de registros por edição). São consideradas as 5 notas do exame (Ciências da Natureza, Ciências Humanas, Linguagens e Códigos, Matemática e Redação); na análise consolidada entre edições adota-se a média simples dessas 5 notas como métrica de desempenho.

O resultado central é que **a renda familiar é o fator nº 1 no ranking de associação com o desempenho, seguida por tipo de escola (pública x privada) e bens do domicílio; e essa hierarquia se manteve estável nas quatro edições** - sem sinal de redução da desigualdade no período.

> *Inicialmente o trabalho considerava o período 2020 a 2024. Porém a partir da edição de 2024, o INEP passou a publicar os microdados em duas tabelas separadas (perfil do participante e resultados das provas) sem identificador comum. Isso inviabiliza análises individuais que cruzem perfil socioeconômico e desempenho, motivo pelo qual a edição de 2024 foi excluída da análise principal.

Perguntas de pesquisa, metodologia, limitações e resultados completos estão melhor detalhados no [📄 Artigo](docs/Artigo%20Projeto.pdf).

## Autoria e Orientação
 
- **Autora:** Carla Moreno
- **Orientadores:** Sergio Serra e Jorge Zavaleta
 
## Estrutura do Repositório
 
```
.
├── data/
│   ├── raw/              # Microdados originais do ENEM em CSV e dicionários oficiais (2020–2023) - baixar antes de rodar os notebooks
│   ├── external/         # Malha das UFs do Brasil (GeoJSON) usada nos mapas - já incluída no repositório
│   └── processed/        # Arquivos Parquet limpos e prontos para análise - gerados automaticamente ao rodar os notebooks de tratamento
├── docs/                 # Artigo do trabalho em PDF
├── reports/
│   └── figures/          # Figuras PNG com gráficos e análises
├── slides/               # Slides de apresentação e atualizações do projeto
├── src/                  # Notebooks: tratamento_enem_YYYY, analise_enem_YYYY e analise_consolidada
└── .venv/                # Ambiente virtual Python
```

Devido a pasta `data/` conter arquivos muito pesados, as pastas `data/raw` e `data/processed` não foram incluídas neste repositório (ver `.gitignore`). Seguem mais detalhes:
- `data/raw`: baixe os microdados originais do ENEM diretamente no [site do INEP](https://www.gov.br/inep/pt-br/acesso-a-informacao/dados-abertos/microdados/enem).
- `data/external`: contém apenas o `brazil_uf.geojson`, um arquivo pequeno e estático, por isso foi incluído normalmente no repositório.
- `data/processed`: gerada automaticamente ao rodar os notebooks de tratamento (`tratamento_enem_YYYY`) em `src/`.

## Artefatos Relevantes
Seguem abaixo, os links diretamente para os aertefatos mais relevantes do projeto:
- 📄 Artigo: [Desigualdade Educacional no ENEM (PDF)](docs/Artigo%20Projeto.pdf)
- 📊 Slides:
  - [Apresentação Problema e Dataset](slides/12-05-26%20Apresentac%CC%A7a%CC%83o%20Problema%20e%20Dataset.pdf)
  - [Atualização de Status do Projeto](slides/14-05-26%20Atualização%20de%20Status%20do%20Projeto.pdf)
  - [Apresentação Final do Projeto](slides/16-07-26%20Apresentação%20Projeto.pdf)
- 💻 Notebooks: 
  - Tratamento: [2020](src/tratamento_enem_2020.ipynb), [2021](src/tratamento_enem_2021.ipynb), [2022](src/tratamento_enem_2022.ipynb), [2023](src/tratamento_enem_2023.ipynb)
  - Análise: [2020](src/analise_enem_2020.ipynb), [2021](src/analise_enem_2021.ipynb), [2022](src/analise_enem_2022.ipynb), [2023](src/analise_enem_2023.ipynb)
  - [Análise Consolidada](src/analise_consolidada_edicoes_enem.ipynb)
 
## Como Reproduzir
 
1. Clone este repositório
2. Baixe os microdados 2020–2023 no [portal do INEP](https://www.gov.br/inep/pt-br/acesso-a-informacao/dados-abertos/microdados/enem)
3. Extraia os microdados em `data/raw/`
4. Execute os notebooks de `src/` na seguinte ordem: tratamento de cada edição → análise de cada edição → análise consolidada.
 
## Como Citar Este Repositório
 
**ABNT**
 
> NASCIMENTO, Carla Moreno Barbosa. **Desigualdade Educacional no ENEM: quais fatores socioeconômicos mais impactam o desempenho do estudante?**. Rio de Janeiro: Programa de Pós-Graduação em Informática, Universidade Federal do Rio de Janeiro, 2026. Disponível em: https://github.com/carlamoreeno/Project-Data-Science.
 
**BibTeX**
 
```bibtex
@misc{nascimento2026enem,
  author       = {Nascimento, Carla Moreno Barbosa},
  title        = {Desigualdade Educacional no {ENEM}: quais fatores socioeconômicos mais impactam o desempenho do estudante?},
  year         = {2026},
  institution  = {Programa de Pós-Graduação em Informática,
                  Universidade Federal do Rio de Janeiro},
  howpublished = {\url{https://github.com/carlamoreeno/Project-Data-Science}}
}
```
 
## Licença
 
O código deste repositório é distribuído sob a [Licença MIT](LICENSE).

Os microdados do ENEM pertencem ao INEP/MEC, não são redistribuídos aqui e seguem os [termos de uso do órgão](https://www.gov.br/inep/pt-br/acesso-a-informacao/dados-abertos/microdados).
 
## Uso de IA Generativa
 
Foram utilizadas, como apoio operacional à execução do trabalho, as ferramentas Claude (Anthropic), Gemini (Google) e ChatGPT (OpenAI). Elas apoiaram a revisão de texto (artigo, README e notebooks), ajustes de slides, consulta sobre medidas estatísticas e sugestões de otimização de código, de forma pontual e operacional, sem substituir as decisões da autora ao longo do trabalho.
