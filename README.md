# Teste - Mairon Duarte Costa
## **Introdução do projeto**

Esse projeto é a junção dos dois testes ( teste_excel, teste_sql_perguntas_(1) ), fiz o teste de word/sql de forma que seja possível executar as suas etapas.

## **Arquitetura do projeto**

![image.png](img/modelagem_sql.png)

## **Pré-requisitos**

Para esse projeto foi utilizado o SQL-Server, para a execução da pasta **src/** tenha o **SQL Server Management Studio 20** instalado.

1. Clone esse repositorio

```bash

git clone https://github.com/Mairondc21/teste_Mairon.git
```

2. Execute o src/create_table.sql, Certifique-se de Criar também o Database mercantil

```sql
CREATE DATABASE mercantil;
USE mercantil;
CREATE TABLE PESSOA (
    COD_PESSOA INT PRIMARY KEY NOT NULL,
    TIPO_PESSOA VARCHAR(1) NOT NULL,
    NOME VARCHAR(100) NOT NULL,
    CPF VARCHAR(11) NULL,
    CNPJ VARCHAR(14) NULL,
    SEXO VARCHAR(1) NULL,
    ESTADO_CIVIL VARCHAR(20) NULL
);

CREATE TABLE CLIENTE (
    COD_PESSOA INT NOT NULL,
    COD_AG INT NOT NULL,
    DATA_RFC DATE NOT NULL,
    MAT_GERENTE INT NOT NULL,
    PRIMARY KEY (COD_PESSOA, COD_AG, DATA_RFC),
    FOREIGN KEY (COD_PESSOA) REFERENCES PESSOA(COD_PESSOA)
);

INSERT INTO PESSOA (COD_PESSOA, TIPO_PESSOA, NOME, CPF, CNPJ, SEXO, ESTADO_CIVIL) VALUES
(1, 'F', 'Maria Silva', '12345678901', NULL, 'F', 'Solteira'),
(2, 'F', 'João Souza', '09876543210', NULL, 'M', 'Casado'),
(3, 'J', 'Empresa XYZ Ltda', NULL, '12345678000199', NULL, NULL),
(4, 'F', 'Mario Costa Silva', '55687700468',NULL ,'M', 'Casado'),
(5, 'F', 'Lanna Maria', '65429733365', NULL, 'F', 'Viuva');

INSERT INTO CLIENTE (COD_PESSOA, COD_AG, DATA_RFC, MAT_GERENTE) VALUES
(1, 101, '2022-03-10', 201),
(2, 102, '2023-03-10', 202),
(1, 103, '2022-06-01', 203),
(3, 105, '2022-01-01', 204),
(4, 105, '2022-01-01', 205);
```

3. Execute o arquivo src/respostas.sql - Não precisa executar a 1) pergunta

