Stacks utilizadas

Backend: Java, Spring Boot, Spring Data JPA
Frontend:

### MINIMUNDO FINANCE-CONTROL ###

O Finance Control será um sistema de controle financeiro pessoal desenvolvido para auxiliar usuários no gerenciamento das suas finanças.

Inicialmente, o sistema permitirá que o usuário realize o seu cadastro, informe o seu capital inicial e registre as suas receitas e despesas.

O sistema deverá registrar as movimentações financeiras realizadas pelo usuário, permitindo acompanhar as entradas e saídas de dinheiro ao longo dos meses.

As despesas e receitas poderão ser consultadas por período, possibilitando que o usuário acompanhe seu saldo disponível e tenha maior controle sobre sua situação financeira.

O Finance Control também disponibilizará um dashboard financeiro com gráficos e resumos mensais, permitindo que o usuário visualize suas receitas, despesas, saldo disponível e a distribuição de seus gastos por categoria. Dessa forma, será possível acompanhar a evolução financeira e analisar o comportamento dos gastos ao longo dos meses.

*REQUISITOS FUNCIONAIS*

### USUÁRIO E AUTENTICAÇÃO ###
RF01	O sistema deve permitir o cadastro de usuários. ()
RF02	O sistema deve permitir que o usuário realize login. ()
RF03	O sistema deve permitir que o usuário encerre sua sessão. ()
RF04	O sistema deve permitir que o usuário consulte e atualize seus dados cadastrais. ()
### CONTAS FINANCEIRAS ###
RF05	O sistema deve permitir o cadastro de contas financeiras. ()
RF06	O sistema deve exigir a informação do capital inicial no cadastro de uma conta financeira. ()
RF07	O sistema deve permitir a consulta das contas financeiras cadastradas. ()
RF08	O sistema deve permitir a edição dos dados de uma conta financeira. ()
RF09	O sistema deve permitir a exclusão de contas financeiras, respeitando as movimentações vinculadas. ()
RF10	O sistema deve calcular e apresentar o saldo atual de cada conta financeira. ()
### CATEGORIAS ###
RF11	O sistema deve disponibilizar categorias predefinidas para receitas e despesas. ()
RF12	O sistema deve permitir que o usuário cadastre categorias personalizadas. ()
RF13	O sistema deve permitir a consulta das categorias disponíveis. ()
RF14	O sistema deve permitir a edição de categorias personalizadas. ()
RF15	O sistema deve permitir a exclusão de categorias personalizadas, respeitando as movimentações vinculadas. ()
### RECEITAS ###
RF16	O sistema deve permitir o cadastro de receitas. ()
RF17	O sistema deve exigir descrição, valor, data, categoria e conta financeira para cadastrar uma receita. ()
RF18	O sistema deve permitir a consulta das receitas cadastradas. ()
RF19	O sistema deve permitir a edição de receitas cadastradas. ()
RF20	O sistema deve permitir a exclusão de receitas cadastradas. ()
### DESPESAS ###
RF21	O sistema deve permitir o cadastro de despesas. ()
RF22	O sistema deve exigir descrição, valor, data, categoria e conta financeira para cadastrar uma despesa. ()
RF23	O sistema deve permitir a consulta das despesas cadastradas. ()
RF24	O sistema deve permitir a edição de despesas cadastradas. ()
RF25	O sistema deve permitir a exclusão de despesas cadastradas. ()
### RELATÓRIO DIÁRIO ### 
RF26	O sistema deve permitir a consulta de relatórios financeiros de uma data específica. ()
RF27	O sistema deve apresentar o total de receitas realizadas na data selecionada. ()
RF28	O sistema deve apresentar o total de despesas realizadas na data selecionada. ()
RF29	O sistema deve apresentar o resultado financeiro da data selecionada. ()
RF30	O sistema deve listar as movimentações financeiras realizadas na data selecionada. ()
### DASHBOARD MENSAL ###
RF31	O sistema deve apresentar o total de receitas do mês selecionado. ()
RF32	O sistema deve apresentar o total de despesas do mês selecionado. ()
RF33	O sistema deve apresentar o resultado financeiro do mês selecionado. ()
RF34	O sistema deve apresentar o saldo atual das contas financeiras. ()
RF35	O sistema deve apresentar as despesas agrupadas por categoria. ()
RF36	O sistema deve apresentar um comparativo entre receitas e despes as do mês selecionado. ()

