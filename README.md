# 👩🏽‍💻 Desafio DIO Star Schema - Tabela Fato Professor

Este repositório contém o modelo de um esquema em estrela (Star Schema) criado para a análise de dados relacionados a professores, cursos ministrados, e departamentos dentro de uma instituição educacional. O modelo foi implementado utilizando o MySQL Workbench.

### 🔶 Estrutura do Esquema
O modelo é composto pela tabela fato Professor e suas respectivas tabelas dimensão: Curso, Departamento, Data, e ProfessorStatus. O objetivo deste modelo é fornecer uma base sólida para realizar análises como a carga de trabalho dos professores, o número de cursos ministrados por departamento, e a análise de status de emprego.

### 🔶 Tabela Fato: Professor
A tabela fato contém as métricas e fatos que estão sendo analisados. A tabela `Professor` armazena informações sobre os professores e sua relação com os cursos e departamentos.

```
CREATE TABLE Fato_Professor (
    ProfessorID INT PRIMARY KEY,
    Nome VARCHAR(255),
    CursoID INT,
    DepartamentoID INT
);
```

### 🔶 Tabela Dimensão: Curso
A tabela dimensão `Curso` armazena informações sobre os cursos ministrados pelos professores.

```
CREATE TABLE Dim_Curso (
    CursoID INT PRIMARY KEY,
    NomeCurso VARCHAR(255),
    ProfessorID INT
);
```
### 🔶 Tabela Dimensão: Departamento
A tabela dimensão `Departamento` contém informações sobre os departamentos aos quais os professores estão associados.

```
CREATE TABLE Dim_Departamento (
    DepartamentoID INT PRIMARY KEY,
    NomeDepartamento VARCHAR(255),
    ProfessorID INT
);
```
### 🔶 Tabela Dimensão: Data
A tabela dimensão `Data` contém informações temporais, como a data de oferta de cursos ou eventos relacionados aos professores.

```
CREATE TABLE Dim_Data (
    DataID TIMESTAMP PRIMARY KEY,
    Data DATE,
    ProfessorID INT
);
```
### 🔶 Tabela Dimensão: ProfessorStatus
A tabela `ProfessorStatus` armazena informações sobre o status profissional dos professores, como tipo de contrato e status de trabalho.

```
CREATE TABLE Dim_ProfessorStatus (
    StatusID INT PRIMARY KEY,
    DescricaoStatus VARCHAR(45), -- Ex: efetivo, temporário, em licença
    TipoContrato VARCHAR(45), -- Ex: tempo integral, parcial
    ProfessorID INT
);
```

### 🔶 Relacionamentos
As tabelas de dimensões são relacionadas à tabela fato Professor através de chaves estrangeiras (ProfessorID). Estas relações permitem a realização de análises profundas sobre o desempenho e status dos professores, cursos ministrados, departamentos, e mais.


![Prof_Star_Schema](https://github.com/feer-rodriguess90/DesafioDIO_Criando_StarSchema/blob/main/ProfStarSchema.png)

## 🎯 Resultados
Com este desafio, foi possível aprender na prática a criação e modelagem de um esquema em estrela (Star Schema), utilizando o MySQL Workbench para estruturar e relacionar tabelas de fato e dimensões. O projeto reforçou a importância de entender os conceitos de modelagem dimensional para construir soluções de Business Intelligence (BI) robustas e escaláveis.


## 🤝🏽 Contribuições
Contribuições são bem-vindas! Sinta-se à vontade para abrir issues ou enviar pull requests.

Happy coding! 👩🏽‍💻

[![linkedin](https://img.shields.io/badge/-LinkedIn-%230077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/datavizwithfer/) 
[![medium](https://img.shields.io/badge/Medium-12100E?style=for-the-badge&logo=medium&logoColor=white)](https://medium.com/@DataVizWithFer)
