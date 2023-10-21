# Processando e Transformando Dados com Power BI

Esse projeto é um produto da coleta, limpeza e transformação de dados no Power BI de uma empresa.

## Coleta

A coleta de dados foi feita por um servidor de MySQL em nuvem da Azure. Após a criação e povoamento das tabelas, 
foi realizada a conexão com o Power BI, sem haver necessidade de fazer o download dos dados brutos na máquina local.

## Limpeza e Transformação de Dados

O conjunto de dados é composto por 6 tabelas: funcionário, departamento, dependente, localização de departamento,
projeto e tempo de trabalho.

O processo iniciou na tabela funcionário, onde realizei a separação da coluna de endereço em funcionário em número da casa, 
rua, estado e país, e depois uni as colunas de primeiro nome, nome do meio e sobrenome em uma única coluna chamada nome.

Prossegui renomeando os nomes das colunas de todas as tabelas para melhor acompanhamento 
e removi colunas desnecessárias que não usarei nos relatórios: endereço completo (permaneci apenas com estado e país), 
data de nascimento dos funcionários e dependentes e as colunas com tabelas mescladas por meio de chaves estrangeiras.

Prosseguindo, corrigi o tipo dos dados de cada coluna, tratando IDs e outros números não quantitativos como texto 
e valores de salário como inteiro com ponto fixo.

Criei três tabelas, produtos de mesclagem, para acompanhamento facilitado de informações importantes, 
que são: nome dos funcionários e dos respectivos gerentes (mesclagem por ID de funcionário e ID de gerente na própria tabela de funcionário),
nome dos funcionários e de seus departamentos (mesclagem por IDs de departamento nas tabelas funcionário e departamento),
e contagem de funcionários por gerente (mesmo caso da primeira mesclagem, só que agrupando os valores por contagem).

Por fim, corrigi os relacionamentos das tabelas afim de que o modelo funcione corretamente.
