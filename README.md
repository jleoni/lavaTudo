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
