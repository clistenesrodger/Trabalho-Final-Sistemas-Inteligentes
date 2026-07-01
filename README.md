# Objetivo do projeto

O projeto é uma comparação entre três modelos de redes neurais convolucionais:

- ResNet50
- DenseNet121
- ConvNeXtV2


# Processo de instalação de dependências

## 1. Criar o ambiente virtual

No diretório do projeto, crie o ambiente virtual com:

```bash
python3 -m venv .venv
```

## 2. Ativar o ambiente virtual

No Linux e MacOs, ative o ambiente com:

```bash
source .venv/bin/activate
```

No Windows, use:

```powershell
.venv\Scripts\activate
```

## 3. Instalar as dependências

Com o ambiente virtual ativado, instale os pacotes do arquivo `requirements.txt`:

```bash
pip install -r requirements.txt
```

Se quiser confirmar a instalação, você pode listar os pacotes com:

```bash
pip list
```
## 4. Execução no Google Colab

Este projeto também pode ser executado no Google Colab, que roda diretamente no navegador.
Você também pode abrir o projeto diretamente pelo navegador em `https://colab.research.google.com/` e executar o notebook por lá. E ative a GPU em `Ambiente de execução > Alterar tipo de ambiente de execução`.
Você também pode instalar Extensão Google Colab pelo próprio visual studio code. Para selecionar o ambiente do colab pelo visual studio: ` Select Kerkel > Select Another Kernel > Colab > New Colab Server > GPU > T4 > Latest > Clicar na tecla Enter > Python 3 (ipykernel) `

## 5. Salvamento dos Dados

A estrutura de salvamento dos arquivos será organizada da seguinte forma:

```text
.
├── models/
│   ├── ResNet50/
│   ├── DenseNet121/
│   └── ConvNeXtV2/
└── resultados/
    ├── ResNet50/
    ├── DenseNet121/
    └── ConvNeXtV2/
```

## Referências

- Link do dataset: https://www.kaggle.com/datasets/mahyeks/almond-varieties
- Link do artigo de base de estudo: https://link.springer.com/article/10.1007/s00217-024-04562-4
- Link do artigo desse estudo: https://prism.openai.com/?u=054a9dd6-7a70-4e21-b33f-7a19193863ea&pg=1&m=main.tex&d=7