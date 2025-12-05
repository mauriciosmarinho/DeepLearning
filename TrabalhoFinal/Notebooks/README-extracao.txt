📓 Notebook Para Extração Offline de Dados das Sentenças do TJMA

Este notebook inclui:

	- Configuração - importação das bibliotecas necessárias (os, re, csv do bs4 e BeautifulSoup)
	- Função de parse html - extrai os campos estruturados
	- Execução em lote - execução sobre documentos html em uma pasta

🎯 Como usar:

	1 - Crie uma pasta (ex.: ./sentencas_html/) e coloque todos os seus .html lá.
	2 - Abra o notebook e ajuste:
		PASTA = "./sentencas_html"
		SAIDA_CSV = "resultado_tjma_v2.csv"
	3 - Execute as células em ordem. Ao final, você terá o CSV com todas as colunas.

⚠️ COMO O PARSER DECIDE CADA CAMPO (RESUMO TÉCNICO):

	- Magistrado(a) e assinatura: procura “Assinado eletronicamente por:” e captura o nome; em seguida, extrai data/hora e ID do documento nas proximidades.
	- Vara / Comarca: usa o cabeçalho da página (“1ª VARA DE SANTA INÊS/MA”) ou, em fallback, a linha “Juíza de Direito — Titular da 1ª Vara da Comarca de Santa Inês/MA”.
	- Gênero & cargo: busca marcadores explícitos na janela ao redor da assinatura (±400 caracteres). Se houver “Juíza/Desembargadora” → Feminino; “Juiz/Desembargador” → Masculino; sem marcador → Indeterminado.
	- Decisão: pega a primeira linha que contém “julgo” (funciona mesmo sem ponto final) e classifica; se não houver, aplica padrões alternativos (ex.: REJEITO A INICIAL, EXTINGO …).
	- Nº do processo: procura “PROCESSO Nº” (variações com “Nº”, “No”, “N°” etc.).
