# Chatbot LLM Offline para Raspberry Pi

Este projeto executa um chatbot LLM local usando um modelo quantizado (GGUF) via `llama.cpp`, com interface de terminal e web.

## 🔧 Requisitos

- Raspberry Pi 5 com Raspberry Pi OS 64-bit
- Python 3.11+
- 8GB de RAM
- Acesso à internet para instalação inicial

## 📦 Instalação

```bash
sudo apt update && sudo apt install -y build-essential cmake python3-dev python3-venv git
git clone https://github.com/seu-usuario/chatbot-llm-pi.git
cd chatbot-llm-pi
python3 -m venv .venv
source .venv/bin/activate
pip install -U pip
pip install fastapi uvicorn jinja2 llama-cpp-python

# Compilar llama.cpp
git clone https://github.com/ggerganov/llama.cpp.git
cd llama.cpp && make && cd ..

# Baixar modelo (exemplo Mistral Q4_K)
mkdir -p model && cd model
wget https://huggingface.co/TheBloke/Mistral-7B-Instruct-v0.1-GGUF/resolve/main/mistral-7b-instruct-v0.1.Q4_K_M.gguf
cd ..
```

## 🚀 Uso

### Terminal

```bash
python app/cli.py
```

### Interface Web

```bash
./start.sh
# Acesse via http://<ip-do-raspberry>:8000
```

## 📁 Estrutura

```
chatbot-llm-pi/
├── app/
│   ├── main.py
│   ├── cli.py
│   ├── llama_runner.py
│   └── templates/
│       └── index.html
├── model/
├── llama.cpp/
├── start.sh
└── README.md
```
