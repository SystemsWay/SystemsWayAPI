 
# Login
  Para realizar login deve solicitar um médoto Post para a Função 'Main' informando um request com o nome do usuário e o hash SHA256 da senha.
  Exemplo de json de solicitação de login.
  >URL: http://localhost:50000/api/main
  ```javascript
  {
    "User":"admin",
    "Passwd":"46070D4BF034FB0D4B06D9E2C46E346944E322744900A485D7D9A95E6D7435F5"
  }
  ```
  Será retornado outro json que pode assumir dois possíveis casos
  1. Login correto:
  Neste caso o json retorna o ID da sessão:
  ```javascript
  {
    "codigo": "00",
    "idSessao": "3F933C10CEE311E383AB361983E584CFA66D403B6E83E43AEFD958B01A42A53F"
  }
  ```
  2. Login incorreto
  ```javascript
{
    "codigo": "01",
    "idSessao": "NA"
}
  ```
  > * Um usuário pode receber ERROR ao tentar realizar um login por um dos motivos: usuário ou senha inválidos, usuário inativo, empresa do usuário inativa.
