 
# Login
  Para realizar login deve solicitar um médoto Post para a Função 'Main' informando um request com o nome do usuário e o hash SHA256 da senha.
  Exemplo de json de solicitação de login.
  >URL: http://localhost:50000/api/main
  ```javascript
  {
    "User":"admin",
    "Passwd":"46070D4BF934FB0D4B06D9E2C46E346944E322444900A435D7D9A95E6D7435F5"
  }
  ```
  Será retornado outro json que pode assumir dois possíveis casos
  1. Login correto:
  Neste caso o json retorna o ID da sessão:
  ```javascript
  {
    "Status":"OK",
    "IDSessao":"46070D4BF934FB0D4B06D9E2C46E346944E322444900A435D7D9A95E6D7435F5",
    "Message":"Login Realizado com sucesso"
  }
  ```
  2. Login incorreto
  ```javascript
  {
    "Status":"ERROR",
    "IDSessao":"",
    "Message":"Usuário ou senha estão inválidos"
  }
  ```
  > * Um usuário pode receber ERROR ao tentar realizar um login por um dos motivos: usuário ou senha inválidos, usuário inativo, empresa do usuário inativa.
