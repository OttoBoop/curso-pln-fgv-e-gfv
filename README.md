# Curso de PLN e Políticas Públicas

**Voluntários da disciplina Laboratório de Políticas Públicas (FGV-EPGE) em parceria com o Gabinete do Vereador Flávio Valle (GFV)**

[![Python](https://img.shields.io/badge/Python-3.8%2B-blue?logo=python&logoColor=white)](https://python.org)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange?logo=jupyter)](https://jupyter.org)
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/OttoBoop/curso-pln-fgv-e-gfv/blob/main/aula-01-classificacao/Classificacao_Noticias_IBRE_Educacional.ipynb)

---

## Sobre o Projeto

Este repositório reúne o material didático de um curso prático de **Processamento de Linguagem Natural (PLN)** aplicado a **políticas públicas**.

O curso é voltado para **voluntários da disciplina Laboratório de Políticas Públicas** (FGV-EPGE) que trabalham em um projeto em parceria com o **Gabinete do Vereador Flávio Valle**. O objetivo do projeto é analisar a percepção de políticas públicas através da análise de notícias com PLN.

O material também está disponível para **qualquer pessoa interessada** em aprender a classificar textos com LLMs. Os notebooks são autocontidos e explicam cada etapa em detalhe — funcionam sem ter assistido às aulas, embora não as substituam.

**Pré-requisito:** conhecimento intermediário de Python.

### Visão do curso

Ao longo do **1º semestre letivo de 2026**, os voluntários aprendem a:

1. **Classificar textos com LLMs** — construir prompts, chamar APIs de modelos de linguagem e avaliar a qualidade dos resultados
2. **Coletar notícias em massa** — usar ferramentas de clipping para baixar notícias de diversos jornais sobre temas específicos
3. **Analisar políticas públicas via PLN** — gerar e analisar suas próprias bases de dados sobre políticas públicas específicas

O repositório está em desenvolvimento ativo. A Aula 01 já está disponível. Novos materiais estão sendo construídos, incluindo a ferramenta de clipping para coleta de notícias e aplicações a análise de políticas públicas.

---

## Como Usar

### Google Colab

Abra o notebook diretamente no navegador clicando no badge **"Open in Colab"** acima da aula desejada. O dataset é baixado automaticamente.

### Execução local

```bash
# 1. Clone o repositório
git clone https://github.com/OttoBoop/curso-pln-fgv-e-gfv.git
cd curso-pln-fgv-e-gfv

# 2. Abra a pasta da aula desejada e execute o notebook
cd aula-01-classificacao
jupyter notebook
```

Cada notebook indica e instala as dependências necessárias na primeira célula.

---

## Estrutura do Repositório

```
curso-pln-fgv-e-gfv/
├── README.md                          # Este arquivo
├── .gitignore                         # Arquivos ignorados pelo Git
└── aula-01-classificacao/             # Material da Aula 01
    ├── Classificacao_Noticias_IBRE_Educacional.ipynb   # Notebook principal
    └── Historias Para classificação.xlsx               # Dataset de 50 notícias
```

---

## Aulas

### Aula 01 — Classificação de Notícias Econômicas com LLMs

> [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/OttoBoop/curso-pln-fgv-e-gfv/blob/main/aula-01-classificacao/Classificacao_Noticias_IBRE_Educacional.ipynb)

Nesta aula, construímos um **pipeline completo de classificação automática de notícias** usando LLMs. A partir de um dataset de 50 notícias econômicas brasileiras, o modelo classifica cada artigo em 4 dimensões:

| Dimensão | Pergunta | Valores |
|----------|----------|---------|
| **Incerteza** | A notícia transmite incerteza econômica? | Sim / Não |
| **Polaridade** | Qual o tom econômico da notícia? | Negativo / Neutro / Positivo |
| **Internacional** | Trata de evento internacional? | Sim / Não |
| **Afeta o Brasil** | Se internacional, afeta a economia brasileira? | Sim / Não / N/A |

**O que a aula cobre:**

- **Engenharia de prompts** — como projetar instruções claras para o modelo classificar corretamente
- **3 abordagens de API:**
  - GPT-3.5-Turbo via Chat Completions (testada e funcional)
  - OpenAI Responses API com Structured Outputs (framework WIP)
  - Google Gemini com Structured Outputs (framework WIP)
- **Extração de dados** — regex para texto livre vs. JSON estruturado (Pydantic, JSON Schema)
- **Avaliação de qualidade** — acurácia, precisão ponderada, matriz de confusão
- **Seção "Agora é Sua Vez"** — espaço para você modificar o prompt e comparar resultados
- **3 desafios abertos** — para quem quer ir além

**Chaves de API:** A chave da OpenAI foi disponibilizada para os voluntários do curso. Para o público externo, é necessário criar sua própria chave (paga). A chave do Google Gemini é gratuita — o notebook explica como obtê-la.

**Sobre o dataset:** adaptado de pesquisa do IBRE/FGV (Instituto Brasileiro de Economia), quando Otávio Bopp era estagiário. Contém 50 notícias econômicas brasileiras já classificadas por humanos, servindo como gabarito para avaliar os modelos.

#### O que você vai aprender

Ao concluir o notebook, você será capaz de:

- **Projetar prompts eficazes** para tarefas de classificação de texto com LLMs
- **Chamar APIs de LLMs** via Python
- **Usar Structured Outputs** (Pydantic + JSON Schema) para obter respostas em formato padronizado
- **Avaliar modelos de classificação** com métricas quantitativas (acurácia, precisão, matriz de confusão)
- **Comparar provedores** de LLM e entender os trade-offs entre eles
- **Iterar e melhorar prompts** com base na análise de erros

---

## Créditos

- **Laboratório de Políticas Públicas** — FGV-EPGE (Escola de Economia da FGV Rio)
- **Gabinete do Vereador Flávio Valle** — Câmara Municipal do Rio de Janeiro
- **Otávio Bopp** — autor e instrutor do curso
- **Dataset da Aula 01** — adaptado de pesquisa do IBRE/FGV (Instituto Brasileiro de Economia)
