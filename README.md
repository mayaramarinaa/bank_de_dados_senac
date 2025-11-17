# bank_de_dados_senac
Este projeto consiste na criação de um banco de dados para uma loja de roupas, com o objetivo de organizar informações sobre produtos, clientes, pedidos, fornecedores, categorias e pagamentos.
O banco foi modelado utilizando um diagrama entidade-relacionamento (DER) e implementado com comandos SQL (DDL e DML).

- Modelo do Banco de Dados

O banco de dados realizado representa: clientes da loja, produtos disponíveis, categorias de produtos, fornecedores, pedidos realizados e métodos de pagamento.

- Diagrama do Projeto:
<img width="814" height="595" alt="Diagrama loja de roupas" src="https://github.com/user-attachments/assets/28dfb146-d203-4bc0-8b86-b440ab5afc9c" />

- Objetivo do Projeto

Este projeto foi criado com os objetivos de aprender a modelar um banco de dados completo, criar tabelas utilizando DDL, inserir e manipular dados utilizando DML, compreender relacionamentos entre tabelas (1:N, N:N), organizar um repositório profissional para projetos SQL. Durante seu desenvolvimento, pratiquei conceitos de chaves primárias e estrangeiras, normalização básica e execução de scripts completos no MySQL.

- Como Executar o Script SQL

Baixe o arquivo .sql disponível em sql_scripts/ em seguida abra seu software SQL (MySQL Workbench, DBeaver, etc.), crie o banco de dados:

CREATE DATABASE loja_roupas;
USE loja_roupas;
Execute o script completo.

- O que é DDL?

DDL (Data Definition Language) define a estrutura do banco de dados.

- Comandos DDL:
  
Comando	Função:

CREATE	Cria tabelas
ALTER	Altera tabelas
DROP	Exclui tabelas
TRUNCATE	Limpa tabelas

- Exemplos de DDL do projeto:
  
Criando a tabela clientes:

CREATE TABLE clientes (
    id_cliente INT PRIMARY KEY,
    nome VARCHAR(45),
    cpf INT,
    email VARCHAR(45),
    telefone INT,
    data_nascimento DATETIME,
    endereco VARCHAR(45)
);

Criando a tabela produtos:

CREATE TABLE produtos (
    id_produtos INT PRIMARY KEY,
    nome VARCHAR(45),
    tamanho VARCHAR(45),
    cor VARCHAR(45),
    preco DECIMAL,
    descricao VARCHAR(45),
    categoria_id_categoria INT,
    fornecedor_id_fornecedor INT,
    FOREIGN KEY (categoria_id_categoria) REFERENCES categoria(id_categoria),
    FOREIGN KEY (fornecedor_id_fornecedor) REFERENCES fornecedor(id_fornecedor)
);

- O que é DML?

DML (Data Manipulation Language) manipula dados de tabelas.

- Comandos DML:
  
Comando	Função:

INSERT	Adiciona dados
UPDATE	Atualiza dados
DELETE	Exclui dados
SELECT	Consulta dados

- Exemplos de DML do projeto
  
Inserindo um cliente:

INSERT INTO clientes (id_cliente, nome, cpf, email, telefone, data_nascimento, endereco)
VALUES (1, 'Maria Silva', 12345678900, 'maria@gmail.com', 11999999999, '1990-05-10', 'Rua A, 100');

Inserindo um produto:

INSERT INTO produtos (id_produtos, nome, tamanho, cor, preco, descricao, categoria_id_categoria, fornecedor_id_fornecedor)
VALUES (1, 'Camiseta Básica', 'M', 'Preta', 49.90, 'Camiseta algodão', 1, 1);

Atualizando um produto:

UPDATE produtos
SET preco = 59.90
WHERE id_produtos = 1;

Deletando um cliente:

DELETE FROM clientes
WHERE id_cliente = 1;

- Aprendizagem do projeto

Com o presente projetos podemos aprender a modelar um banco de dados completo, diferença entre DDL e DML, como criar e relacionar tabelas, como documentar projetos no GitHub e como organizar arquivos SQL em repositórios.
