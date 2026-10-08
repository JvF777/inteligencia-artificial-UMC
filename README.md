# Inteligência Artificial — UMC

Repositório com os notebooks desenvolvidos na disciplina de Inteligência Artificial.

**Aluno:** João Vitor Ferreira Pedroso  
**Curso:** Engenharia de Software  
**Turma:** 6°  
**Período:** Noturno
**Professor:** Fabiano Bezerra Menegidio

## Arquivos

| Arquivo | Descrição | Entrega |
|---|---|---|
| `Exercícios_Python_JoaoVitorFerreiraPedroso_6_B_Noite.ipynb` | 50 exercícios de Python — fundamentos da linguagem | 12/08/2026 |
| `Exercícios_DataScience_JoaoVitorFerreiraPedroso_6_B_Noite.ipynb` | 80 exercícios de Data Science — NumPy, SciPy, Pandas e Matplotlib | 23/08/2026 |
| `atividade-svm-jo-o-vitor-ferreira-pedroso-09-9.ipynb` | Classificação de espécies de Iris com Support Vector Machine, usando dataset externo do Kaggle | 09/09/2026 |
| `Water_Potability SUMMIT`  | 	Classificação de potabilidade da água com Support Vector Machine, usando dataset externo do Kaggle | 17/09/2026 |
| `joao_pedroso_SVM.ipynb` | Previsão do valor de imóveis com Support Vector Regression (SVR), usando o dataset California Housing do Kaggle | 01/10/2026 |
| `joao_pedroso_relatorio.pdf` | Relatório da atividade de previsão do valor de imóveis com SVR | 01/10/2026 |
| `iris_modelos.ipynb` | Comparação de SVM, Árvore de Decisão, Floresta Aleatória e Boosting no dataset Iris, com e sem GridSearchCV | 01/10/2026 |
| `classificacao_fishmorph_svm.ipynb` | Classificação de ordens de peixes com Support Vector Machine, usando o dataset FishMorph do Kaggle | 07/10/2026 |


----------------------------------------------------------------------------------------------------------------------------------------------------------

## 50 exercícios Python

Resolução dos 50 exercícios propostos. Cada exercício traz o código comentado, com justificativa das escolhas de implementação.

Conteúdos abordados:

- Entrada e saída, variáveis e f-strings
- Operadores aritméticos e operador de resto (`%`)
- Estruturas condicionais (`if/elif/else`, `match/case`)
- Laços de repetição (`for`, `while`) e controle de fluxo (`break`)
- Listas, dicionários e manipulação de strings

----------------------------------------------------------------------------------------------------------------------------------------------------------
## Exercícios de Data Science

80 exercícios divididos em quatro bibliotecas, com código comentado.

**NumPy (20 exercícios)** — criação de arrays e matrizes, fatiamento, `reshape`, operações elemento a elemento, estatística descritiva (mediana, moda, correlação), normalização, soma cumulativa e manipulação de diagonais.

**SciPy (20 exercícios)** — integração simples e dupla (`quad`), equações diferenciais (`solve_ivp`), busca de raízes (`root`, `fsolve`), otimização (`minimize`), transformada de Fourier (`fft`, `ifft`), álgebra linear (`solve`, `inv`, `det`, `eig`), interpolação (`interp1d`) e ajuste de curvas (`curve_fit`).

**Pandas (20 exercícios)** — criação de DataFrames, leitura e escrita de arquivos (CSV e Excel), filtragem por condição, criação de colunas calculadas, tratamento de valores nulos (`dropna`, `fillna`, `interpolate`), agrupamento (`groupby`, `pivot_table`), junção de tabelas (`merge`) e ordenação.

**Matplotlib (20 exercícios)** — gráficos de linha, dispersão, barras (verticais, horizontais e empilhadas), pizza, subplots, gráfico 3D, personalização de cores, grade, rótulos, legendas, limites de eixos e exportação para PDF.

----------------------------------------------------------------------------------------------------------------------------------------------------------

## Classificação de Iris com SVM

Análise completa do dataset Iris usando dados externos obtidos do Kaggle, com modelo de classificação construído exclusivamente com Support Vector Machine.

Dataset: Iris Species — 150 amostras, 4 atributos numéricos e 3 classes balanceadas.

Notebook no Kaggle: https://www.kaggle.com/code/joaovitorpedroso/atividade-svm-jo-o-vitor-ferreira-pedroso-09-9

Etapas desenvolvidas:

