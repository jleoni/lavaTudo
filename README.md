# lavaTudo

Teste Dr. Lava Tudo
Desenvolvedor

Utilize git clone https://github.com/jleoni/lavaTudo para utilizar este projeto.

Você está recebendo teste completo para nossa vaga de Desenvolvedor. Nosso objetivo é analisar
suas habilidades e desenvoltura para conseguir resolvê-lo. Não deixe de enviar o resultado, mesmo
que incompleto! Qualquer dúvida sobre o teste, encaminhe para vagas@drlavatudo.com com o
assunto "DÚVIDA TI".

Considerando a seguinte estrutura de dados:

Cliente Serviços
● ID (auto incrementável) 
● Nome 
● Email 
● Data de Nascimento 
● Telefone celular 
● Telefone residencial

Serviços
● ID (auto incrementável) 
● Nome serviço 
● Valor final 

Ordem de Serviços
● ID (auto incrementável) 
● ID Cliente
● ID Serviço
● Data Contratação
● Data Execução

Pode se perceber que o Cliente pode contratar apenas um serviço por vez. Considerando essa
informação:

1. Quais alterações devemos fazer nessa estrutura para que o cliente consiga fazer mais de
um serviço por solicitação?

Resposta:

Criar a nova tabela Ordem de Serviços Detalhe e alterar a tabela de Serviços

Ordem de Serviços
● ID (auto incrementável) 
● ID Cliente
● Data Contratação
● Data Execução

Ordem de Serviços Detalhe
● ID (auto incrementável) 
● ID Ordem Serviço
● ID Serviço
● Valor

2. Utilizando qualquer Linguagem de Consulta Estruturada (SQL) e considerando a
nova estrutura de dados criada na questão anterior:

a. Selecione todos os clientes e a quantidade de ordem de serviços realizados

b. Selecione todas as Ordens de Serviços com mais de um serviço

c. Selecione os serviços mais vendidos

d. Atualize o valor final de todos os serviços em 12%

e. Remova a última ordem de serviço criada

f. Insira um cliente

Coloque todas as respostas e queries em um único arquivo .sql e adicione dentro de repositório com
o nome “Queries.sql”

API

Considerando seus conhecimentos em desenvolvimento de software e utilizando a base de
dados da questão 2, implemente um sistema (na linguagem de sua preferência) com os
seguintes requisitos :

1. Construir Api seguindo padrões Restful

2. Api’s que precisam ser construídas e os dados que devem retornar:
a. EndPoint: /api/os/

i. Retornar dados de uma de Ordem de Serviço específica
ii. Retornar listagem de todas as Ordens de Serviço

b. EndPoint: /api/cliente/
i. Retornar dados de um cliente específico
ii. Retornar listagem de clientes ordenados pelo nome
iii. Cadastrar cliente, evitando que emails repetidos sejam utilizados

c. EndPoint: /api/servico/
i. Retornar dados de um serviços específico
ii. Retornar listagem dos serviços disponíveis
iii. Retornar listagem dos serviços ordenando pelos mais realizados

Não é necessário construir interface (tela) para realizar as chamadas à API, você pode
utilizar a ferramenta Postman ou outra de sua escolha, o retorno de cada endpoint deverá
estar em formato json, salve todos em um único arquivo .txt e adicione no repositório com
o nome “Json.txt”

Requisitos utilizados neste projeto:
Ferramenta: Visual Studio 2015
Linguagem: C#.NET
Tecnologia: Web API, MVC e ASP.NET.
Banco de dados: SQL Server 2008
Conexão com banco de dados: Entity Framework


Para criar o banco de dados:

USE [COSMOS]
GO

--1. Quais alterações devemos fazer nessa estrutura para que o cliente consiga fazer mais de
um serviço por solicitação?

--Resposta:

/****** Object:  Table [Cliente]    Script Date: 09/13/2018 09:15:38 ******/
CREATE TABLE [Cliente](
	[ID] [int] IDENTITY(1,1) NOT NULL,
	[Nome] [varchar](50) NULL,
	[Email] [varchar](50) NULL,
	[DataDeNascimento] [datetime] NULL,
	[TelefoneCelular] [varchar](50) NULL,
	[TelefoneResidencial] [varchar](50) NULL,
 CONSTRAINT [PK_Cliente] PRIMARY KEY CLUSTERED 
(
	[ID] ASC
)WITH (PAD_INDEX  = OFF, STATISTICS_NORECOMPUTE  = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS  = ON, ALLOW_PAGE_LOCKS  = ON) ON [PRIMARY]
) ON [PRIMARY]
GO

