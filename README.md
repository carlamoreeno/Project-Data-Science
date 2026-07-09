# Desigualdade Educacional no ENEM

Repositório que contém o projeto acadêmico final desenvolvido para a disciplina “Fundamentos da Ciência de Dados”.

Este projeto investiga como fatores socioeconômicos - renda familiar, tipo de escola (pública/privada), raça, escolaridade dos pais e região geográfica - se relacionam com o desempenho dos candidatos no Exame Nacional do Ensino Médio (ENEM). Utiliza os microdados públicos disponibilizados pelo [INEP](https://www.gov.br/inep/pt-br/acesso-a-informacao/dados-abertos/microdados/enem) e abrange as edições de 2020 a 2023*.

> *Inicialmente o trabalho considerava o período 2020 a 2024. Porém a partir da edição de 2024, o INEP passou a publicar os microdados em duas tabelas separadas (perfil do participante e resultados das provas) sem identificador comum, em conformidade com a LGPD. Isso inviabiliza análises individuais que cruzem perfil socioeconômico e desempenho, motivo pelo qual a edição de 2024 foi excluída da análise principal.

As cinco notas do candidato no exame (Ciências da Natureza, Ciências Humanas, Linguagens e Códigos, Matemática e Redação) são consideradas e analisadas. Na análise consolidada de todas as edições, apenas a média dessas 5 notas é usada como referência.

## Perguntas de Pesquisa

1. Quais fatores socioeconômicos mais impactam o desempenho dos candidatos no ENEM?
2. Essa relação se manteve estável entre as edições de 2020 a 2023?

## Dataset

| Atributo | Detalhes |
|---|---|
| Fonte | INEP / Ministério da Educação |
| Edições | 2020, 2021, 2022, 2023 |
| Formato | CSV → convertido para Parquet |
| Granularidade | Nível individual (entre 3,4 e 5,8 milhões de registros por edição - variável ano a ano) |
| Principais variáveis | dados demográficos, notas nas provas e informações do questionário socioeconômico |

## Estrutura de Pastas

```
.
├── article/              # Artigo do trabalho em LaTeX (em progresso)
├── data/
│   ├── raw/              # Microdados originais do ENEM em CSV e dicionários oficiais (2020–2023)
│   ├── external/         # Malha das UFs do Brasil (GeoJSON) usada nos mapas
│   └── processed/        # Arquivos Parquet limpos e prontos para análise
├── reports/
│   └── figures/          # Figuras PNG com gráficos e análises
├── slides/               # Slides de apresentação e atualizações do projeto
├── src/                  # Notebooks: tratamento_enem_YYYY, analise_enem_YYYY e analise_consolidada
└── .venv/                # Ambiente virtual Python
```

## Autora

**Carla Moreno Barbosa Nascimento**  
Programa de Pós-Graduação em Informática (PPGI) — UFRJ  
carlamoreno@ic.ufrj.br
