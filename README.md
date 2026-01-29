![Banner do Projeto].()


# Projeto Integrador – ETL de Dados da Olist (MySQL)

## 📌 Visão Geral
Este repositório apresenta o **Projeto Integrador** do curso de **Ciência de Dados**, cujo objetivo foi executar um processo completo de **ETL (Extract, Transform, Load)** utilizando os dados abertos de vendas da **Olist Brasil**, disponibilizados na plataforma Kaggle.

Todo o projeto foi desenvolvido utilizando **MySQL**, desde a extração dos dados brutos até sua organização final em um banco de dados relacional pronto para análise.

A documentação segue a metodologia **STAR (Situation, Task, Action, Result)**.

---

## 🧩 Situação (Situation)
A Olist disponibiliza um conjunto de dados públicos sobre seu marketplace, contendo informações de pedidos, clientes, produtos, vendedores, pagamentos e avaliações.

Entretanto, os dados são fornecidos em múltiplos arquivos CSV, sem tratamento prévio, apresentando:
- Dados distribuídos em várias tabelas
- Campos nulos e inconsistentes
- Falta de padronização de datas e valores
- Necessidade de integração entre entidades

Esses fatores dificultam análises diretas sem um processo adequado de armazenamento e tratamento.

---

## 🎯 Tarefa (Task)
O objetivo deste projeto foi:

- Extrair os dados brutos da Olist a partir do Kaggle
- Armazenar os dados em um banco relacional MySQL
- Limpar, padronizar e tratar os dados
- Criar e validar relacionamentos entre tabelas
- Garantir integridade e confiabilidade da base
- Preparar os dados para análises futuras

---

## ⚙️ Ação (Action)

### 🔹 Extração (Extract)
- Download dos arquivos CSV do dataset **Brazilian E-Commerce Public Dataset by Olist**
- Identificação das principais entidades do negócio

### 🔹 Modelagem
- Criação do banco de dados no MySQL
- Definição das tabelas com tipos de dados adequados
- Criação de chaves primárias (PK) e estrangeiras (FK)

### 🔹 Carga (Load)
- Importação dos arquivos CSV utilizando `LOAD DATA INFILE`
- Validação da carga inicial dos dados

### 🔹 Transformação e Limpeza (Transform)
- Tratamento de valores nulos
- Padronização de datas e horários
- Ajustes de tipos numéricos
- Remoção de registros inconsistentes
- Validação da integridade referencial

---

## 🔄 Diagrama do Processo ETL

```mermaid
flowchart TB
    A[Dataset Olist - Kaggle<br/>Arquivos CSV] 
    --> B[Extração dos Dados]

    B 
    --> C[MySQL - Staging Area<br/>Carga Inicial dos CSVs]

    C 
    --> D[Transformação e Limpeza<br/>
    • Tratamento de valores nulos<br/>
    • Padronização de datas<br/>
    • Ajuste de tipos de dados<br/>
    • Remoção de inconsistências]

    D 
    --> E[Modelagem Relacional<br/>
    Criação de PKs e FKs]

    E 
    --> F[MySQL - Base Final<br/>
    Dados Limpos e Estruturados]

    F 
    --> G[Base Pronta para Análises<br/>
    EDA • BI • Modelos Analíticos]