/****** Object:  Table [Servico]    Script Date: 09/13/2018 09:15:38 ******/
CREATE TABLE [Servico](
	[ID] [int] IDENTITY(1,1) NOT NULL,
	[NomeServico] [varchar](50) NULL,
	[ValorFinal] [numeric](18, 2) NULL,
 CONSTRAINT [PK_Servico] PRIMARY KEY CLUSTERED 
(
	[ID] ASC
)WITH (PAD_INDEX  = OFF, STATISTICS_NORECOMPUTE  = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS  = ON, ALLOW_PAGE_LOCKS  = ON) ON [PRIMARY]
) ON [PRIMARY]
GO

/****** Object:  Table [OrdemServico]    Script Date: 09/13/2018 09:15:38 ******/
CREATE TABLE [dbacosmos].[OrdemServico](
	[ID] [int] IDENTITY(1,1) NOT NULL,
	[IdCliente] [int] NULL,
	[DataContratacao] [datetime] NULL,
	[DataExecucao] [datetime] NULL,
 CONSTRAINT [PK_OrdemServico] PRIMARY KEY CLUSTERED 
(
	[ID] ASC
)WITH (PAD_INDEX  = OFF, STATISTICS_NORECOMPUTE  = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS  = ON, ALLOW_PAGE_LOCKS  = ON) ON [PRIMARY]
) ON [PRIMARY]
GO

/****** Object:  Table [OrdemServico_Detalhe]    Script Date: 09/13/2018 09:15:38 ******/
CREATE TABLE [dbacosmos].[OrdemServico_Detalhe](
	[ID] [int] IDENTITY(1,1) NOT NULL,
	[IdOrdemServico] [int] NOT NULL,
	[IdServico] [int] NULL,
	[Valor] [numeric](18, 2) NULL,
 CONSTRAINT [PK_OrdemServico_Detalhe] PRIMARY KEY CLUSTERED 
(
	[ID] ASC
)WITH (PAD_INDEX  = OFF, STATISTICS_NORECOMPUTE  = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS  = ON, ALLOW_PAGE_LOCKS  = ON) ON [PRIMARY]
) ON [PRIMARY]
GO

select * from cliente
select * from servico
select * from ordemservico
select * from ordemservico_detalhe

insert into cliente values ('jesse leandro leoni','jlleoni@gmail.com','1973-12-28','(31) 99224-1771', '(31) 99224-1771')
insert into cliente values ('marlene alves soares','marlene@gmail.com','1985-05-19','(31) 99224-0071', '(31) 99224-0071')
insert into servico values ('lavar tapetes do carro',50)
insert into servico values ('lavar carpete do carro',150)
insert into ordemservico values (2,getdate(),getdate())
insert into ordemservico_detalhe values(1,1,50)
insert into ordemservico_detalhe values(1,2,150)
insert into ordemservico values (3,getdate(),getdate())
insert into ordemservico_detalhe values(3,1,50)

--2. Utilizando qualquer Linguagem de Consulta Estruturada (SQL) e considerando a
--nova estrutura de dados criada na questão anterior:

--a. Selecione todos os clientes e a quantidade de ordem de serviços realizados

select 
	nome, count(*) qtd_servico_realizado 
from 
	cliente c 
	inner join ordemservico os on c.id = os.idcliente 
group by nome
	
	inner join ordemservico_detalhe osd on os.id = osd.idordemservico

--b. Selecione todas as Ordens de Serviços com mais de um serviço

select 
	os.id os,
	count(osd.id) qtd_servicos_realizados
from cliente c 
	inner join ordemservico os on c.id = os.idcliente	
	inner join ordemservico_detalhe osd on os.id = osd.idordemservico
group by os.id
having count(osd.id) > 1

--c. Selecione os serviços mais vendidos

select 
	NomeServico, count(NomeServico) qtd_vendas
from 
	ordemservico os
	inner join ordemservico_detalhe osd on os.id = osd.idordemservico
	inner join servico s on s.id = osd.idservico
group by
	NomeServico
order by 2 desc	

--d. Atualize o valor final de todos os serviços em 12%

update servico set valorfinal = valorfinal * 1.12
update ordemservico_detalhe set valor = valor * 1.12

--e. Remova a última ordem de serviço criada

delete from ordemservico_detalhe where idordemservico = (select max(id) from ordemservico)
delete from ordemservico where id = (select max(id) from ordemservico)

--f. Insira um cliente

insert into cliente values ('valentina leoni','valente@gmail.com','2015-02-20','(31) 99224-0071', '(31) 99224-0071')
