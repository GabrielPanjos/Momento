# Momento 

Você está prestes a explorar o banco de dados da empresa "Momento"! Com essa base de dados, vamos treinar consultas SQL e responder algumas perguntas intrigantes que vão revelar como a empresa está organizada. Vamos lá?

### Departamento de Tecnologia 

* Inclua suas próprias informações no departamento de Tecnologia da empresa.

Q:
```sql
INSERT INTO funcionarios(funcionario_id,primeiro_nome,sobrenome,email,senha,telefone,data_contratacao,cargo_id,salario,gerente_id,departamento_id) VALUES (208,'Yago','Gonçalves','franyagoy@gmail.com','yagoat30#@','2054-3750','2024-10-31',20,30.000,NULL,6);
```

* Agora diga, quantos funcionários temos ao total na empresa?

R: No total 42 Funcionários.

Q:
```sql
SELECT COUNT(*) FROM momento.funcionarios;
```

* E quanto ao Departamento de Tecnologia?

R: 6 Funcionários trabalham no Departamento de Tecnologia.

Q:
```sql
SELECT COUNT(*) FROM momento.funcionarios WHERE departamento_id = 6;
```

#

### Departamento de Vendas 

* **Quantos funcionários trabalham no Departamento de Vendas?**
Use uma consulta para descobrir o número total de funcionários alocados nesse departamento.

R: 5 Funcionários trabalham no Departamento de Vendas.

Q:
```sql
SELECT COUNT(*) FROM momento.funcionarios WHERE departamento_id = 8;
```

* **Salários no Departamento de Vendas**

* Qual é o custo total dos salários do pessoal de Vendas? Isso nos ajuda a entender o orçamento do departamento!

R: Os salários do pessoal de vendas é de R$51500.00

Q:
```sql
SELECT SUM(salario) FROM momento.funcionarios WHERE departamento_id = 8;
```


* Quanto o departamento de Vendas gasta em salários?

R: Gastam R$51500.00

Q:
```sql
SELECT SUM(salario) FROM momento.funcionarios WHERE departamento_id = 8;
```


* Quais são os produtos mais vendidos e quais têm pouca ou nenhuma saída?

R: Os produtos mais vendidos são: Uniforme do Superman e Capacete do Homem Formiga.
   Os menos vendidos foram o Laço da Honestidade e os Batarangues Oficiais.

Q:
```sql
SELECT produto_nome,quantidade FROM momento.vendas
INNER JOIN produtos ON produtos.produto_id = vendas.produto_id
ORDER BY quantidade DESC;
```


* Qual é o produto mais caro no inventário da empresa?

R: O produto mais caro é o Sabre de Luz do Mace Windu que custa R$990,29

Q:
```sql
SELECT * FROM momento.produtos ORDER BY produto_price DESC;
```


#

### Departamento de Inovações 

* **Um novo departamento foi criado. O departamento de Inovações.** 
Ele será locado no Brasil. Por favor, adicione-o no banco de dados da empresa colocando quaisquer informações que você achar relevantes.

* O departamento de Inovações está sem funcionários. Inclua alguns colegas de turma nesse departamento.  

R:

Q:
```sql
INSERT INTO escritorios(escritorio_id,escritorio_nome,endereco,cep,cidade,estado_provincia,pais_id) VALUES (2000,"Estúdio de Inovação",'Senac Lapa Tito','05051-000','São Paulo','São Paulo','BR');

INSERT INTO departamentos(departamento_id,departamento_nome,escritorio_id) VALUES (14,'Inovação',2000);
```


#

### Funcionários

* Quantos funcionários da empresa Momento possuem conjuges?

R: 37 funcionários possuem conjuges.

Q:
```sql
SELECT COUNT(*) FROM momento.funcionarios
INNER JOIN dependentes ON funcionarios.funcionario_id = dependentes.funcionario_id
```


* Qual o funcionário contratado há mais tempo na empresa?

R: O funcionário mais velho é Steven Wayne, contratado desde 1987.

Q:
```sql
SELECT CONCAT(primeiro_nome, " ", sobrenome) AS nome_funcionario, data_contratacao FROM momento.funcionarios ORDER BY data_contratacao;
```


* Qual o funcionário contratado há menos tempo na empresa?

R: O funcionário mais novo é Guga, que foi contratado hoje, 31/10/2024.

Q:
```sql
SELECT CONCAT(primeiro_nome, " ", sobrenome) AS nome_funcionario, data_contratacao FROM momento.funcionarios ORDER BY data_contratacao DESC;
```


* Quem são os funcionários com mais tempo na empresa, considerando a `data_contratacao`?

R: Steven Wayne e Jennifer Whalen

Q:
```sql
SELECT CONCAT(primeiro_nome, " ", sobrenome) AS nome_funcionario, data_contratacao FROM momento.funcionarios ORDER BY data_contratacao;
```


* Como a média salarial dos funcionários da "Momento" evoluiu nos últimos anos?
Dica: utilize a função `AVG()` para calcular a média salarial dos funcionários. e `GROUP BY` para agrupar os resultados por ano.

R:

Q:
```sql

```


#

### Médias salariais

* Qual a média salarial dos funcionários da empresa Momento, excluindo-se o CEO, CMO e CFO?

R:

Q:
```sql

```


* Qual a média salarial do departamento de tecnologia? 

R:

Q:
```sql

```


* Qual o departamento com a maior média salarial?

R:

Q:
```sql

```


* Qual o departamento com o menor número de funcionários?

R:

Q:
```sql

```


#

### Produtos

* Pensando na relação quantidade e valor unitario, qual o produto mais valioso da empresa?

R:

Q:
```sql

```


* Qual o produto mais vendido da empresa?

R:

Q:
```sql

```


* Qual o produto menos vendido da empresa?

R:

Q:
```sql

```


#

### Escritórios

* Quantos escritórios a "Momento" possui em cada região? (Dica: relacione as tabelas regioes e escritorios).
* 
R:

Q:
```sql

```



* Qual é o custo total de suprimentos em cada escritório? Que tal ordenar os resultados para ver qual escritório possui os suprimentos mais caros?
