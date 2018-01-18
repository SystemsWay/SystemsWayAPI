# SystemsWayAPI
Documentação para Executar API

## Pré Requisitos

> * Sistema Operacional de 64 bits, obrigatório.
> * Instalar o MYSQL Server a partir da versão 5.7.* [Mysql Server](https://dev.mysql.com/downloads/mysql/)
Obs.: Até o momento não foi testado a utilização da API para configurações alternativas de conexão com o banco (porta de acesso, banco em outra máquina) recomenda-se instalar com as configurações padrões: localhost, porta default de instalação.
> * É necessário instalar o .Net Core 2.1.*, links abaixo:
> > * [Linux (Debian e derivados, Red Hat e Derivados)](https://docs.microsoft.com/pt-br/dotnet/core/linux-prerequisites?tabs=netcore2x)
> > * [Windows](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-2.1.4-windows-x64-installer)
> > * [MAC](https://docs.microsoft.com/pt-br/dotnet/core/macos-prerequisites?tabs=netcore2x).

## Obtendo uma Versão

> Será necessário obter a senha para extração dos arquivos, solicite a senha por e-mail.

* Acesse o [reposítorio] e realize o donwload da versão desejada.
* Extraia os arquivos no local de sua preferência

## Configuração do Serviço

A configuração se resuma a edição de dois arquivos:

> Config/Config.json

Contem as configurações de execução:
* RunPort: porta em que o serviço estará disponibilizado.
* ShowLog: Caso executado em modo console, e com esta flag ativa, os logs serão exibidos na console em modo texto.
* SaveLog: Caso esta flag esteja ativa, os logs serão salvos no caminho informado em 'LogFile'
* LogFile: Caminho onde os logs serão salvos, caso SaveLog Esteja ativo.

> appsettings.json

Contem as configurações de conexão com a base de dados.
Obs.: Não é necessário criar a base de dados. Caso o servidor exista, será criada a base com o nome 'Way' assim que o serviço for iniciado. Caso a base já exista, nenhuma ação será executada (update de base).
Obs.: O único valor que pode ser alterado neste arquivo é a string de conexão com o banco: StringConnectionMYSQL

* StringConnectionMYSQL configure os parâmetros server, user id, password e database conforme a sua instalação do Mysql Server.

## Executar em Console 

Obs.: A forma de executar a API não se diferência tando no Windows, Linux e MAC. A sintaxe do comando é o mesmo.
* Abra uma janela de console, e navegue até a pasta onde extraiu
* Execute o comando abaixo:

> dotnet WAY.dll

Deverá ser exibido o endereço onde o serviço esteja disponível, caso tudo ocorra bem.
![Exemplo de API executando em console em um terminal Linux](https://github.com/SystemsWay/SystemsWayAPI/blob/master/Image/RunServerAPI.png)
## Executar como serviço

**Ainda não implementado**
