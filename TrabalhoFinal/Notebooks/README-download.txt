Elementos-chave:

Data/Hora:
Tipo:
URL: documentoSemLoginHTML.seam?ca=[token]&idProcessoDoc=161000320
O parâmetro ca é um token de acesso temporário

✅ Busca o processo
✅ Acessa os detalhes
✅ Identifica sentenças
✅ Baixa os documentos

✅ O que o notebook faz:
1. Busca o Processo

Acessa o PJe-TJMA
Preenche o número do processo
Encontra o link de detalhes

2. Extrai Documentos

Acessa a página de detalhes
Identifica TODOS os documentos na tabela
Classifica automaticamente: Sentenças, Decisões, Outros
Extrai URLs completas

3. Baixa Documentos

Baixa sentenças (ou todos documentos, você escolhe)
Salva em HTML
Organiza por pastas

4. Gera Metadados

CSV com todos os documentos
JSON completo
Relatórios de execução

📁 Estrutura de Arquivos Gerados:

sentencas_tjma/
├── pdfs/                   # Documentos baixados (HTML)
├── html/                   # HTMLs das páginas
├── metadados/              # CSVs e JSONs
    ├── [processo]_metadados.csv
    ├── [processo]_completo.json
    └── relatorio_[timestamp].csv

🚀 Como usar:
Célula 9 - Um processo (para testes):

NUMERO_PROCESSO = "0800151-71.2021.8.10.0056"
HEADLESS = False  # Ver o navegador
APENAS_SENTENCAS = True  # Só sentenças

Célula 10 - Múltiplos processos:

LISTA_PROCESSOS = [
    "0800151-71.2021.8.10.0056",
    "1234567-89.2023.8.10.0001",
    # ...
]

Célula 11 - Carregar de CSV:

Coloque seus números de processo em um CSV
O notebook lê e processa todos

📊 Features Especiais:
✅ Identifica automaticamente sentenças vs decisões
✅ Salva metadados completos
✅ Relatório de sucessos/falhas
✅ Intervalo entre requisições (respeita o servidor)
✅ Tratamento de erros robusto
✅ Screenshots em caso de erro
✅ Documentação para citação ABNT







