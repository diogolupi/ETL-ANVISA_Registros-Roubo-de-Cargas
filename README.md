# 📦 ETL - Roubos, Furtos e Extravios (ANVISA)

Este repositório contém um pipeline completo de **extração, tratamento, padronização e consolidação** de dados públicos da ANVISA relacionados a **roubos, furtos e extravios de produtos sujeitos à vigilância sanitária**.

## 🔗 Fonte dos Dados

- Portal ANVISA: [Roubos, Furtos e Extravios](https://www.gov.br/anvisa/pt-br/assuntos/fiscalizacao-e-monitoramento/roubos-furtos-e-extravios)

---

## 🧠 Visão Geral do Pipeline

O projeto é dividido em 4 etapas principais:

| Etapa | Descrição |
|-------|-----------|
| **Etapa 1** | Coleta automatizada dos arquivos (.pdf e .xlsx) a partir do portal da ANVISA |
| **Etapa 2** | Extração de tabelas dos arquivos PDF com `camelot`, `pdfplumber` e exportação para Excel |
| **Etapa 3** | Padronização dos arquivos tratados (.xlsx), limpeza de colunas e separação de UF |
| **Etapa 4** | Consolidação final de todos os anos em um único arquivo unificado |

---

## 💻 Como Usar

Você pode executar este projeto de duas formas:

### ▶️ Opção 1: Jupyter Notebook

1. Abra o terminal e ative seu ambiente virtual, se tiver.
2. Inicie o Jupyter com:

```bash
jupyter notebook
```

3. Navegue até o notebook `ETL-Roubo_de_Cargas.ipynb` e execute célula por célula, seguindo as etapas descritas no índice.

### 🧩 Opção 2: VS Code com Jupyter

1. Instale a extensão **Jupyter** no VS Code.
2. Abra o notebook `ETL-Roubo_de_Cargas.ipynb`.
3. Certifique-se de selecionar o ambiente Python correto no canto superior direito.
4. Execute célula por célula (Shift + Enter).

---

## 🧰 Instalação das Bibliotecas

Instale os pacotes com:

```python
!pip install pandas openpyxl pdfplumber camelot-py PyPDF2 beautifulsoup4 requests selenium webdriver-manager
```

Ou use:

```bash
pip install -r requirements.txt
```

---

## 📁 Estrutura Esperada de Pastas

```
├── dados/                           # Arquivos brutos por ano (PDFs e planilhas baixadas)
│   └── 2014/
│   └── 2015/
│   └── ...
├── dataframe/
│   ├── ano/                         # Planilhas extraídas do PDF (por ano)
│   ├── tratado/                     # Planilhas tratadas e padronizadas
│   └── consolidado/                 # Arquivo final unificado
├── ETL-Roubo_de_Cargas.ipynb        # Notebook com todas as etapas
├── requirements.txt                 # Lista de dependências
└── README.md
```

---

## ⚠️ Observações Manuais

- Os **arquivos do ano de 2018** devem ser **baixados manualmente**, renomeados e salvos na pasta `dados/2018/`.
- Os arquivos `produtos_saude_2014.pdf` e `cosmeticos_2015.pdf` requerem **ajuste manual das colunas** após extração — use o cabeçalho de `medicamentos_2014.xlsx` como base.

---

## ✅ Resultado Final

Ao final da execução, será gerado um arquivo consolidado com todos os dados limpos e estruturados:

```
dataframe/consolidado/consolidado_final.xlsx
```

---

## 👨‍💻 Autor

**Diogo Rodrigues**  
Estagiário em Análise de Dados na ANVISA  
Graduando em Ciência de Dados e Machine Learning - UniCEUB  
[LinkedIn](https://www.linkedin.com/in/diogolupi) | [GitHub](https://github.com/diogolupi)

---

## 📄 Licença

Este projeto é livre para uso educacional e institucional. Consulte os termos de uso da ANVISA para redistribuição de dados públicos.
