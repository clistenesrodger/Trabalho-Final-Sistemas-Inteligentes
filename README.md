# Classificação de Variedades de Amêndoa com Redes Neurais Convolucionais

Estudo comparativo de três arquiteturas de redes neurais convolucionais aplicadas à classificação de variedades de amêndoa a partir de imagens. O projeto avalia o desempenho de **ResNet50**, **DenseNet121** e **ConvNeXtV2** utilizando as mesmas condições de treinamento e o mesmo conjunto de dados, com métricas consistentes para permitir comparação direta entre os modelos.

---

## Índice

- [Visão geral](#visão-geral)
- [Dataset](#dataset)
- [Modelos comparados](#modelos-comparados)
- [Estrutura do projeto](#estrutura-do-projeto)
- [Instalação e execução](#instalação-e-execução)
- [Execução no Google Colab](#execução-no-google-colab)
- [Referências](#referências)

---

## Visão geral

A tarefa consiste em classificar imagens de amêndoas em suas respectivas variedades. Cada arquitetura passa pelo mesmo pipeline de treinamento, que inclui:

- Pré-processamento e aumento de dados (data augmentation)
- Fine-tuning com backbone pré-treinado no ImageNet
- Avaliação com Accuracy, Precision, Recall, F1-Score, Kappa e AUC-ROC

Os resultados são salvos por modelo para facilitar a comparação posterior.

---

## Dataset

O dataset utilizado é o **Almond Varieties**, disponível publicamente no Kaggle.

- **Link:** [https://www.kaggle.com/datasets/mahyeks/almond-varieties](https://www.kaggle.com/datasets/mahyeks/almond-varieties)

Após baixar, extraia o conteúdo na raiz do projeto antes de executar os notebooks.

---

## Modelos comparados

| Modelo        | Família          | Parâmetros (aprox.) |
|---------------|------------------|---------------------|
| ResNet50      | ResNet           | 25 M                |
| DenseNet121   | DenseNet         | 8 M                 |
| ConvNeXtV2    | ConvNeXt V2      | 28 M                |

Todos os modelos são carregados com pesos pré-treinados no ImageNet via `timm` e passam por fine-tuning supervisionado no dataset de amêndoas.

---

## Estrutura do projeto

```text
.
├── models/
│   ├── ResNet50/
│   ├── DenseNet121/
│   └── ConvNeXtV2/
├── resultados/
│   ├── ResNet50/
│   ├── DenseNet121/
│   └── ConvNeXtV2/
├── requirements.txt
├── Treinamento-Modelos.ipynb
└── README.md
```

As pastas `models/` e `resultados/` são criadas automaticamente durante o treinamento. Cada subpasta de modelo armazena os pesos do melhor checkpoint (`.pth`) e os arquivos de métricas (`.json`, `.npy`).

---

## Instalação e execução

### 1. Pré-requisitos

- Python 3.10 ou superior
- GPU com CUDA (recomendado) — ou CPU para testes rápidos

### 2. Criar o ambiente virtual

```bash
python3 -m venv .venv
```

### 3. Ativar o ambiente virtual

**Linux / macOS:**

```bash
source .venv/bin/activate
```

**Windows:**

```powershell
.venv\Scripts\activate
```

### 4. Instalar as dependências

```bash
pip install -r requirements.txt
```

Para confirmar que os pacotes foram instalados corretamente:

```bash
pip list
```

### 5. Executar o notebook

Abra o notebook com Jupyter ou VS Code e execute as células em ordem.

---

## Execução no Google Colab

O projeto é compatível com o [Google Colab](https://colab.research.google.com/), sem necessidade de instalação local.

**Passos:**

1. Abra o Colab e faça upload do notebook desejado (ou abra direto do Google Drive).
2. Ative a GPU em: `Ambiente de execução > Alterar tipo de ambiente de execução > T4 GPU`.
3. Execute a célula de instalação de dependências no início do notebook.

**Via extensão do VS Code:**

Se preferir usar o Colab pelo VS Code, instale a extensão **Google Colab** e siga:

```
Select Kernel > Select Another Kernel > Colab > New Colab Server > GPU > T4 > Latest > Python 3 (ipykernel)
```

---

## Referências

- **Dataset:** [Almond Varieties — Kaggle](https://www.kaggle.com/datasets/mahyeks/almond-varieties)
- **Artigo de base:** [Springer — Food quality evaluation with deep learning](https://link.springer.com/article/10.1007/s00217-024-04562-4)
- **Artigo deste estudo:** [Manuscrito no PRISM](https://prism.openai.com/?u=054a9dd6-7a70-4e21-b33f-7a19193863ea&pg=1&m=main.tex&d=7)