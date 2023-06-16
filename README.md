
# Fake News Classifier

Este projeto consiste em um classificador de notícias falsas utilizando aprendizado de máquina. Ele utiliza o algoritmo de Regressão Logística para realizar a classificação.

## Pré-requisitos
```markdown
Certifique-se de ter as seguintes bibliotecas instaladas no seu ambiente Python:

- pandas
- numpy
- nltk
- scikit-learn

Você também precisará baixar o conjunto de dados [train.csv](https://www.kaggle.com/search?q=fake+news) e colocá-lo na mesma pasta do código.
```
## Instalação

1. Clone o repositório:
   ```
   git clone [https://github.com/seu-usuario/nome-do-repositorio.git]
   ```


## Como usar

1. Abra o arquivo `fake_news_classifier.ipynb` em um ambiente Jupyter Notebook ou execute o código Python diretamente no seu editor de escolha.

2. Execute cada célula sequencialmente para carregar os dados, pré-processar as notícias, treinar o modelo e fazer previsões.

3. No trecho de código final, você pode definir uma notícia de exemplo na variável `noticia` para verificar se ela é falsa ou verdadeira.

## Explicação do código

O código está dividido em várias células, cada uma realizando uma etapa específica do processo. Abaixo, você encontrará uma explicação de cada etapa:

1. Importação das bibliotecas necessárias:
   - pandas: para trabalhar com os dados em formato de tabela.
   - numpy: para operações numéricas.
   - nltk: para processamento de linguagem natural.
   - scikit-learn: para treinar o modelo de classificação.

2. Download das stopwords do nltk:
   - As stopwords são palavras comuns que geralmente não contribuem para a classificação de textos. Elas são removidas durante o pré-processamento.
   
3. Carregamento do conjunto de dados:
   - Os dados estão armazenados em um arquivo CSV que contém colunas como "title", "author", "text" e "label".
   
4. Remoção de valores nulos:
   - Os valores nulos são removidos do conjunto de dados para garantir a integridade dos dados.

5. Concatenação das colunas:
   - As colunas "title", "author" e "text" são concatenadas em uma única coluna chamada "all". Isso ajuda a ter um único texto para análise.

6. Definição da função de stemming:
   - A função `stemming_tokenizer` aplica o processo de stemming para trazer as palavras para sua forma raiz. Isso ajuda a reduzir a dimensionalidade dos dados e normalizar as palavras.

7. Pré-processamento das notícias:
   - A função de stemming é aplicada a cada texto na coluna "all" para pré-processar as notícias.

8. Separação em features e labels:
   - As features são extraídas da coluna pré-processada "features", que contém o texto processado.
   - As labels são extraídas da coluna "label", que representa a veracidade

 das notícias (1 para fake e 0 para real).

9. Conversão do texto em representação numérica:
   - O vetorizador TF-IDF é usado para converter o texto em uma representação numérica.
   - O conjunto de treinamento é ajustado ao vetorizador e transformado em representação numérica.
   - O conjunto de teste também é transformado com base no ajuste do conjunto de treinamento.

10. Treinamento do modelo:
    - Um modelo de Regressão Logística é criado e treinado com as features e labels do conjunto de treinamento.

11. Previsão e avaliação do modelo:
    - O modelo é usado para fazer previsões no conjunto de teste.
    - A acurácia é calculada comparando as previsões com as labels reais.

12. Previsão de uma notícia de exemplo:
    - Uma notícia de exemplo é pré-processada e convertida em representação numérica usando o vetorizador.
    - A previsão do modelo é obtida para a notícia de exemplo.
    - Com base na probabilidade da classe falsa, é determinado se a notícia é falsa ou verdadeira.

# Contribua
Sinta-se à vontade para modificar o código e experimentar diferentes técnicas de pré-processamento, algoritmos de classificação e métricas de avaliação.
