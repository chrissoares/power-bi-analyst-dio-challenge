### Descrição do desafio módulo 3 – Processamento de Dados Simplificado com Power BI

 ✔ - 1. Criação de uma instância na Azure para MySQL

✔ - 2. Criar o Banco de dados com base disponível no github

✔ - 3. Integração do Power BI com MySQL no Azure

✔ - 4. Verificar problemas na base a fim de realizar a transformação dos dados

### Diretrizes para transformação dos dados

✔ - 1. Verifique os cabeçalhos e tipos de dados

✔ - 2. Modifique os valores monetários para o tipo double preciso

✔ - 3. Verifique a existência dos nulos e analise a remoção

✔ - 4. Os employees com nulos em Super_ssn podem ser os gerentes. Verifique se há algum colaborador sem gerente

✔ - 5. Verifique se há algum departamento sem gerente

✔ - 6. Se houver departamento sem gerente, suponha que você possui os dados e preencha as lacunas

✔ - 7. Verifique o número de horas dos projetos

✔ - 8. Separar colunas complexas

✔ - 9. Mesclar consultas employee e departament para criar uma tabela employee com o nome dos departamentos associados aos colaboradores. A mescla terá como base a tabela employee. Fique atento, essa informação influencia no tipo de junção

✔ - 10. Neste processo elimine as colunas desnecessárias.

✔ - 11. Realize a junção dos colaboradores e respectivos nomes dos gerentes . Isso pode ser feito com consulta SQL ou pela mescla de tabelas com Power BI. Caso utilize SQL, especifique no README a query utilizada no processo.

✔ - 12. Mescle as colunas de Nome e Sobrenome para ter apenas uma coluna definindo os nomes dos colaboradores

✔ - 13. Mescle os nomes de departamentos e localização. Isso fará que cada combinação departamento-local seja único. Isso irá auxiliar na criação do modelo estrela em um módulo futuro.

✔ - 14. Explique por que, neste caso supracitado, podemos apenas utilizar o mesclar e não o atribuir.
Não encontrei a opção de atribuir, a opção existente no vídeo que trata sobre o tema, mas que não teve nenhuma atenção no mesmo, é Acrescentar. Então podemos Mesclar Consultas ou Acrescentar Consultas.
Acrescentar Consultas não cabe ao item 13 devido a forma como funciona, ela unifica em uma tabela todos os campos das tabelas selecionadas. Caso as tabelas tenham campos com nomes em comuns, eles estarão preenchidos conforme as tabelas originais, os campos que existem apenas em uma tabela, ficaram com valor nulo para os registros da outra tabela.
Imagine o caso onde temos a tabela Empregados (id, nome, endereço, salario) e a tabela Dependentes onde temos (id, nome, parentesco, id_funcionario). Ao realizar o Acrescentar com essas duas tabelas o resultado seria uma tabela Empregados_Dependentes (id, nome, endereço, salario, parentesco, id_funcionario). Vou exemplificar com dados agora.
Empregados
Id  Nome        Endereço                            Salario
1   Christiano  Rua do Código, 512, Sarara, MG      5.000,00
2   Jeronimo    Rua do Porto, 77, Verdemar, RJ      7.000,00
3   Zelele      Rodovia 512 Km 5, S/N, Malhada, GO  7.500,00

Dependentes
Id  Nome        Parentesco  Id_Funcionario
1   Enzo        Filho       2
2   Sheila      Conjuge     2
3   Rose        Conjuge     1
4   Maria       Filho       3

Empregados_Dependentes
Id  Nome        Endereço                            Salario   Parentesco  Id_Funcionario
1   Christiano  Rua do Código, 512, Sarara, MG      5.000,00  Null        Null
2   Jeronimo    Rua do Porto, 77, Verdemar, RJ      7.000,00  Null        Null
3   Zelele      Rodovia 512 Km 5, S/N, Malhada, GO  7.500,00  Null        Null
1   Enzo        Null                                Null      Filho       2
2   Sheila      Null                                Null      Conjuge     2
3   Rose        Null                                Null      Conjuge     1
4   Maria       Null                                Null      Filho       3

Os campos cujo as tabelas originais possuem valor, serão preenchidos, cada um em seu respectivo registro (linha), os demais serão nulos.
    
✔ - 15. Agrupe os dados a fim de saber quantos colaboradores existem por gerente

✔ - 16. Elimine as colunas desnecessárias, que não serão usadas no relatório, de cada tabela
