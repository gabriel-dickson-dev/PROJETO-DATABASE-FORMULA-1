# Banco de Dados - Fórmula 1

Este projeto simples contém o script SQL para criar e testar um banco de dados sobre Fórmula 1 (`db_formula1`). O objetivo é praticar comandos básicos e intermediários de SQL, como criação de tabelas, chaves estrangeiras (`FOREIGN KEY`) e consultas (`SELECT`).

## 📊 Estrutura do Banco

O banco é formado por 3 tabelas relacionadas:
*   **`pais`**: Código e nome do país.
*   **`piloto`**: Nome, salário e o país de origem do piloto.
*   **`gp`**: Nome do Grande Prêmio e quantidade de voltas.

---

## 🚀 Como usar

1. Copie o código do arquivo SQL do projeto.
2. Cole e execute no seu SGBD (como MySQL Workbench, phpMyAdmin ou terminal).
3. O script criará o banco automaticamente, inserirá os dados de teste e executará as consultas de exemplo.

---

## 🔍 O que foi praticado nas consultas:

*   Uso do `LIKE` para filtrar textos.
*   Junção de tabelas com `JOIN` para relacionar Pilotos e Países.
*   Uso de `ALIAS` (`AS`) para renomear colunas no resultado.
*   Filtros com `IN` e faixas de valores com `BETWEEN`.
*   Cálculo de média salarial usando `GROUP BY` e `AVG`.
*   Ordenação de dados com `ORDER BY` e remoção de duplicados com `DISTINCT`.

---

## 🛠️ Tecnologias
*   SQL
*   MySQL / MariaDB

## 👤 Autor
*   Gabriel Dickson (github.com/gabriel-dickson-dev)