Extração dos dados — leitura do CSV anexado em /kaggle/input, sem uso de load_iris()
EDA — estrutura e tipos das colunas, verificação de nulos e duplicados, estatísticas descritivas, balanceamento das classes, histogramas e boxplots por espécie, dispersão par a par e matriz de correlação
Preparação — remoção da coluna identificadora, codificação do alvo com LabelEncoder, divisão estratificada em treino e teste (70/30) e padronização com StandardScaler ajustada apenas no treino
Modelo — SVC do scikit-learn, com ajuste de C, kernel e gamma via GridSearchCV dentro de um Pipeline, usando validação cruzada estratificada de 5 dobras
Avaliação — acurácia, precisão, revocação, F1 por classe, matriz de confusão, validação cruzada no dataset completo e visualização da fronteira de decisão

----------------------------------------------------------------------------------------------------------------------------------------------------------
## Classificação de potabilidade da água com SVM

Classificação de amostras de água quanto à potabilidade a partir de parâmetros físico-químicos, com modelo construído exclusivamente com Support Vector Machine. Projeto apresentado em formato de pôster no UMC Summit.

Dataset: Water Quality — 3.276 amostras, 9 atributos numéricos contínuos e alvo binário.

Notebook no Kaggle: https://www.kaggle.com/code/joaovitorpedroso/summit-umc-water

Etapas desenvolvidas:

Avaliação da base — estrutura, tipos das colunas, estatísticas descritivas e análise da disparidade de escala entre os atributos Tratativa de codificação — verificação da presença de atributos categóricos, dispensada por a base ser integralmente numérica, com a rotina mantida para reprodutibilidade Tratativa de dados ausentes — 1.434 valores ausentes em três atributos, com destaque para o sulfato (23,84%). Comparação entre remoção das observações incompletas, que implicaria perda de 38,6% da base, e imputação pela mediana, estratégia adotada por preservar o volume amostral EDA — distribuição dos atributos, identificação de valores atípicos por diagrama de caixa, comparação das distribuições entre classes e matriz de correlação Preparação — divisão estratificada em treino e teste (80/20) e padronização com StandardScaler ajustada apenas no treino Modelo — SVC do scikit-learn, com ajuste de C e gamma via GridSearchCV, usando validação cruzada estratificada de 5 dobras, comparado a um modelo de referência com parâmetros padrão Avaliação — acurácia, precisão, revocação, F1, relatório de classificação e matriz de confusão em valores absolutos e percentuais

Resultados: acurácia de 67,07% no conjunto de teste, contra 60,98% de um classificador que sempre previsse a classe majoritária. A busca em grade selecionou os valores padrão da biblioteca, não produzindo ganho sobre o modelo de referência, o que indica que o desempenho é limitado pela capacidade discriminativa dos atributos e não pela parametrização. A matriz de confusão revelou viés conservador, com 29 falsos positivos contra 187 falsos negativos, assimetria que favorece o lado de menor risco sanitário.

----------------------------------------------------------------------------------------------------------------------------------------------------------

## Previsão do valor de imóveis com SVR

Atividade de SVM para regressão, com o algoritmo SVR do scikit-learn. O objetivo é prever o valor mediano das casas e obter R² maior que 0,65 no conjunto de teste.

**Dataset:** Housing (California Housing), do Kaggle, com 20.640 registros e 10 atributos, sendo 9 numéricos e 1 categórico. Variável alvo: median_house_value.

**Notebook no Kaggle:** : https://www.kaggle.com/code/joaovitorpedroso/joaovitor-ferreirapedroso

**Etapas desenvolvidas:**

* **Análise exploratória:** dimensões, tipos, estatísticas descritivas, distribuição do alvo, boxplots e matriz de correlação
* **Valores ausentes:** 207 valores em total_bedrooms (1%), com comparação entre remover linhas, remover coluna, imputar pela média e imputar pela mediana
* **Outliers:** identificação pelo método do IQR e tratamento por capping, sem remover registros
* **Preparação:** codificação one-hot, divisão 80/20 com random_state=42 e padronização com StandardScaler
* **Modelo:** SVR de referência, comparação dos kernels linear, rbf e poly e busca de hiperparâmetros com GridSearchCV
* **Avaliação:** R², MAE, RMSE e gráfico de valores reais e previstos

**Resultados:** R² de 0,7678 no conjunto de teste, MAE de 36.422,83 e RMSE de 55.155,71. Os modelos iniciais tiveram R² negativo, e o resultado só melhorou quando o alvo também foi padronizado. O kernel rbf foi o melhor, e o modelo final usou C igual a 10, epsilon igual a 0,1 e gamma igual a scale.

**Arquivos:** joao_pedroso_SVM.ipynb e joao_pedroso_relatorio.pdf

