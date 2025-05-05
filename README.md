🧠 Chatbot LLM Offline para Raspberry Pi

Este projeto permite executar um chatbot com Modelos de Linguagem de Grande Escala (LLMs) diretamente em um Raspberry Pi 5, sem necessidade de conexão com a internet após a instalação.  Utiliza modelos quantizados no formato GGUF via llama.cpp, oferecendo interfaces tanto em terminal quanto web. 


---

🚀 Funcionalidades

✅ Execução local de modelos LLM quantizados (GGUF) com llama.cpp.

✅ Interfaces de uso via terminal e web (FastAPI + Jinja2).

✅ Compatível com modelos como Mistral, LLaMA, entre outros.

✅ Operação offline após configuração inicial.

✅ Ideal para dispositivos com recursos limitados, como o Raspberry Pi 5. 



---

🧰 Requisitos

Raspberry Pi 5 com Raspberry Pi OS 64-bit.

Python 3.11 ou superior.

Mínimo de 8GB de RAM.

Acesso à internet para a instalação inicial. 



---

⚙️ Instalação

1. Atualize o sistema e instale dependências:

sudo apt update && sudo apt install -y build-essential cmake python3-dev python3-venv git





2. Clone o repositório e configure o ambiente virtual:

git clone https://github.com/emeryinlover/srvllm.git
cd srvllm
python3 -m venv .venv
source .venv/bin/activate
pip install -U pip
pip install fastapi uvicorn jinja2 llama-cpp-python





3. Compile o llama.cpp:

git clone https://github.com/ggerganov/llama.cpp.git
cd llama.cpp && make && cd ..





4. Baixe um modelo quantizado (exemplo: Mistral Q4_K):

mkdir -p model && cd model
wget https://huggingface.co/TheBloke/Mistral-7B-Instruct-v0.1-GGUF/resolve/main/mistral-7b-instruct-v0.1.Q4_K_M.gguf
cd ..






---

🧪 Uso

Terminal

Execute o chatbot no terminal com: 

python app/cli.py



Interface Web

Inicie o servidor web com: 

./start.sh



Acesse via navegador em: http://<ip-do-raspberry>:8000 


---

📁 Estrutura do Projeto

srvllm/

├── app/
│
│ ──├── cli.py
│   │
│   ├── main.py
│   │
│   └── templates/
│   
├── model/
│   │
│   └── mistral-7b-instruct-v0.1.Q4_K_M.gguf
│   
├── llama.cpp/
│   
├── start.sh
│   
└── README.md





---

📌 Notas

Modelos quantizados no formato GGUF são otimizados para dispositivos com recursos limitados.

É possível utilizar outros modelos compatíveis com llama.cpp, como LLaMA 2, Falcon, entre outros.

Para desempenho ideal, recomenda-se o uso de um Raspberry Pi 5 com 8GB de RAM. 



---

🤝 Contribuições

Contribuições são bem-vindas! Sinta-se à vontade para abrir issues ou pull requests para melhorias, correções ou novas funcionalidades. 


---

📄 Licença

Este projeto está licenciado sob a MIT License. 


---

Para mais informações sobre llama.cpp e modelos quantizados, consulte os seguintes recursos: 

Repositório do llama.cpp: https://github.com/ggerganov/llama.cpp

Modelos quantizados GGUF no Hugging Face: https://huggingface.co/TheBloke 



---

Espero que este README.md atenda às suas expectativas e facilite o uso e compreensão do projeto srvllm!
