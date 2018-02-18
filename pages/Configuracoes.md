# Configuração API

## String Acesso Base de Dados

> * Encontra-se no arquivo 'appsettings.json'
Uma vez acessado este arquivo, procure pela String 'StringConnectionMYSQL'

Nesta string, preencha os dados de acesso à base de dados, segue exemplo de String abaixo, este arquivo sempre virá preenchido com valor default utilizado durante os testes:

``` server=localhost;user id=root;password=D26m04a03;database=Way;Charset=utf8; ```

## Configurações API

As configurações da API estão localizadas na caminho ~/Config/Config.json

Cada configuração segue especificada abaixo:

> * RunPort: Valor inteiro que especifica a porta na qual a API estará disponível. Caracteristicas: A posta especificada estará acessível somente à rede interna, a porta acessível a rede externa corresponde ao valor informado +1

> * ShowLog: Valor Booleano (true, false). Caso esteja com valor true, os logs serão exibidos no console caso a API esteja sendo executada em console

> * SaveLog: Valor Booleano (true, false). Caso esteja com valor true, os logs serão salvos em arquivo com o nome composto pela data atual.

> * LogFile: Campo String, deve conter o caminho da pasta onde os logs serão salvos. Um arquivo será criado por dia. Somente 

> * EmailHost: Campo String, deve conter o host utilizado para envio de email

> * EmailPort: Campo Int, deve conter a porta que o host de emil deve utilizar

> * EmailEneableSSL: Campo Booleano, Deve informa se o host de email utiliza SSL

> * EmailUseDefaultCredencials : Campo Booleano, Deve informa utiliza-se a credenciais defaults do host (sem credenciais)

> * EmailTimeOut: Campo Int, contém o tempo em milisegundos de timeout de envio de email

> * EmailUser: Campo String, Contém o email utilizado para envio de emails

> * EmailPasswd: Campo String, contém a Senha do Email.

> * EmailTimeSleepTask: Campo Int, tempo em milisegundos de delay para serviço de envio de email

> * LengthRandomPasswd: Campo Int, deve conter a quantidade de caracteres de senhas geradas aleatoriamente.

> * UpdateDataBase: Campo Booleano, indica se a instacia da API está sendo utilizada para realizar update na base de dados
