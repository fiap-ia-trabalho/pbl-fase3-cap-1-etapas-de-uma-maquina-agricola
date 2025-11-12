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

## 🎬 Vídeo de Demonstração (Parte 1)

O vídeo abaixo demonstra o processo completo de conexão, a importação assistida e a consulta de validação (`SELECT *`) na tabela final.

**https://youtu.be/249f2QICEHE**

---

## ⚙️ Processo Detalhado e Prints de Evidência

O trabalho foi dividido nas seguintes etapas:

### 1. Preparação dos Dados e Conexão

Os dados da Fase 2 (`cidades.json`) foram processados e convertidos para `dados_cidades.xlsx`. A conexão com o banco de dados da FIAP foi estabelecida com sucesso e nomeada como `FIAP_cap1_fase3`.

![Conexão Estabelecida](Ambiente%20preparado%20(1).jpeg)

### 2. Importação dos Dados

Seguimos o "Assistente de Importação de Dados" para carregar o arquivo `xlsx`:

1.  **Visualização dos Dados (Etapa 1 de 5):** O assistente identificou o arquivo de origem.
    ![Início da Importação](In%C3%ADcio%20da%20importa%C3%A7%C3%A3o%20(2).jpeg)
2.  **Método de Importação (Etapa 2 de 5):** Definimos o nome da tabela de destino como **`dados_cidades_API`**.
    ![Definição da Tabela](M%C3%A9todo%20de%20importa%C3%A7%C3%A3o%20e%20nomenclatura(3).jpeg)
3.  **Escolher Colunas (Etapa 3 de 5):** Mapeamos as colunas `CIDADE` e `PROBABILIDADE_DE_CHUVA`.
    ![Seleção das Colunas](Sele%C3%A7%C3%A3o%20das%20colunas(4).jpeg)
4.  **Definição de Coluna (Etapa 4 de 5):** Ajustamos os tipos de dados.
    ![Definição dos Tipos](defini%C3%A7%C3%A3o%20das%20colunas(5).jpeg)
5.  **Concluir (Etapa 5 de 5):** O assistente mostrou o resumo.
    ![Resumo da Importação](Concluir%20importa%C3%A7%C3%A3o%20(6).jpeg)

A importação foi confirmada com a mensagem "Tarefa bem-sucedida e importação com commit efetuado."

![Sucesso](importa%C3%A7%C3%A3o%20bem%20sucedida(7).jpeg)

### 3. Solução de Problemas (Erro ORA-00900)

Na primeira tentativa de consulta, encontramos o erro `ORA-00900: instrução SQL inválida`.

* **Comando com Erro:** `SELECT*FROM DADOS_CIDADES_API;`
* **Causa:** Erro de sintaxe. Faltava um espaço entre `SELECT` e o caractere `*`.

![Erro de Sintaxe](Erro%20de%20sintaxe%20no%20teste%20(8).jpeg)

### 4. Validação (Consulta SQL Correta)

Após corrigir a sintaxe, a consulta foi executada com sucesso, validando que todos os dados estavam presentes no banco da Oracle.

* **Comando Correto:**
```sql
SELECT * FROM DADOS_CIDADES_API;
