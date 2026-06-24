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