----------------------------------------------------------------------------------------------------------------------------------------------------------

## Comparação de modelos de classificação no dataset Iris

Comparação entre SVM, Árvore de Decisão, Floresta Aleatória e Boosting, cada um com e sem GridSearchCV, avaliados por acurácia e sensibilidade.

**Dataset:** Iris Species, 150 amostras (149 após remoção de duplicata), 4 atributos numéricos e 3 classes balanceadas.

**Notebook no Kaggle: https://www.kaggle.com/code/joaovitorpedroso/dataset-iris-rvore-de-decis-o

**Etapas desenvolvidas:**

* **Inspeção e limpeza:** estrutura, tipos, verificação de nulos e remoção de linha duplicada
* **EDA:** estatísticas descritivas por espécie, distribuição dos atributos e boxplots
* **Preparação:** divisão estratificada em treino e teste
* **Modelos:** SVM, Árvore de Decisão, Floresta Aleatória e Gradient Boosting, com configuração padrão e com GridSearchCV
* **Avaliação:** acurácia, sensibilidade (recall macro) e matriz de confusão no conjunto de teste

**Resultados:** cinco configurações empataram com 96,67% de acurácia no conjunto de teste. O SVM sem GridSearchCV foi o modelo recomendado, escolhido como critério de desempate por ser o mais simples. A setosa foi separada com 100% de sensibilidade por todos os modelos, e os erros ocorreram entre versicolor e virginica, que se sobrepõem nos atributos.

----------------------------------------------------------------------------------------------------------------------------------------------------------

## Classificação de ordens de peixes com SVM

Classificação da ordem taxonômica de peixes a partir de atributos morfológicos, com modelo construído exclusivamente com Support Vector Machine.

**Dataset:**: https://www.kaggle.com/datasets/menegidio/fishmorph-dataset

**Notebook:**: https://colab.research.google.com/drive/1_cNaiMkAb8oPApYZhpqqQ1xe6nB53h-h#scrollTo=_h4A1KrmZFsb

**Etapas desenvolvidas:**

* **Extração dos dados:** download direto do Kaggle com kagglehub, escolhendo a versão por ordem por ter menos classes e mais amostras por classe que a versão por família
* **Avaliação da base:** estrutura, tipos das colunas e estatísticas descritivas, com os 10 atributos numéricos e a ordem como única coluna de texto
* **Tratativa de dados:** nenhum valor ausente encontrado e remoção de 1 linha duplicada
* **Filtragem das classes:** a base apresentava 32 ordens fortemente desbalanceadas, algumas com apenas 1 amostra. Foram mantidas as 8 ordens com pelo menos 100 amostras, viabilizando a divisão estratificada e a validação cruzada
* **EDA:** distribuição das categorias, histogramas, diagramas de caixa e matriz de correlação, com correlações fracas a moderadas (máxima de 0,55) e sem redundância entre atributos
* **Preparação:** codificação do alvo com LabelEncoder, divisão estratificada em treino e teste (80/20) e padronização com StandardScaler ajustada apenas no treino
* **Modelo:** SVC do scikit-learn com GridSearchCV testando 4 valores de kernel (linear, rbf, poly, sigmoid), C (0,1, 1, 10, 100) e gamma (0,001, 0,01, 0,1, 1), totalizando 64 combinações, com validação cruzada estratificada de 5 dobras em amostra de 3.000 linhas do treino e limite de iterações para combinações de convergência lenta
* **Avaliação:** acurácia, relatório de classificação e matriz de confusão

**Resultados:** o melhor modelo foi o SVM com kernel RBF, C = 10 e gamma = 0,1, com acurácia de 80,77% na validação cruzada e 81,43% no conjunto de teste. A proximidade entre as duas métricas indica boa generalização, sem sinais de overfitting. O kernel RBF ocupou as cinco primeiras posições da busca, enquanto o linear ficou cerca de 7 pontos abaixo, mostrando que a separação entre as ordens é não linear.

## Releases

| Versão | Data | Conteúdo |
|---|---|---|
| v1.0 | 12/08/2026 | Notebook com os 50 exercícios de Python |
| v2.0 | 23/08/2026 | Notebook com os 80 exercícios de Data Science |
| v3.0 | 09/09/2026 | Notebook de classificação de Iris com SVM, usando dataset do Kaggle |
| v4.0 | 17/09/2026 | Notebook de classificação de potabilidade da água com SVM, usando dataset do Kaggle |
| v5.0 | 07/10/2026 | Notebooks de previsão do valor de imóveis com SVR, comparação de modelos na Iris e classificação de ordens de peixes com SVM |





