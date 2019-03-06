# desafio-limite

### Desafio Conductor de Seleção 
Seguindo as orientações do desafio, segue a descrição e orientações a respeito da aplicação desenvolvida
	- Recursos utilizados:
	```
	* IDE Spring Tool Suite Version: 3.9.7.RELEASE
	* JDK 11
    * Apache Maven 4.0.0
    * JUnit 4.12
	* Banco de dados MySql 8.0.13
    * Interface visual em HTML5, JavaScript, jQuery 1.10.1, Bootstrap 3.3.7
    ```

### Pré requisitos:
	- A aplicação está preparada para rodar o banco de dados, o serviço REST e a interface visual no mesmo computador e este computador deve ter:
	```
	* MySql 5.5+
	* JDK 11+
	* Web browser Google Chrome ou Mozila Firefox
    ```
	
### Como instalar a aplicação:
	- Para instalar a aplicação, siga os seguintes passos:
	```
	1. Logar como root no MySql e executar o script "\conductor\docs\mysql\cria_base_mysql.sql".
	2. Copiar a pasta "\conductor\telas" para qualquer local do mesmo computador.
	3. Copiar o arquivo "\conductor\target\conductor.jar" para qualquer local do mesmo computador.
	4. Executar o arquivo "conductor.jar" com o comando "java -jar c:\caminho\onde\foi\copiado\conductor.jar".
	5. Abrir o arquivo "telas\index.html" em algum web browser Google Chrome ou Mozila Firefox. Nos meus teste não funcionou no Microsoft Internet Explorer nem no Microsoft Edge
    ```
	
### Características técnicas:
	- A aplicação tem as seguintes características técnicas:
	```
	* O serviço REST utiliza a porta HTTP 8081 para evitar conflito caso a porta padrão 8080 já esteja em uso
	* O serviço REST busca o banco de dados no servidor "localhost" na porta padrão "3306" e define o "serverTimezone" para "America/Sao_Paulo"
	* A interface visual busca o serviço REST na url "http://localhost:8081/"
    ```
	
### Como utilizar a aplicação:
	```
	1. Ao abrir o arquivo "telas\index.html" no web Browser, tem um menu superior com as opções
		1.1. Inicio
			- Contém esta mesma descrição
		1.2. Pessoas
			- Cadastro de pessoas que podem ter de zero a N contas
        1.3. Contas
			- Cadastro de contas que devem pertencer a uma pessoa e podem ter um limite de crédito de zero a N reais.
        1.4. Lançamentos
			- Cadastro de lançamentos de uma conta, que podem ser de crédito quando o valor for positivo e de débito quando o valor for negativo.
		1.5. Encargos
			- Cadastro de encargos a serem cobrados das contas com o saldo negativo. Os encargos incidem de X em X tempo, definido no campo frequencia (em minutos), sobre as contas com saldo negativo e o valor a ser cobrado pode ser percentual sobre o saldo devedor ou em reais.
		1.6. Transferência
			- Uma transferência pode ser de SALDO ou de LIMITE, sendo que transferência de LIMITE só pode ser feita entre contas de uma mesma pessoa
	2. As telas Pessoas, Contas, Lançamentos, e Encargos tem os botões:
		2.1. Novo, que cadastra um novo item utilizando os valores preenchidos nos campos
		2.2. Alterar, que altera o item selecionado utilizando os valores preenchidos nos campos
		2.3. Excluir, que exclui o item selecionado
		2.4. Limpar Campos, que limpa os campos da tela
	3. A tela Transferência tem os botões:
		3.1 - Transferir, que executa a transferência definida nos campos. Uma transferência de saldo consiste em criar dois novos lançamentos, um de débito na conta de origem e um de crédito na conta de destino. Uma transferência de LIMITE somente reduz o limite da conta de origem e adiciona na conta destino.
    ```