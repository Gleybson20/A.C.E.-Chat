
# 🤖 Chatbot A.C.E. Consultoria

## 📌 Visão Geral
Este projeto é um chatbot híbrido da **A.C.E. Consultoria**, criado para fornecer respostas rápidas sobre a empresa e suas operações. O chatbot consulta uma base de conhecimento em formato JSON, mas também pode recorrer à Inteligência Artificial (IA) da OpenAI para respostas mais complexas ou não cadastradas. O projeto pode ser utilizado tanto via **terminal** (CLI) quanto através de uma **API FastAPI**, permitindo a integração com sistemas externos.

## ✨ Principais Características:
✔ **Base de Conhecimento Local**: O chatbot primeiro tenta encontrar uma resposta no arquivo `knowledge_base.json`.  
✔ **Integração com OpenAI**: Se a pergunta não for encontrada, o chatbot consulta a IA da OpenAI para gerar uma resposta.  
✔ **Armazenamento de Respostas**: As respostas geradas pela IA podem ser salvas no arquivo JSON para futuras consultas.  
✔ **Interação Flexível**: Disponível tanto por **API** quanto **CLI**, proporcionando flexibilidade na interação.  
✔ **Logs de Interações**: O chatbot registra interações e erros para facilitar a análise de desempenho.  
✔ **Testes Automatizados**: Inclui testes unitários para garantir que as funcionalidades funcionem corretamente.

## 🎯 Funcionalidades do Projeto
✔ **Consulta Inteligente**: O chatbot verifica se a pergunta está na base de dados local antes de recorrer à IA.  
✔ **Resposta via OpenAI**: Se a pergunta não estiver cadastrada, o chatbot usa a IA da OpenAI para gerar uma resposta.  
✔ **Armazenamento Automático de Novas Perguntas**: Se a resposta for gerada pela IA, ela pode ser salva no `knowledge_base.json` para futuras consultas.  
✔ **Interface Dupla**: Permite interação via **terminal** (CLI) ou **API HTTP**, permitindo integração com sistemas externos.  
✔ **Registros de Logs**: Mantém registros das interações do chatbot para monitoramento e melhorias.  
✔ **Testes Automatizados**: Testes para garantir que o sistema de respostas e a API estão funcionando corretamente.

## 🛠️ Tecnologias Utilizadas
| Tecnologia     | Descrição                                           |
|----------------|-----------------------------------------------------|
| **Python**     | Linguagem principal do projeto                      |
| **FastAPI**    | Framework para criação da API                       |
| **OpenAI API** | Integração com o GPT-4o para respostas automáticas  |
| **JSON**       | Armazenamento da base de conhecimento               |
| **Logging**    | Registro de interações e erros                      |
| **unittest**   | Testes automatizados para garantir a qualidade      |

## 📁 Estrutura do Projeto
```
📂 A.C.E.-Chat-main  
│── 📂 data/                   # Base de conhecimento  
│   ├── knowledge_base.json    # Arquivo JSON com perguntas e respostas  
│
│── 📂 src/                    # Código-fonte do chatbot  
│   ├── chatbot.py             # Lógica principal do chatbot  
│   ├── data_loader.py         # Manipulação do JSON de dados  
│   ├── interaction.py         # Interface de interação (CLI)  
│   ├── openai_client.py       # Integração com OpenAI  
│
│── app.py                     # API FastAPI para interagir com o chatbot  
│── requirements.txt            # Bibliotecas necessárias  
│── test_chatbot.py             # Testes do chatbot  
│── test_data_loader.py         # Testes da base de conhecimento  
│── README.md                   # Documentação do projeto  
```

## 📊 Fluxo de Funcionamento

### 🚀 Como Executar o Chatbot
**📌 1. Instalar Dependências**  
Antes de executar o chatbot, instale as bibliotecas necessárias:

```bash
pip install -r requirements.txt
```

**📌 2. Configurar a Chave da OpenAI**  
Crie um arquivo `.env` na raiz do projeto e adicione sua chave da OpenAI:

```
OPENAI_API_KEY="sua-chave-aqui"
```

**📌 3. Executar o Chatbot no Terminal**  
Execute o chatbot no terminal com o seguinte comando:

```bash
python src/interaction.py
```

Isso iniciará o chatbot no terminal. Digite uma pergunta e receba a resposta!

**📌 4. Executar a API**  
Para executar a API FastAPI, utilize o seguinte comando:

```bash
uvicorn app:app --reload
```

Isso iniciará a API FastAPI na porta 8000. Teste com o comando:

```bash
curl -X POST "http://127.0.0.1:8000/chat" -H "Content-Type: application/json" -d '{"question": "O que é a A.C.E. Consultoria?"}'
```

## 🛠️ Testes Automatizados
Para garantir que o chatbot está funcionando corretamente, execute os testes unitários com:

```bash
python -m unittest test_chatbot.py
```

Isso validará se:
✔ O chatbot responde corretamente perguntas cadastradas no JSON.  
✔ O chatbot retorna respostas válidas da OpenAI.  
✔ A API está funcionando corretamente.

## 📌 Conclusão
O **A.C.E.-Chat** combina uma base de conhecimento estruturada com a inteligência artificial da OpenAI, proporcionando uma solução eficiente para responder dúvidas sobre a A.C.E. Consultoria. Com flexibilidade de uso (via CLI ou API) e recursos de aprendizado contínuo, o chatbot está pronto para ser integrado em diversas plataformas e otimizar a comunicação com os usuários.
