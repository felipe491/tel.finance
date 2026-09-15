# tel.finance
Pipeline em Python para extração de dados de comprovantes (OCR), consolidação estruturada em Excel e alimentação de Dashboard Financeiro em Power BI.
📊 Financial OCR Pipeline & Dashboard Automation

📌 Visão Geral do Projeto
Projeto desenvolvido para resolver o gargalo de digitação manual de comprovantes de pagamento e recebimento no controle financeiro. A solução utiliza um bot no Telegram integrado a um motor de OCR (Optical Character Recognition) para ler imagens de comprovantes, extrair os dados estruturados via Python e alimentar uma base de dados que suporta um dashboard analítico no Power BI.

🛠️ Tecnologias Utilizadas
Linguagem:** Python 3.x
Extracão de Texto (OCR):** Tesseract OCR, `pytesseract`, `OpenCV` (Pré-processamento de imagem)
Interface de Entrada:** API Telegram (`python-telegram-bot`)
Tratamento e Estruturação de Dados:** `pandas`, `re` (Regular Expressions)
Armazenamento de Dados:** Excel (`openpyxl` / `gspread`)
Visualização & BI:Power BI (Dashboards interativos e KPIs)

⚙️ Arquitetura da Solução
1. Captura: O usuário envia a foto ou PDF do comprovante via Telegram.
2. Processamento: O script em Python aplica filtros de imagem (escala de cinza e limiarização com OpenCV) para otimizar o OCR.
3. Parsing:** O `pytesseract` extrai o texto bruto e expressões regulares (`Regex`) filtram:
   Valor ($R\$$)
   Data da transação
   Tipo (Pagamento / Recebimento)
   Beneficiário / Pagador
4. Armazenamento: Os dados são tratados com `pandas` e appendados automaticamente na planilha-base.
5. BI & Analytics: O Power BI atualiza os dados para exibir métricas de fluxo de caixa, gastos por categoria e análise de ticket médio.

📈 KPIs Analisados no Dashboard
Fluxo de Caixa Líquido (Entradas vs. Saídas)
Distribuição de Gastos por Categoria
Evolução Mensal do Faturamento / Despesas
Ticket Médio por Transação
