## Título

Combinando Redes Neurais Convolucionais e Recorrentes para a Classificação de Doenças Pulmonares em Vídeos de Ultrassom

## Resumo

Aprendizado profundo é uma técnica importante para a construção de aplicativos de diagnóstico auxiliado por computador. Este trabalho apresenta um método computacional para classificar vídeos de ultrassom pulmonar capturados por transdutores convexos para auxiliar no diagnóstico da COVID-19. Redes neurais convolucionais foram utilizadas para extração das características espaciais e a dependência temporal foi aprendida por uma rede neural recorrente do tipo *long short-term memory*. Diferentes tipos de arquiteturas de redes neurais convolucionais foram testadas para extração de características. Os hiperparâmetros foram otimizados utilizando o *framework* Optuna. A extração de características utilizando transferência de aprendizado com redes pré-treinadas no conjunto de dados ImageNet apresentou resultados comparáveis às redes pré-treinadas em imagens de ultrassom pulmonar de outros trabalhos. Os resultados foram comparados com outros estudos, mostrando que o aprendizado profundo e o ultrassom pulmonar podem auxiliar no diagnóstico da COVID-19 e de outras doenças pulmonares. O melhor classificador apresentou uma acurácia média de 95%, precisão de 94,44%, sensibilidade de 100%, especificidade de 95,65%, e F1-Score de 96,77% para o diagnóstico de COVID-19 em uma validação cruzada com cinco partições, superando classificadores baseados em abordagens puramente espaciais.

## Palavras-chave

Aprendizado Profundo, CNN, COVID-19, LSTM, Otimização de Hiperparâmetros, RNN, Ultrassom Pulmonar.

### Conjunto de dados

O conjunto de dados de ultrassom pulmonar pode ser acessado em: [covid19_ultrasound](https://github.com/jannisborn/covid19_ultrasound/tree/9e254a140b4faa2c200b8bb5cee2347b7198fbef)

Será necessário clonar o repositório git fornecido acima e seguir as etapas descritas em: [README](https://github.com/jannisborn/covid19_ultrasound/blob/9e254a140b4faa2c200b8bb5cee2347b7198fbef/data/README.md).

As etapas descrita no documento acima também contemplam o pré-processamento dos dados.

### Características espaciais

Todos as características extraídas pelas diferentes arquiteturas de CNNs utilizadas neste trabalho estão disponíveis para *download* em: [dados/caracteristicas-espaciais](https://drive.google.com/drive/folders/1XDb1-Iq6bj12Nrj5EFT6Q0p8hgcce_mO?usp=sharing).

### Classificadores

O classificador (Xception-LSTM) configuração 4 (20 *frames*) proposto por este trabalho está disponível para *download* no formato h5 em: [dados/classificadores](https://drive.google.com/drive/folders/1XDb1-Iq6bj12Nrj5EFT6Q0p8hgcce_mO?usp=sharing).

### Otimização de hiperparâmetros

O banco de dados contendo os resultados do processo de otimização de todos os classificadores está disponível para *download* em: [dados/optuna](https://drive.google.com/drive/folders/1XDb1-Iq6bj12Nrj5EFT6Q0p8hgcce_mO?usp=sharing)

Para ver os resultados, você precisa instalar a biblioteca `optuna-dashboard` para `Python 3`.

    $ pip install optuna-dashboard==2.6.0
    $ optuna-dashboard sqlite:///optuna.db # you must have previously downloaded the file.
    
Visite a url [http://127.0.0.1:8080/](http://127.0.0.1:8080/) para visualizar o *dashboard*.

### Jupyter notebook

Para usar o notebook é necessário instalar algumas dependências para `Python 3`.

    $ pip install jupyter numpy sklearn tensorflow==2.4.1

Para rodar o classificador e extrair os resultados use o notebook: [xception-lstm.ipynb](xception-lstm.ipynb).

### Evaluation

O arquivo [resultados.csv](resultados.csv) contém os resultados numéricos para cada um dos classificadores. Adicionamente, foi fornecida uma versão gráfica (*box plot*) para cada uma das classes de diagnóstico e um para a acurácia em: [imagens](imagens).


### Sumário dos modelos

O sumário dos modelos e o tamanho (em MB) foram salvos nos arquivos disponibilizados no diretório: [parametros](parametros).