*REQUISITOS NÃO FUNCIONAIS*

### SEGURANÇA ###
RNF01	O sistema deve armazenar as senhas dos usuários utilizando mecanismos seguros de hash.
RNF02	O sistema deve utilizar autenticação JWT para proteger os recursos restritos.
RNF03	O sistema deve garantir que cada usuário tenha acesso somente aos próprios dados financeiros.
RNF04	O sistema deve validar e controlar o acesso às operações conforme a identidade do usuário autenticado.

### DESEMPENHO ###
RNF05	O sistema deve responder às requisições em tempo adequado para uma aplicação de controle financeiro.
RNF06	O sistema deve realizar consultas financeiras sem comprometer o desempenho da aplicação.

### CONFIABILIDADE E INTEGRIDADE ###
RNF07	O sistema deve garantir a integridade dos dados armazenados no banco de dados.
RNF08	O sistema deve utilizar transações para garantir a consistência das operações financeiras.
RNF09	O sistema deve apresentar mensagens de erro padronizadas quando ocorrerem falhas durante as operações.

### COMPATIBILIDADE E INTERFACE ###
RNF10	O sistema deve disponibilizar uma API seguindo os padrões REST.
RNF11	A API deve permitir integração com aplicações externas por meio de requisições HTTP.

### MANUTENIBILIDADE E DOCUMENTAÇÃO ###
RNF12	O código-fonte deve possuir organização modular e separação de responsabilidades.
RNF13	A API deve possuir documentação utilizando Swagger/OpenAPI.
RNF14	O sistema deve possuir testes automatizados para validar as suas funcionalidades.

*REGRAS DE NEGÓCIOS*

### USUÁRIOS E AUTENTICAÇÃO ###
RN01	Cada usuário deverá possuir um endereço de e-mail único no sistema.
RN02	O cadastro de usuário deverá exigir os dados obrigatórios definidos pelo sistema.
RN03	As credenciais de acesso deverão pertencer exclusivamente ao usuário cadastrado.
RN04	O usuário deverá estar autenticado para acessar funcionalidades restritas do sistema.
RN05	Cada usuário poderá visualizar, cadastrar, editar e excluir somente os seus próprios dados financeiros.
RN06	O encerramento da sessão deverá invalidar a autorização de acesso correspondente, conforme a estratégia de autenticação adotada.
RN07	A exclusão de um usuário deverá impedir o acesso aos seus dados e respeitar as regras de integridade dos registros financeiros vinculados.

### CONTAS FINANCEIRAS ###
RN08	Toda a conta financeira deverá estar vinculada a um único usuário.
RN09	Toda a conta financeira deverá possuir um capital inicial informado no cadastro.
RN10	O capital inicial deverá ser considerado no cálculo do saldo atual da conta.
RN11	O saldo atual deverá ser calculado considerando o capital inicial, as receitas e as despesas vinculadas à conta.
RN12	Receitas deverão aumentar o saldo da conta financeira.
RN13	Despesas deverão diminuir o saldo da conta financeira.
RN14	A alteração de uma movimentação deverá atualizar o saldo correspondente.
RN15	A exclusão de uma movimentação deverá refletir no saldo da conta vinculada.
RN16	Uma conta financeira não poderá ser excluída enquanto possuir movimentações vinculadas.
RN17	Um usuário não poderá acessar ou modificar contas financeiras pertencentes a outro usuário.

