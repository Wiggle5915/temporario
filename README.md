# requirements.txt
streamlit>=1.28.0
langchain>=0.1.0
langchain-experimental>=0.0.50
langchain-openai>=0.0.8
openai>=1.3.0
pandas>=2.0.0
python-dotenv>=1.0.0
tabulate>=0.9.0
openpyxl>=3.1.0

# Instalação e Execução

## 1. Preparação do Ambiente

```bash
# Criar ambiente virtual
python -m venv venv

# Ativar ambiente (Windows)
venv\Scripts\activate

# Ativar ambiente (Linux/Mac)
source venv/bin/activate

# Instalar dependências
pip install -r requirements.txt
```

## 2. Configuração da API Key

### Opção A: Variável de Ambiente
```bash
# Windows
set OPENAI_API_KEY=sua_chave_aqui

# Linux/Mac
export OPENAI_API_KEY=sua_chave_aqui
```

### Opção B: Arquivo .env
Crie um arquivo `.env` na raiz do projeto:
```
OPENAI_API_KEY=sua_chave_aqui
```

## 3. Execução

### Interface Web (Streamlit) - RECOMENDADO
```bash
streamlit run nf_analyzer_agent.py
```

### Modo Console
```bash
python nf_analyzer_agent.py
```

## 4. Uso

1. **Via Interface Web:**
   - Acesse http://localhost:8501
   - Insira sua OpenAI API Key
   - Faça upload do arquivo 202401_NFs.zip
   - Faça suas perguntas!

2. **Via Console:**
   - Digite sua API Key quando solicitado
   - Informe o caminho para o arquivo ZIP
   - Digite suas perguntas

## 5. Exemplos de Perguntas

- "Qual fornecedor teve maior montante recebido?"
- "Qual item teve maior volume entregue em quantidade?"
- "Qual o valor médio das notas fiscais?"
- "Quantas notas fiscais foram emitidas?"
- "Quais são os 5 produtos mais vendidos?"
- "Qual o valor total faturado no período?"
- "Qual fornecedor tem mais notas fiscais?"

## 6. Estrutura do Projeto

```
projeto/
├── nf_analyzer_agent.py    # Código principal
├── requirements.txt        # Dependências
├── .env                   # API Keys (opcional)
└── README.md              # Este arquivo
```

## 7. Troubleshooting

### Erro de API Key
- Verifique se a chave está correta
- Certifique-se de ter créditos na conta OpenAI

### Erro de Upload
- Verifique se o arquivo ZIP contém os CSVs corretos
- Nomes esperados: *Cabecalho*.csv e *Itens*.csv

### Erro de Dependências
```bash
pip install --upgrade pip
pip install -r requirements.txt --force-reinstall
```

## 8. Personalização

Para adaptar para outros tipos de CSV:
1. Modifique a função `extract_zip_files()` para seus nomes de arquivo
2. Ajuste o `prefix` do agente com contexto específico
3. Customize os exemplos de perguntas na interface
