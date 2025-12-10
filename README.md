# ReconhecimentoFacial_Colab
Projeto de reconhecimento facial usando ResNet50 e OpenCV no Colab
# 🎭 Reconhecimento Facial em Grupo (FaceNet)

Este projeto demonstra um pipeline de Visão Computacional para detecção e reconhecimento facial em imagens de grupo. O desafio inicial envolveu a resolução de problemas de compatibilidade de bibliotecas e calibração de modelos, resultando na implementação de uma solução robusta utilizando a arquitetura FaceNet para extração de *embeddings*.

## ✨ Destaques do Projeto

* **Detecção Facial:** Utiliza o modelo MTCNN (Multi-task Cascaded Convolutional Networks), otimizado para encontrar rostos em diferentes ângulos e tamanhos, superando as limitações do detector Caffe/OpenCV em ambientes de grupo.
* **Extração de Características (Embedding):** Emprega a arquitetura **FaceNet** (InceptionResnetV1 pré-treinado em VGG-Face2). Esta transição foi crucial para resolver um problema de viés de classificação de gênero observado com o ResNet50 genérico.
* **Reconhecimento:** Utiliza a Distância Euclidiana para comparar os *embeddings* de rostos detectados com um banco de dados de referência, com um limiar de reconhecimento rigoroso.

## ⚙️ Tecnologias e Dependências

O projeto é desenvolvido em um ambiente Google Colab/Jupyter Notebook.

* **Linguagem:** Python
* **Frameworks:** PyTorch, TensorFlow
* **Bibliotecas Principais:** `facenet-pytorch`, `opencv-python`, `numpy`, `scikit-learn`.

## 🚀 Como Executar o Projeto (No Google Colab)

Para replicar os resultados, siga os passos abaixo em ordem:

### 1. Preparação

1.  **Clone o Repositório:** Faça um clone deste repositório ou baixe o arquivo `reconhecimento_facial_resnet.ipynb`.
2.  **Faça Upload das Imagens:** Certifique-se de que os seguintes arquivos estejam no mesmo diretório do notebook no Colab:
    * `a.jpg` (Referência Masculina)
    * `m1.jpg` (Referência Feminina)
    * `img25.jpg` (Imagem de teste de grupo)

### 2. Execução das Células

Abra o notebook no Google Colab e execute as células sequencialmente:

| Célula | Objetivo | Ação |
| :--- | :--- | :--- |
| **Célula 1** | Instalação e Carregamento do FaceNet/MTCNN | Instala as bibliotecas `facenet-pytorch` e carrega os modelos `MTCNN` e `InceptionResnetV1`. |
| **Célula 2** | Criação do Banco de Dados | Gera os *embeddings* de referência para "Homem" (`a.jpg`) e "Mulher" (`m1.jpg`). |
| **Célula 3** | Reconhecimento e Visualização | Carrega a imagem `img25.jpg`, detecta rostos, calcula a distância e exibe o resultado com caixas delimitadoras e rótulos. |

## 📐 Calibração e Limiar de Reconhecimento

O projeto utiliza o modelo FaceNet, que gera *embeddings* em um espaço de distância muito compacto.

| Parâmetro | Valor | Descrição |
| :--- | :--- | :--- |
| `RECOGNITION_THRESHOLD` | **1.0** | Limiar de distância Euclidiana. Distâncias abaixo de 1.0 indicam alta confiança no reconhecimento de identidade. |

---

## 👨‍💻 Autor

Rolando Ferrão (Atrodeon)
