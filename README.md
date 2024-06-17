# BDTrabalhoFinal
Repositório do trabalho final de banco de dados.

## 📚 Vocabulário de Banco de Dados

### 🗄️ SGBD
> Um Sistema Gerenciador de Banco de Dados (SGBD) é um conjunto de softwares que permite a criação, manipulação e administração de bancos de dados. Ele oferece ferramentas para armazenamento, recuperação, modificação e exclusão de dados, garantindo a integridade e segurança das informações.

### 🛡️ Restrições em banco de dados
> Restrições em banco de dados são regras aplicadas aos dados para garantir a integridade e a consistência dos mesmos (Chaves primárias, chaves estrangeiras, restrições de não nulo, etc). 

### 📊 Modelo relacional
> O modelo relacional é uma abordagem para gerenciar dados usando tabelas, onde cada tabela representa uma entidade e as colunas representam os atributos dessa entidade. 

### 🧩 Modelagem conceitual
> A modelagem conceitual é a fase inicial do design de banco de dados onde são definidos os requisitos do sistema e representados de maneira independente de qualquer sistema de gerenciamento de banco de dados. Ela usa diagramas de entidade-relacionamento (ER) para descrever as entidades, atributos e relacionamentos.

### 🔄 Modelagem lógica
> Modelagem lógica é a etapa onde o modelo conceitual é transformado em um esquema lógico, adequado para um SGBD específico.

### 🏗️ Modelagem física
> A modelagem física é a etapa final do design de banco de dados onde o esquema lógico é implementado no SGBD escolhido. Inclui a definição de estruturas de armazenamento, índices, partições e outras considerações de desempenho.

### 🖥️ Linguagem SQL
> A Linguagem de Consulta Estruturada (SQL) é a linguagem padrão usada para interagir com bancos de dados relacionais.

### 📜 Data Definition Language (DDL)
> A Data Definition Language (DDL) é um subconjunto da SQL utilizado para definir e modificar a estrutura dos objetos no banco de dados, como tabelas, índices e esquemas (CREATE, ALTER, DROP).

### ✍️ Data Manipulation Language (DML)
> A Data Manipulation Language (DML) é um subconjunto da SQL usado para inserir, atualizar, deletar e consultar dados no banco de dados (INSERT, UPDATE, DELETE e SELECT).

### 🌟 Boas práticas em modelagem de banco de dados
> Boas práticas em modelagem de banco de dados incluem a normalização dos dados para eliminar redundâncias, o uso adequado de chaves primárias e estrangeiras e a definição clara de índices para melhorar o desempenho.

## 💼 Atividades

### 📋 Todos os clientes armazenados no sistema:
```
SELECT * FROM cliente;
```
### 🚗 Exiba os veículos que tenham final 3 no número da placa
```
SELECT * FROM veiculo WHERE placa LIKE '%3';
```
### 📞 Mostre os clientes que residem no RS e que não possuam telefone
```
SELECT * FROM cliente WHERE uf_cnh = 'RS' AND telefone IS NULL;
```
### ⏳ Exiba o código dos clientes que alugaram veículos por mais de 90 dias.
```
SELECT id_cliente FROM contrato_aluguel WHERE duracao > 90;
```
### 📊 Quantos veículos há cadastrados no sistema
```
SELECT COUNT(*) AS total_veiculos FROM veiculo;
```
### 👶 Mostre o veículo alugado por Alexandre Zamberlan.
```
SELECT v.* 
FROM contrato_aluguel ca
JOIN cliente c ON ca.id_cliente = c.id_cliente
JOIN veiculo v ON ca.id_veiculo = v.id_veiculo
WHERE c.nome = 'Alexandre Zamberlan';
```
### 👥 Mostre os clientes e os escritórios associados no contrato de aluguel.
```
SELECT c.nome AS cliente, e.nome AS escritorio 
FROM contrato_aluguel ca
JOIN cliente c ON ca.id_cliente = c.id_cliente
JOIN escritorio e ON ca.id_escritorio = e.id_escritorio;
```
