# FarmTech Solutions - PBL Fase 3: Banco de Dados Oracle

**Curso:** Inteligência Artificial & Computação em Nuvem
**Instituição:** FIAP ON
**Atividade:** PROJETO FASE 3 - ETAPAS DE UMA MÁQUINA AGRÍCOLA

---

## 👥 Grupo

* **Cauan Otto Rodrigues Sousa** – RM567940
* **Fernando Araújo Gurgel** – RM567606
* **Iraci Monteiro Souza** – RM567544
* **Maria Luisa Rodrigues Nascimento** – RM567659
* **Rafaela Torres Martins** – RM567735

---

## 🎯 Desafio

O objetivo desta entrega obrigatória é carregar os dados coletados pelos sensores da Fase 2 em um banco de dados relacional Oracle. O processo envolve a configuração do Oracle SQL Developer, a importação dos dados e a validação da carga através de consultas SQL.

---

## ⚙️ Processo Detalhado

O trabalho foi dividido nas seguintes etapas:

### 1. Preparação dos Dados

Nossos dados da Fase 2 (originados do arquivo `cidades.json`) foram processados e convertidos para um arquivo Excel (`dados_cidades.xlsx`). Este foi o formato utilizado para a importação no Oracle SQL Developer, que reconheceu o formato `excel 95-2003 (xls)`.

### 2. Configuração do Oracle SQL Developer

Foi feito o download e a instalação do Oracle SQL Developer. A conexão com o banco de dados da FIAP foi estabelecida com sucesso e nomeada como `FIAP_cap1_fase3`.

### 3. Importação dos Dados

Com a conexão ativa, seguimos o "Assistente de Importação de Dados":

1.  Clicamos com o botão direito em "Tabelas" e selecionamos "Importar Dados...".
2.  Carregamos o arquivo `dados_cidades.xlsx`.
3.  Definimos o nome da tabela de destino como **`dados_cidades_API`**.
4.  Mapeamos as colunas (`CIDADE` e `PROBABILIDADE_DE_CHUVA`) e seus tipos.
5.  Concluímos a importação, que foi confirmada com a mensagem "Tarefa bem-sucedida e importação com commit efetuado."

### 4. Solução de Problemas (Erro ORA-00900)

Na primeira tentativa de consulta, encontramos o erro `ORA-00900: instrução SQL inválida`.

* **Comando com Erro:** `SELECT*FROM DADOS_CIDADES_API;`
* **Causa:** Erro de sintaxe. Faltava um espaço entre `SELECT` e o caractere `*`.

### 5. Validação (Consulta SQL)

Após corrigir a sintaxe, a consulta foi executada com sucesso, validando que todos os dados estavam presentes no banco da Oracle.

* **Comando Correto:**
```sql
SELECT * FROM DADOS_CIDADES_API;

