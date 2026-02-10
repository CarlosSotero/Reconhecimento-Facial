# Detecção de Faces em Tempo Real com OpenCV DNN (Google Colab)

Este projeto implementa um **sistema de detecção de faces** utilizando um **modelo pré-treinado de Deep Learning** disponível no módulo **DNN do OpenCV**, executado no ambiente do **Google Colab** com captura de imagem via webcam.

O foco do projeto é demonstrar, de forma prática, como integrar **visão computacional clássica**, **redes neurais profundas** e **aplicações interativas em notebook**.

---

## 🎯 Objetivo

Detectar automaticamente **rostos humanos em imagens capturadas pela webcam**, desenhando **bounding boxes** e exibindo a **confiança da detecção** para cada face encontrada.

---

## 🧠 Modelo Utilizado

- Arquitetura: **Single Shot Detector (SSD)**
- Backbone: **ResNet-10**
- Framework original: **Caffe**
- Implementação: **OpenCV DNN**
- Entrada esperada: **300 × 300 pixels**
- Saída: Bounding boxes + score de confiança

Modelo amplamente utilizado por ser **leve, rápido e eficaz** para detecção de faces em tempo real.

---

## 📂 Estrutura do Projeto
├── deploy.prototxt

├── res10_300x300_ssd_iter_140000.caffemodel

├── notebook.ipynb

└── README.md

Os arquivos do modelo são baixados automaticamente no notebook.

---

## 🔄 Pipeline do Projeto

1. Importação das bibliotecas necessárias
2. Captura de imagem via webcam no Google Colab
3. Redimensionamento da imagem
4. Carregamento do modelo pré-treinado
5. Pré-processamento da imagem (blob)
6. Forward pass na rede neural
7. Filtragem das detecções por confiança
8. Desenho das bounding boxes e scores
9. Visualização do resultado final

---

## 📸 Captura de Imagem no Colab

Como o Google Colab não tem acesso direto à webcam via Python, o projeto utiliza:

- JavaScript injetado no notebook
- Captura da imagem no browser
- Retorno da imagem em **Base64**
- Decodificação e salvamento local

Isso permite criar aplicações interativas mesmo em ambiente web.

---

## ⚙️ Pré-processamento (Blob)

A imagem é convertida em um **blob**, que padroniza a entrada da rede:

- Redimensionamento para 300 × 300
- Normalização dos pixels
- Subtração da média por canal (BGR):
  - (104.0, 177.0, 123.0)

Esse pré-processamento deve ser consistente com o usado no treinamento do modelo.

---

## 🎚️ Parâmetros Importantes

- **Confidence Threshold**: `0.5`  
  Apenas detecções com confiança acima de 50% são consideradas.

- **Resolução de visualização**: largura de 400 px  
  Mantém bom equilíbrio entre qualidade e desempenho.

---

## 🖼️ Resultado

O sistema exibe:
- A imagem capturada
- Bounding boxes ao redor dos rostos detectados
- Porcentagem de confiança associada a cada detecção

---

## 🛠️ Tecnologias Utilizadas

- Python
- OpenCV
- OpenCV DNN
- NumPy
- imutils
- Google Colab
- JavaScript (integração com webcam)

---

## 📌 Observações

Este projeto tem caráter **educacional e demonstrativo**, com foco em:
- Entendimento de pipelines de detecção de objetos
- Uso de modelos pré-treinados
- Integração entre Python, OpenCV e ambientes web

É uma base sólida para evoluções como:
- Detecção em vídeo
- Rastreamento de faces
- Reconhecimento facial
- Deploy em aplicações reais

---

## 📜 Licença

Projeto desenvolvido para fins de estudo e portfólio.