### CATEGORIAS ###
RN18	Toda categoria deverá possuir uma classificação entre receita e despesa.
RN19	Uma categoria de receita somente poderá ser utilizada em receitas.
RN20	Uma categoria de despesa somente poderá ser utilizada em despesas.
RN21	As categorias predefinidas pelo sistema não poderão ser excluídas ou modificadas pelos usuários.
RN22	Cada categoria personalizada deverá pertencer ao usuário que a cadastrou.
RN23	O usuário somente poderá editar ou excluir suas próprias categorias personalizadas.
RN24	Uma categoria não poderá ser excluída enquanto possuir movimentações vinculadas.

### RECEITAS ###
RN25	Toda receita deverá possuir um valor maior que zero.
RN26	Toda receita deverá estar vinculada a uma conta financeira existente.
RN27	Toda receita deverá possuir uma categoria classificada como receita.
RN28	A conta financeira e a categoria utilizadas deverão pertencer ao usuário autenticado ou ser recursos predefinidos disponíveis para ele, conforme o caso.
RN29	Toda receita deverá possuir uma data de realização informada.
RN30	O cadastro de uma receita deverá aumentar o saldo da conta financeira vinculada.
RN31	A edição de uma receita deverá considerar o valor anterior para recalcular corretamente o saldo.
RN32	A exclusão de uma receita deverá descontar do saldo o valor anteriormente adicionado.

### DESPESAS ###
RN33	Toda despesa deverá possuir um valor maior que zero.
RN34	Toda despesa deverá estar vinculada a uma conta financeira existente.
RN35	Toda despesa deverá possuir uma categoria classificada como despesa.
RN36	A conta financeira e a categoria utilizadas deverão pertencer ao usuário autenticado ou ser recursos predefinidos disponíveis para ele, conforme o caso.
RN37	Toda despesa deverá possuir uma data de realização informada.
RN38	O cadastro de uma despesa deverá diminuir o saldo da conta financeira vinculada.
RN39	A edição de uma despesa deverá considerar o valor anterior para recalcular corretamente o saldo.
RN40	A exclusão de uma despesa deverá devolver ao saldo o valor anteriormente descontado.

### RELATÓRIO DIÁRIO ###
RN41	O relatório diário deverá considerar somente as movimentações pertencentes à data selecionada.
RN42	O relatório deverá considerar exclusivamente as movimentações do usuário autenticado.
RN43	O total de receitas deverá corresponder à soma das receitas realizadas na data selecionada.
RN44	O total de despesas deverá corresponder à soma das despesas realizadas na data selecionada.
RN45	O resultado financeiro diário deverá ser calculado pela diferença entre receitas e despesas do dia.
RN46	Dias sem movimentações deverão apresentar totais zerados.

### DASHBOARD MENSAL ###
RN47	O dashboard deverá considerar somente as movimentações pertencentes ao mês e ano selecionados.
RN48	O dashboard deverá apresentar exclusivamente informações financeiras do usuário autenticado.
RN49	O total de receitas deverá corresponder à soma das receitas realizadas durante o mês selecionado.
RN50	O total de despesas deverá corresponder à soma das despesas realizadas durante o mês selecionado.
RN51	O resultado financeiro mensal deverá ser calculado pela diferença entre receitas e despesas do período.
RN52	O saldo atual deverá considerar o capital inicial e todas as movimentações efetivadas nas contas do usuário, independentemente do mês selecionado.
RN53	As despesas por categoria deverão ser agrupadas de acordo com suas respectivas categorias.
RN54	O comparativo mensal deverá apresentar os valores totais de receitas e despesas do período selecionado.
RN55	Meses sem movimentações deverão apresentar totais zerados.

### REGRAS RELACIONADAS AOS REQUISITOS NÃO FUNCIONAIS ###
RN56	Nenhuma senha poderá ser armazenada em texto puro.
RN57	Nenhuma operação financeira poderá ser concluída parcialmente quando envolver múltiplas alterações que precisem ser atômicas.
RN58	Toda operação de leitura ou alteração de dados financeiros deverá respeitar a autenticação e autorização do usuário.
RN59	Erros ocorridos durante as operações deverão ser tratados sem expor informações internas sensíveis da aplicação.
RN60	Os valores monetários deverão ser armazenados e processados com precisão decimal, evitando erros de arredondamento de ponto flutuante.
