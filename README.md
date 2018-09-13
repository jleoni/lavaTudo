# lavaTudo

Teste Dr. Lava Tudo
Desenvolvedor

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



