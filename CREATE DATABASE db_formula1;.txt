CREATE DATABASE db_formula1;

USE db_formula1;

-- Tabela País
CREATE TABLE pais (
    cod_pais INT PRIMARY KEY AUTO_INCREMENT,
    nome_pais VARCHAR(50) NOT NULL
);

-- Tabela Piloto
CREATE TABLE piloto (
    cod_piloto INT PRIMARY KEY AUTO_INCREMENT,
    nome_piloto VARCHAR(100) NOT NULL,
    cod_pais INT,
    salario DECIMAL(10,2),
    FOREIGN KEY (cod_pais) REFERENCES pais(cod_pais)
);

-- Tabela GP
CREATE TABLE gp (
    cod_gp INT PRIMARY KEY AUTO_INCREMENT,
    nome_gp VARCHAR(100),
    qtd_voltas INT
);

-- Inserindo países
INSERT INTO pais(nome_pais) VALUES
('BRASIL'),
('ITALIA'),
('FRANCA'),
('BELARUS'),
('BOLIVIA');

-- Inserindo pilotos brasileiros
INSERT INTO piloto(nome_piloto, cod_pais, salario) VALUES
('Ayrton Senna', 1, 100000),
('Felipe Massa', 1, 90000),
('Rubens Barrichello', 1, 85000),
('Nelson Piquet', 1, 95000),
('Emerson Fittipaldi', 1, 80000);

-- Inserindo pilotos italianos
INSERT INTO piloto(nome_piloto, cod_pais, salario) VALUES
('Giuseppe Farina', 2, 75000),
('Riccardo Patrese', 2, 72000),
('Jarno Trulli', 2, 70000);

-- Inserindo pilotos franceses
INSERT INTO piloto(nome_piloto, cod_pais, salario) VALUES
('Alain Prost', 3, 110000),
('Pierre Gasly', 3, 78000);

-- Inserindo GPs
INSERT INTO gp(nome_gp, qtd_voltas) VALUES
('GP Brasil', 71),
('GP Italia', 53),
('GP Franca', 58);

-- QUERY 1
-- Liste o nome dos países que começam com B e terminam com L
SELECT nome_pais
FROM pais
WHERE nome_pais LIKE 'B%L';

-- QUERY 2
-- Liste os pilotos do Brasil, Itália e França
SELECT p.nome_piloto, pa.nome_pais
FROM piloto p
JOIN pais pa ON p.cod_pais = pa.cod_pais
WHERE pa.nome_pais IN ('BRASIL', 'ITALIA', 'FRANCA');

-- QUERY 3
-- Liste o nome dos pilotos
SELECT nome_piloto
FROM piloto;

-- QUERY 4
-- Liste o nome dos GP e quantidade de voltas usando ALIAS
SELECT nome_gp AS GrandePremio,
qtd_voltas AS Voltas
FROM gp;
-- QUERY 5
-- Liste os pilotos e seus países
SELECT p.nome_piloto, pa.nome_pais
FROM piloto p
JOIN pais pa ON p.cod_pais = pa.cod_pais;

-- QUERY 6
-- Salários entre 70 e 100 mil
SELECT nome_piloto, salario
FROM piloto
WHERE salario BETWEEN 70000 AND 100000;

-- QUERY 7
-- Média salarial por país
SELECT cod_pais, AVG(salario) AS media_salarial
FROM piloto
GROUP BY cod_pais;

-- QUERY 8
-- Diferentes salários em ordem crescente
SELECT DISTINCT salario
FROM piloto
ORDER BY salario ASC;
