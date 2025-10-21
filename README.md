# Prova 1 - Controle Estatístico de Processo (CEP)

**Aluna:** Camila de Araújo Valença
**Matrícula:** 202014548

## Descrição Geral (O Quê?)

Este repositório contém a análise de Controle Estatístico de Processo (CEP) realizada para a Prova 1 da disciplina. O objetivo foi avaliar a estabilidade de um processo de manufatura (baseado na medição de `Torque [Nm]`) utilizando as **Cartas de Controle X-barra ($\bar{X}$)** e **R (Amplitude)**. A análise segue estritamente o roteiro de 10 passos fornecido pelo professor, implementado em um notebook do Google Colab.

## Dataset Utilizado (A Matéria-Prima)

* **Fonte:** Kaggle
* **Nome Original:** AI4I 2020 Predictive Maintenance Dataset
* **Arquivo Utilizado:** `(dataset)CamilaValenca_CEP_Prova.csv`
* **Variável Analisada:** `Torque [Nm]` - Uma medida quantitativa contínua relevante para o desempenho ou condição do equipamento.
* **Estrutura para Análise:** Foram selecionadas as primeiras 125 observações válidas e sequenciais da variável `Torque [Nm]` do dataset original. Estas foram organizadas em **25 amostras (subgrupos) de tamanho n=5**, conforme exigido pela metodologia das cartas $\bar{X}$ e R.

## Metodologia Aplicada (Como Foi Feito?)

A análise seguiu um roteiro estruturado de 10 passos, implementado no notebook `.ipynb`:

1.  **Importação das Bibliotecas:** Carregamento das ferramentas Python (`pandas`, `numpy`, `matplotlib`, `os`, `textwrap`) necessárias para manipulação de dados, cálculos e visualização.
2.  **Carregamento e Preparação dos Dados:** Leitura do arquivo CSV, seleção e limpeza da variável `Torque [Nm]`, e estruturação das 125 medições nas 25 amostras de n=5.
3.  **Cálculo das Estatísticas por Amostra:** Para cada uma das 25 amostras, foram calculadas a **Média Amostral ($\bar{X}$)** e a **Amplitude Amostral (R)**.
4.  **Cálculo dos Limites de Controle (Carta $\bar{X}$):** Determinação da Média das Médias ($\bar{\bar{X}}$), Amplitude Média ($\bar{R}$), e dos Limites Superior (LSC), Inferior (LIC) e Linha Central (LC) para a carta $\bar{X}$, usando a constante A₂ = 0.577.
5.  **Cálculo dos Limites de Controle (Carta R):** Determinação dos Limites Superior (LSC), Inferior (LIC) e Linha Central (LC) para a carta R, usando as constantes D₃ = 0 e D₄ = 2.114.
6.  **Construção da Carta $\bar{X}$:** Geração do gráfico da Carta $\bar{X}$, plotando as 25 médias amostrais contra os limites calculados. O gráfico foi exibido no notebook e salvo como `.png`.
7.  **Construção da Carta R:** Geração do gráfico da Carta R, plotando as 25 amplitudes amostrais contra os limites calculados. O gráfico foi exibido no notebook e salvo como `.png`.
8.  **Análise de Pontos Fora de Controle:** Identificação automática das amostras cujos valores de $\bar{X}$ ou R ultrapassaram os limites de controle.
9.  **Interpretação dos Resultados:** Avaliação formal do estado de controle estatístico do processo, discussão sobre a presença de causas especiais e sugestão de ações corretivas.
10. **Documentação:** Inclusão de comentários no código e elaboração deste `README.md` e dos textos explicativos no notebook.

## Estrutura do Repositório (Dicionário de Arquivos)

Este repositório está organizado com os seguintes arquivos:

* `CamilaValenca_CEP_Prova.ipynb`:
    * **Tipo:** Notebook do Google Colab.
    * **Conteúdo:** Arquivo principal contendo todo o código Python da análise, os textos explicativos detalhando cada passo da metodologia, os gráficos gerados ($\bar{X}$ e R) e as saídas textuais (cálculos, pontos fora de controle, interpretação final).

* `(dataset)CamilaValenca_CEP_Prova.csv`:
    * **Tipo:** Arquivo CSV (Comma Separated Values).
    * **Conteúdo:** Os dados de entrada utilizados (originalmente do Kaggle), contendo as medições da variável `Torque [Nm]`.

* `carta_xbar_CamilaValenca_CEP_Prova.png`:
    * **Tipo:** Arquivo de Imagem PNG.
    * **Conteúdo:** Gráfico visual da Carta de Controle X-barra ($\bar{X}$) resultante da análise.

* `carta_r_CamilaValenca_CEP_Prova.png`:
    * **Tipo:** Arquivo de Imagem PNG.
    * **Conteúdo:** Gráfico visual da Carta de Controle R (Amplitude) resultante da análise.

* `xbar_r_por_amostra_CamilaValenca_CEP_Prova.csv`:
    * **Tipo:** Arquivo CSV.
    * **Conteúdo:** Tabela com os resultados dos cálculos intermediários: para cada uma das 25 amostras, lista a média ($\bar{X}$) e a amplitude (R) calculadas.

* `CamilaValenca_CEP_Prova.txt`:
    * **Tipo:** Arquivo de Texto (.txt).
    * **Conteúdo:** Transcrição da interpretação final dos resultados (Passo 9), detalhando a avaliação do controle estatístico, as amostras anômalas e as recomendações.

* `README.md`:
    * **Tipo:** Arquivo Markdown.
    * **Conteúdo:** Este arquivo, servindo como guia e dicionário para o conteúdo e a análise presente no repositório.

## Resumo dos Resultados (A Conclusão)

A análise das Cartas de Controle $\bar{X}$ e R indicou que o processo está parcialmente sob controle estatístico. Foram identificados pontos fora dos limites de controle, sugerindo a presença de **causas especiais de variação**:
* **Na Carta $\bar{X}$:** Nenhuma.
* **Na Carta R:** Amostra 11.

Isso indica que o processo de medição/aplicação de torque apresentou uma instabilidade na variabilidade durante o período analisado. Recomenda-se investigar as causas associadas à amostra fora de controle].

A interpretação detalhada e as recomendações específicas podem ser encontradas no notebook (`.ipynb`) e no arquivo `CamilaValenca_CEP_Prova.txt`.

## Como Executar a Análise (Para Reproduzir)

1.  Faça o download (ou clone) deste repositório.
2.  Abra o Google Colab (<https://colab.research.google.com/>).
3.  Faça o upload do notebook `CamilaValenca_CEP_Prova.ipynb`.
4.  Faça o upload do arquivo de dados `(dataset)CamilaValenca_CEP_Prova.csv` para o ambiente do Colab (diretório raiz `/content/`).
5.  Execute as células do notebook em ordem sequencial.
