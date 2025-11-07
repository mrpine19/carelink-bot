# CareLink Bot

## Descrição

Sistema de assistente virtual para hospital, composto por dois bots
especializados:

### **CareLink Bot**

-   Atendimento a pacientes (especialmente idosos com baixa afinidade
    digital)\
-   Responde perguntas sobre agendamentos, consultas e informações do
    hospital\
-   Busca semântica no manual do paciente

### **Database Bot**

-   Assistente para funcionários do hospital\
-   Consulta banco de dados Oracle para relatórios e informações\
-   Geração automática de queries SQL via IA

------------------------------------------------------------------------

## Estrutura do Projeto

    carelink-bot/
    ├── src/
    │   ├── api.py                 # API para funcionários
    │   
    │   ├── main.py                # Teste do bot paciente
    │   └── main_funcionario.py    # Teste do bot funcionário
        ├── bots/
        │   ├── carelink_bot.py        # Bot para pacientes
        │   └── database_bot.py        # Bot para funcionários
        ├── services/
        │   ├── gemini_client.py       # Cliente Gemini AI
        │   ├── oracle_connector.py    # Conexão com banco Oracle
        │   ├── query_generator.py     # Geração de queries SQL
        │   ├── pdf_processor.py       # Processamento de PDF
        │   └── appointment_manager.py # Gerenciamento de consultas
        ├── utils/
        │   ├── semantic_searcher.py   # Busca semântica
        │   ├── prompts.py             # Prompts para IA
        │   ├── my_models.py           # Modelos de IA
        │   └── my_helper.py           # Utilitários
        └── config/
            ├── my_keys.py             # Configurações e chaves
            └── config_prod.py         # Configurações produção

------------------------------------------------------------------------

## Requisitos

-   Python 3.11+\
-   Banco de dados Oracle\
-   API Key do Google Gemini

------------------------------------------------------------------------

## Instalação

``` bash
pip install -r requirements.txt
```

------------------------------------------------------------------------

## Configuração

Crie um arquivo `.env` com:

    DB_USER=seu_usuario
    DB_PASSWORD=sua_senha
    DB_HOST=oracle.fiap.com.br
    DB_PORT=1521
    DB_SID=ORCL
    GEMINI_API_KEY=sua_chave_gemini

Coloque o manual do paciente em:

    src/data/manuals/

------------------------------------------------------------------------

## Uso

### ✅ API Funcionários

``` bash
cd src
python api.py
```

**Endpoint:** `POST /api/staff-chat`\
Exemplo:

``` json
{
  "message": "Quantos pacientes temos no sistema?",
  "user_id": "func_001"
}
```

### ✅ API Pacientes

``` bash
cd src
(n tem)
```

**Endpoint:** `POST /perguntar`\
Exemplo:

``` json
{
  "pergunta": "Como agendar uma consulta?"
}
```

------------------------------------------------------------------------

## Funcionalidades

### Para Pacientes

-   Agendamento de consultas\
-   Informações sobre procedimentos\
-   Suporte ao manual do paciente\
-   Linguagem simplificada para idosos

### Para Funcionários

-   Consultas ao banco Oracle\
-   Relatórios automáticos\
-   Estatísticas do hospital\
-   Geração de queries SQL via IA

------------------------------------------------------------------------

## Tecnologias

-   Flask\
-   Oracle Database\
-   Google Gemini AI\
-   Sentence Transformers (busca semântica)\
-   LangChain

------------------------------------------------------------------------

## Desenvolvimento

``` bash
python src/main.py             # Teste bot paciente
python src/main_funcionario.py # Teste bot funcionário
python src/api.py              # Gera endpoin q está conectado no front-end
```

------------------------------------------------------------------------

## Licença

Projeto acadêmico - FIAP
