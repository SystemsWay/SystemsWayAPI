
# Gerência de Usuário
> Link base: http://localhost:50000/Api/Usuario
## Get
	Recebe como parâmetro o id da sessão (Obrigatório) e o id do usuário (opcional).
### Exemplo de link sem id do usuário:
> http://localhost:5000/api/Usuario/EB078EB1ABFC9722EBAB9BA3DD303AFD37DD1AE50A791CBA16ABEE0A727029DF

Para este exemplo será retornado todos os usuários cadastrados para a mesma empresa do usuário da sessão informada.
	
Exemplo de Retorno:
```javascript
[{
    "Id":"1",
    "UserName":"admin",
    "Ativo":"true"
  },
  {
    "Id":"2",
    "UserName":"user2",
    "Ativo":"true"
 }]
 ```

 ### Exemplo de link com id do usuário:
 > http://localhost:5000/api/Usuario/EB078EB1ABFC9722EBAB9BA3DD303AFD37DD1AE50A791CBA16ABEE0A727029DF?id=1
 
 Para este exemplo será retornado o usuário cadastrado com o id igual a 1
 Exemplo de Retorno:
```javascript
[{
    "Id":"1",
    "UserName":"admin",
    "Ativo":"true"
  }]
```

 * Caso o ID da sessão informado na URL sejá inválido, será retornado um json com status ERROR, informando que o ID da sessão está inválido. Neste caso, verifique se o id está correto, caso esteja, loge novamente, a sessão pode ter sido inativada pelas rotinas da API (inativação por inatividade, por alteração no usuário vínculado ou alteração no registro da empresa do usuário)
 
## Post

 Recebe um json e o id da sessão do usuário
 Exemplo de link:
 > http://localhost:5000/api/Usuario/EB078EB1ABFC9722EBAB9BA3DD303AFD37DD1AE50A791CBA16ABEE0A727029DF
 Arquivo json associado:

```javascript
{
  "UserName":"User02",
  "PassWord":"0778cfd9d0558d1f6486216c914807405e82c743974a656411fe29980e59c157",
  "Email":"email@teste.com",
  "Ativo":true
}
```

Caso o usuário seja cadastrado, será retornado um json informando que o usuário foi cadastrado, tal como o do exemplo:

```javascript
{
    "Status":"OK",
    
    "Message":"",
    "StackTrace":""
 }
```

Caso o usuário não seja cadastrado, será retornado um json infotmando o problema:

```javascript
{
    "idCadastro": 3,
    "codigo": "OK",
    "message": null
}
```

Caso o Hash da senha não seja informado, uma senha aleatória será gerada e enviada para o email informado no registro, o rash da senha gerada será retornado
 Onde a mensagem pode ser uma das seguintes (Assumindo que o ID da sessão seja válido):
 > * O formato de senha está incorreto, a senha deve estar sob o Hash SHA/256, com 64 caracteres.
 > * O nome do usuário não pode conter espaços
 > * Já Existe um usuário cadastrado com este nome.
 
## Put

 > Link Base: http://localhost:5000/api/Usuario/EB078EB1ABFC9722EBAB9BA3DD303AFD37DD1AE50A791CBA16ABEE0A727029DF?id=1
 
 Recebe um arquivo na URL o id da Sessão e o ID do usuário, ambos obrigatórios, e um arquivo json com os novos dados do usuário.
 Exemplo de arquivo json:
 
```javascript
{
  "UserName":"User02",
  "PassWord":"0778cfd9d0558d1f6486216c914807405e82c743974a656411fe29980e59c157",
  "Email":"email2@teste.com",
  "Ativo":true
}
```

Caso o ID exista, será realizar a atualização dos dodos, utilizando os dados informados no json.

Obs.: Não é necessário enviar o arquivo json completo, somente o campo que foi editado, isso vale para todos os métodos post da api. 

**SEMPRE INFORME O VALOR DO CAMPO Ativo POIS CASO NÃO SEJA INFORMADO, O REGISTRO SERÁ INATIVADO**

## Delete
> Link Base: http://localhost:5000/api/Usuario/EB078EB1ABFC9722EBAB9BA3DD303AFD37DD1AE50A791CBA16ABEE0A727029DF?id=1
Recebe o ID da sessão e o ID do usuário
Reotorna um código de erro, ou código OK, informando que a ação foi realizada.