# SystemsWayAPI
Documentação para a API SystemsWay

[Executando a API](https://github.com/SystemsWay/SystemsWayAPI/blob/master/InstalacaoAPI.md#systemswayapi)

[Configurações](https://github.com/SystemsWay/SystemsWayAPI/blob/master/pages/Configuracoes.md#configura%C3%A7%C3%A3o-api)

[Retorno API](https://github.com/SystemsWay/SystemsWayAPI/blob/master/pages/RetornoAPI.md#valida%C3%A7%C3%A3o-de-retorno-api)

[Login](https://github.com/SystemsWay/SystemsWayAPI/blob/master/pages/login.md#login)

[Gerência de Usuários](https://github.com/SystemsWay/SystemsWayAPI/blob/master/pages/gerenciaUsuario.md#ger%C3%AAncia-de-usu%C3%A1rio)

[Gerência de Pessoas](https://github.com/SystemsWay/SystemsWayAPI/blob/master/pages/GerenciaPessoa.md#ger%C3%AAncia-de-pessoa)

# Introdução
	A API da Systems Way foi criado com o intuito de facilitar a integração do WAY com demais aplicações e permitir que um mesmo sistema responda a solicitações das diversas plataformas que serão utilizadas pelo WAY.
## Detalhes técnicos
  > * É implementado utilizando .Net Core 2.0.
  > * Utiliza protocolo HTTP,
  > * Basicamente é uma WEB API RESTFul, respondendo ao métodos GET, POST, PUT e DELETE com suas features específicas, atendendo às necessidades da SystemWay.
  > * Todos os dados de login (senha) são salvos e trafegados utilzando o Algoritmo SHA256 com 64 caracteres. ([Mais detalhes sobre SHA256](http://www.iwar.org.uk/comsec/resources/cipher/sha256-384-512.pdf))
  > * O caminho padrão da API é definido como sendo http://IP:5000/api/function, onde IP é o endereço de ip onde o mesmo está hospedado, e function é a função/módulo que está sendo requisitado.
  
**Obs.: Para os exemplos desse tutorial, assuma que a API está ospedada em localhost**

# Considerações iniciais
  > * É necessário realizar login somente uma vez, cada login realizado cria uma sessão, as demais atividades serão realizadas conforme essa sessão.
  > * Caso queira trocar a sessão, basta realizar o login novamente, neste caso, a sessão antiga será inativada. E a nova sessão válida será a retornada no login.
  > * Não será possível conseguir o ID de uma sessão, exceto com a realização de um novo login.
  > * Todos os dados criados e manipulados por umas sessão são associados à empresa associada ao usuário da sessão.
  > * Um usuário possui somente uma sessão ativa.
 

Obs.: Nenhum registro será apagado, o delete somente inativa o registro com id informado
