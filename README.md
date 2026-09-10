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

Classificação de Iris com SVM

Análise completa do dataset Iris usando dados externos obtidos do Kaggle, com modelo de classificação construído exclusivamente com Support Vector Machine.

Dataset: Iris Species — 150 amostras, 4 atributos numéricos e 3 classes balanceadas.

Notebook no Kaggle: https://www.kaggle.com/code/joaovitorpedroso/atividade-svm-jo-o-vitor-ferreira-pedroso-09-9

Etapas desenvolvidas:

Extração dos dados — leitura do CSV anexado em /kaggle/input, sem uso de load_iris()
EDA — estrutura e tipos das colunas, verificação de nulos e duplicados, estatísticas descritivas, balanceamento das classes, histogramas e boxplots por espécie, dispersão par a par e matriz de correlação
Preparação — remoção da coluna identificadora, codificação do alvo com LabelEncoder, divisão estratificada em treino e teste (70/30) e padronização com StandardScaler ajustada apenas no treino
Modelo — SVC do scikit-learn, com ajuste de C, kernel e gamma via GridSearchCV dentro de um Pipeline, usando validação cruzada estratificada de 5 dobras
Avaliação — acurácia, precisão, revocação, F1 por classe, matriz de confusão, validação cruzada no dataset completo e visualização da fronteira de decisão

## Releases

| Versão | Data | Conteúdo |
|---|---|---|
| v1.0 | 12/08/2026 | Notebook com os 50 exercícios de Python |
| v2.0 | 23/08/2026 | Notebook com os 80 exercícios de Data Science |
| v3.0 | 09/09/2026 | Notebook de classificação de Iris com SVM, usando dataset do Kaggle |

