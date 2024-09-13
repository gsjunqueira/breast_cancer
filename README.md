# Projeto: Classificação de Câncer de Mama (Breast Cancer Wisconsin - Diagnostic)

## Objetivo Principal

Desenvolver classificadores para o conjunto de dados [Breast Cancer Wisconsin (Diagnostic)](https://archive.ics.uci.edu/static/public/17/breast+cancer+wisconsin+diagnostic) da UCI, visando identificar tumores malignos e benignos com base em características dos núcleos celulares de imagens de aspiração por agulha fina (FNA).

### Descrição dos Dados

Os dados consistem em recursos computados a partir de imagens de FNA de uma massa mamária, descrevendo características dos núcleos celulares presentes. O conjunto de dados é amplamente utilizado para a classificação binária de tumores em malignos e benignos.

Mais informações sobre os dados estão disponíveis [aqui](http://www.cs.wisc.edu/~street/images/).

## Bibliotecas Utilizadas

As principais bibliotecas Python utilizadas para o desenvolvimento deste projeto incluem:

- `numpy`
- `pandas`
- `matplotlib`
- `seaborn`
- `scikit-learn`
- `imblearn`
- `ucimlrepo`

## Pré-Processamento

1. **Divisão de Dados**: Os dados foram divididos em conjuntos de treino e teste usando a técnica do holdout com 70% dos dados para treino e 30% para teste.
2. **Normalização**: Aplicada aos dados de treino e, posteriormente, aos dados de teste usando `StandardScaler`.
3. **Balanceamento de Classes**: Utilizou-se o método `SMOTE` para corrigir o desbalanceamento entre as classes no conjunto de treino.
4. **Codificação de Labels**: As classes foram convertidas em valores numéricos com `LabelEncoder`.

## Seleção de Parâmetros

### A seguir, são descritas as diferentes abordagens de seleção de parâmetros realizadas

- **Correlação**: Os 5 parâmetros com maior correlação com a variável de saída foram selecionados com base na matriz de correlação.
- **Informação Mútua**: A seleção dos 5 principais parâmetros foi baseada na pontuação da informação mútua.
- **Razão Discriminante de Fisher**: Seleção de parâmetros com base nas contribuições para a razão discriminante de Fisher, calculada via Análise Discriminante Linear (LDA).
- **Análise de Componentes Principais (PCA)**: Redução dimensional com PCA, mantendo os 5 principais componentes.

## Funções Auxiliares

- **Heatmap**: Para visualização da matriz de correlação.
- **Matriz de Confusão**: Função para exibir graficamente a matriz de confusão dos modelos.
- **Indicadores de Desempenho**: Função que calcula a acurácia, sensibilidade e especificidade de cada classificador.

1. **Classificador baseado na distância de Mahalanobis**:
   - Implementação do cálculo da distância de Mahalanobis e uso dessa métrica para classificar os dados.
   - Avaliação do desempenho usando todos os parâmetros e subconjuntos de características (correlação, informação mútua, discriminante de Fisher e PCA).

2. **Classificador k-NN (K-Nearest Neighbors)**:
   - Implementação do k-NN, utilizando tanto todos os parâmetros quanto os subconjuntos mencionados.

3. **Classificador LDA (Linear Discriminant Analysis)**:
   - Implementação e avaliação do LDA nos diferentes cenários.

4. **Classificador MLP (Multilayer Perceptron)**:
   - Implementação de uma rede neural simples (MLP) com uma camada oculta e 16 neurônios, também avaliando com diferentes conjuntos de características.

5. **Classificador SVM (Support Vector Machine)**:
   - Utilização de SVM com kernel radial (RBF), aplicando as mesmas técnicas de avaliação.

As funções implementadas para cada classificador recebem os dados balanceados e retornam uma série de métricas de desempenho, como **acurácia**, **sensibilidade** e **especificidade**, que são utilizadas para comparar os modelos.

Na seção final, os resultados são analisados com base nas métricas. O código finaliza mostrando qual classificador apresentou o melhor desempenho em termos de acurácia, sensibilidade e especificidade.

## Contribuições

Contribuições são bem-vindas! Sinta-se à vontade para abrir uma _issue_ ou _pull request_ para melhorias.

## Licença

Este projeto é licenciado sob os termos da MIT License.
