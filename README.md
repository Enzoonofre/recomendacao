# Projeto de Recomendação de Imagens

Este projeto tem como objetivo desenvolver um sistema de recomendação de imagens baseado em similaridade. Utilizando técnicas de aprendizado profundo (deep learning), o sistema é capaz de analisar uma imagem de entrada, prever sua classe e buscar imagens similares na internet. O projeto foi desenvolvido em Python, com o uso de bibliotecas como TensorFlow, Keras e Scikit-learn.

## Descrição do Projeto

O sistema funciona em três etapas principais:

1. **Pré-processamento e Treinamento do Modelo**:
   - O dataset utilizado é o **Furniture Image Dataset**, que contém imagens de diferentes tipos de móveis.
   - O modelo de rede neural é baseado na arquitetura **MobileNetV2**, pré-treinada no ImageNet, e ajustada para o problema específico de classificação de móveis.
   - O modelo é treinado para classificar imagens em 4 classes: cadeira, geladeira, mesa e TV.

2. **Predição e Extração de Características**:
   - Após o treinamento, o modelo é capaz de prever a classe de uma nova imagem.
   - Além disso, o sistema extrai características da imagem utilizando a penúltima camada do modelo, gerando um vetor de características que representa a imagem.

3. **Busca e Recomendação de Imagens Similares**:
   - Com base na classe predita, o sistema realiza uma busca na internet por imagens relacionadas.
   - As imagens encontradas são processadas e comparadas com a imagem de entrada utilizando a similaridade de cosseno entre os vetores de características.
   - As imagens mais similares são exibidas ao usuário.

## Dificuldades Encontradas

Uma das principais dificuldades do projeto foi a etapa de **mineração de dados**, especialmente na busca e processamento de imagens na internet. Como essa é uma área com a qual eu não tinha tanto contato, foi necessário aprender e implementar técnicas para:

- Realizar buscas eficientes de imagens na web.
- Processar e normalizar as imagens baixadas.
- Lidar com exceções e erros durante o download e processamento das imagens.

Além disso, a extração e comparação de características das imagens exigiu um bom entendimento de como os modelos de deep learning representam visualmente as informações, o que também foi um desafio.

## Como Executar o Projeto

### Pré-requisitos

- Python 3.x
- Bibliotecas necessárias: TensorFlow, Keras, NumPy, Scikit-learn, Requests, BeautifulSoup, Pillow, Matplotlib.

### Instalação

1. Clone o repositório:
   ```bash
   git clone https://github.com/Enzoonofre/recomendacao.git
   cd recomendacao
   ```

2. Instale as dependências:
   ```bash
   pip install -r requirements.txt
   ```

3. Baixe o dataset do Kaggle:
   - Crie uma conta no Kaggle e obtenha o arquivo da chave API `kaggle.json`.
   - Execute o notebook ou script para fazer o download do dataset.

### Execução

1. Execute o notebook `Recomendacao.ipynb` no Google Colab ou em um ambiente local com Jupyter Notebook.
2. Siga as instruções no notebook para:
   - Fazer o upload do arquivo `kaggle.json`.
   - Baixar e extrair o dataset.
   - Treinar o modelo.
   - Realizar predições e buscar imagens similares.

## Exemplos de Uso

### Predição de Classe e Similaridade

Para prever a classe de uma imagem e buscar imagens similares, utilize a função `find_similar_images`:

```python
image_path = "/content/cadeira.jpg"
find_similar_images(image_path)
```

### Extração de Características

Para extrair características de uma imagem:

```python
vector = extract_features("/content/cadeira.jpg")
print(vector)
```

### Cálculo de Similaridade

Para calcular a similaridade entre duas imagens:

```python
vector1 = extract_features("/content/cadeira.jpg")
vector2 = extract_features("/content/cadeira2.jpg")
similarity = 1 - cosine(vector1, vector2)
print(f"Similaridade: {similarity:.4f}")
```

## Resultados

O sistema foi capaz de classificar imagens com uma precisão de aproximadamente **90%** e recomendar imagens similares com base na similaridade de cosseno. A etapa de mineração de dados, apesar dos desafios, mostrou-se eficaz na busca e processamento de imagens na web.

## Melhorias Futuras

- **Expansão do Dataset**: Incluir mais classes de móveis para melhorar a capacidade de classificação do modelo.
- **Otimização da Busca**: Implementar técnicas mais avançadas de busca e filtragem de imagens na internet.
- **Interface Gráfica**: Desenvolver uma interface gráfica para facilitar o uso do sistema por usuários finais.

## Contribuição

Contribuições são bem-vindas! Sinta-se à vontade para abrir issues e pull requests.

## Licença

Este projeto está licenciado sob a licença MIT.
---

**Autor**: Enzo Onofre  
**Contato**: enzo.onofre@ufu.br  
**Repositório**: [https://github.com/Enzoonofre/recomendacao](https://github.com/Enzoonofre/recomendacao)
