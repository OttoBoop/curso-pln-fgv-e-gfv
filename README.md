# Curso de PLN e Politicas Publicas

**Laboratorio de Politicas Publicas (FGV-EPGE) em parceria com o Gabinete do Vereador Flavio Valle (GFV)**

[![Python](https://img.shields.io/badge/Python-3.8%2B-blue?logo=python&logoColor=white)](https://python.org)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange?logo=jupyter)](https://jupyter.org)
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/OttoBoop/curso-pln-fgv-e-gfv/blob/main/aula-01-classificacao/Classificacao_Noticias_IBRE_Educacional.ipynb)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

---

## Sobre o Projeto

Este repositorio reune o material didatico de um curso pratico de **Processamento de Linguagem Natural (PLN)** aplicado a **politicas publicas**. O curso e organizado pelo **Laboratorio de Politicas Publicas da FGV-EPGE** em parceria com o **Gabinete do Vereador Flavio Valle (GFV)**.

### O que voce vai encontrar aqui

Material de aulas que ensinam, passo a passo, como usar modelos de linguagem (LLMs) para analisar noticias — desde a classificacao automatica ate a coleta em massa. Todo o conteudo foi pensado para ser acessivel: mesmo que voce nao tenha participado das aulas presenciais, os notebooks sao autocontidos e explicam cada etapa em detalhe.

### Visao do curso

O objetivo final e que os participantes consigam, de forma autonoma:

1. **Classificar noticias com LLMs** — construir prompts eficazes, chamar APIs (OpenAI, Google Gemini) e avaliar a qualidade dos resultados
2. **Coletar noticias em massa** — usar ferramentas de clipping para baixar noticias de diversos jornais sobre temas especificos
3. **Analisar politicas publicas via PLN** — aplicar as tecnicas aprendidas para avaliar como a imprensa cobre temas de politicas publicas

---

## Aulas

### Aula 01 — Classificacao de Noticias Economicas com LLMs

> [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/OttoBoop/curso-pln-fgv-e-gfv/blob/main/aula-01-classificacao/Classificacao_Noticias_IBRE_Educacional.ipynb)

Nesta aula, construimos um **pipeline completo de classificacao automatica de noticias** usando LLMs. A partir de um dataset de 50 noticias economicas brasileiras, o modelo classifica cada artigo em 4 dimensoes:

| Dimensao | Pergunta | Valores |
|----------|----------|---------|
| **Incerteza** | A noticia transmite incerteza economica? | Sim / Nao |
| **Polaridade** | Qual o tom economico da noticia? | Negativo / Neutro / Positivo |
| **Internacional** | Trata de evento internacional? | Sim / Nao |
| **Afeta o Brasil** | Se internacional, afeta a economia brasileira? | Sim / Nao / N/A |

**O que a aula cobre:**

- **Engenharia de prompts** — como projetar instrucoes claras para o modelo classificar corretamente
- **3 abordagens de API:**
  - GPT-3.5-Turbo via Chat Completions (testada e funcional)
  - OpenAI Responses API com Structured Outputs (framework WIP)
  - Google Gemini com Structured Outputs (framework WIP)
- **Extracao de dados** — regex para texto livre vs. JSON estruturado (Pydantic, JSON Schema)
- **Avaliacao de qualidade** — acuracia, precisao ponderada, matriz de confusao
- **Secao "Agora e Sua Vez"** — espaco para voce modificar o prompt e comparar resultados
- **3 desafios abertos** — para quem quer ir alem

**Sobre o dataset:** Adaptado de pesquisa do IBRE/FGV (Instituto Brasileiro de Economia), quando Otavio Bopp era estagiario. Contem 50 noticias economicas brasileiras ja classificadas por humanos, servindo como gabarito para avaliar os modelos.

### Em breve

Aulas futuras cobrirao a ferramenta de clipping para coleta de noticias em massa e aplicacoes especificas a analise de politicas publicas.

---

## Como Usar

### Opcao 1: Google Colab (recomendada)

A forma mais simples — nao precisa instalar nada no seu computador:

1. Clique no badge **"Open in Colab"** acima da aula desejada
2. O notebook abre direto no seu navegador
3. Siga as instrucoes dentro do notebook (ele explica como configurar as chaves de API)

### Opcao 2: Execucao local

```bash
# 1. Clone o repositorio
git clone https://github.com/OttoBoop/curso-pln-fgv-e-gfv.git
cd curso-pln-fgv-e-gfv

# 2. Instale as dependencias
pip install openai google-genai pandas scikit-learn openpyxl python-dotenv

# 3. Abra o notebook
jupyter notebook aula-01-classificacao/Classificacao_Noticias_IBRE_Educacional.ipynb
```

### Pre-requisitos

- **Python 3.8+**
- **Chave de API da OpenAI** (obrigatoria para a Aula 01)
- **Chave de API do Google Gemini** (opcional — usada no modulo 3)

O notebook explica em detalhe como obter e configurar cada chave.

---

## O que Voce Vai Aprender (Aula 01)

Ao concluir o notebook, voce sera capaz de:

- **Projetar prompts eficazes** para tarefas de classificacao de texto com LLMs
- **Chamar APIs de LLMs** (OpenAI e Google Gemini) via Python
- **Usar Structured Outputs** (Pydantic + JSON Schema) para obter respostas em formato padronizado
- **Avaliar modelos de classificacao** com metricas quantitativas (acuracia, precisao, matriz de confusao)
- **Comparar provedores** de LLM e entender os trade-offs entre eles
- **Iterar e melhorar prompts** com base na analise de erros

---

## Tecnologias

| Pacote | Para que serve |
|--------|---------------|
| `openai` | Cliente oficial da API da OpenAI |
| `google-genai` | Cliente oficial da API do Google Gemini |
| `pandas` | Manipulacao e analise de dados tabulares |
| `scikit-learn` | Metricas de avaliacao (acuracia, precisao, matriz de confusao) |
| `openpyxl` | Leitura de arquivos Excel (.xlsx) |
| `python-dotenv` | Carregamento seguro de chaves de API |
| `pydantic` | Definicao de schemas para Structured Outputs |

---

## Estrutura do Repositorio

```
curso-pln-fgv-e-gfv/
├── README.md                          # Este arquivo
├── .gitignore                         # Arquivos ignorados pelo Git
└── aula-01-classificacao/             # Material da Aula 01
    ├── Classificacao_Noticias_IBRE_Educacional.ipynb   # Notebook principal
    └── Historias Para classificação.xlsx               # Dataset de 50 noticias
```

---

## Creditos

- **Laboratorio de Politicas Publicas** — FGV-EPGE (Escola de Economia da FGV Rio)
- **Gabinete do Vereador Flavio Valle** — Camara Municipal do Rio de Janeiro
- **Otavio Bopp** — autor e instrutor do curso
- **Dataset original** — adaptado de pesquisa do IBRE/FGV (Instituto Brasileiro de Economia)

---

## Licenca

Este projeto e distribuido sob a licenca MIT. Veja [LICENSE](LICENSE) para mais detalhes.
