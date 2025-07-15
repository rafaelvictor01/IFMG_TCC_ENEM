# 🧠 Análise de Perfil de Candidatos do ENEM (2019–2023)

Este projeto é o resultado do meu Trabalho de Conclusão de Curso (TCC) para o curso de **Bacharelado em Sistemas de Informação** pelo [Instituto Federal de Minas Gerais – Campus Sabará](https://www.ifmg.edu.br/sabara). O principal objetivo foi **identificar padrões de perfil socioeconômico e educacional entre os candidatos do ENEM**, utilizando técnicas de **mineração de dados, clusterização e seleção de atributos** (feature selection).

> 📘 **Leitura recomendada:** Para uma compreensão completa da metodologia, análises e justificativas, recomendo a leitura do trabalho na íntegra, disponível no [Repositório Institucional do IFMG](https://repositorio.ifmg.edu.br/items/a0666de3-5c99-4b98-8d0b-8de9e9786038). Uma versão em PDF está também incluída neste repositório.

---

## 🎯 Objetivo

Trabalhamos com os **Microdados do ENEM** — bases públicas fornecidas pelo [INEP](https://www.gov.br/inep/pt-br/acesso-a-informacao/dados-abertos/microdados/enem), com milhões de registros por ano. O foco foi identificar **grupos de candidatos com perfis similares** e entender **quais variáveis mais os caracterizam**, mesmo sem considerar diretamente suas notas.

---

## 🛠️ Tecnologias e Ferramentas

- **Python + Jupyter Notebooks**
- **Pandas, Scikit-learn**
- **Matplotlib**
- *(opcional)* Microsoft Excel ou LibreOffice Calc

> 💡 **Dica:** Devido ao volume massivo dos dados, a execução **não é recomendada em ambientes de notebooks online** como o Google Colab. Preferencialmente, execute localmente em um ambiente com recursos adequados.

### 💻 Ambiente de Desenvolvimento

> **CPU:** AMD Ryzen 5 2600 Six-Core – 3.40 GHz  
> **RAM:** 32 GB (dual-channel)  
> **Sistema:** Windows 11 Pro – 64 bits (versão 24H2)

---

## 🤨 Problema-chave

> **Como agrupar milhões de candidatos do ENEM por perfil socioeconômico/educacional de forma escalável e compreensível, e entender o que define cada grupo – sem considerar as notas como fator direto?**

---

## ⚙️ Estratégia Modular

Para contornar limitações de hardware, optei por uma **arquitetura modular baseada em scripts independentes por etapa**. Essa abordagem permitiu:

- Executar e debugar partes isoladas sem repetir todo o pipeline
- Manter datasets em memória o menor tempo possível
- Tratar dados ano a ano, de forma incremental

### 🔗 Notebooks por etapa

| Script | Descrição |
|--------|-----------|
| `0_Analise_Exploratoria.ipynb` | Análise inicial dos dados brutos e identificação de padrões e variáveis interessantes |
| `1_Pre_Processamento.ipynb` | Limpeza, normalização e transformação dos dados |
| `2_Definicao_Num_Clusters.ipynb` | Estudo do número ideal de clusters via método do cotovelo (Elbow Method) |
| `3_Clusterizacao.ipynb` | Aplicação do K-Means e geração dos agrupamentos por perfil |
| `4_Feature_Selection.ipynb` | Extração de características marcantes por cluster usando SelectKBest e Chi² como função de pontuação |
| `5_Graficos.ipynb` | Geração de visualizações gráficas para compor o relatório e apresentação final |

> 📂 Algumas pastas adicionais como `ManualClusteringAnalysis/` e `ManualFeatureSelectionAnalysis/` contêm rascunhos e documentos auxiliares utilizados no processo de análise e validação dos resultados.

---

## 🧪 Exemplos de Resultados

A clusterização permitiu identificar cinco grupos bem definidos quanto aos seus aspectos socioeconômicos.
Embora o agrupamento não tenha considerado as notas dos candidatos como critério de segmentação, utilizamos as médias de pontuação dos participantes para estabelecer comparações entre os grupos.
As análises evidenciaram uma correlação positiva entre o aprimoramento dos indicadores socioeconômicos e o desempenho no exame.
Aspectos como renda familiar, origem da renda, infraestrutura doméstica e acesso à tecnologia foram recorrentes na caracterização dos grupos, tanto neste estudo quanto em pesquisas relacionadas.
Além disso, análises quantitativas complementares demonstraram a influência de fatores como região de origem, cor/raça e escolaridade dos pais na composição dos grupos com maiores e menores desempenhos no exame.
