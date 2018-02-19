# Gerência de Pessoa
> Link base: http://localhost:50000/Api/Pessoa

## Get
Recebe como parâmetro o id da sessão (Obrigatório) e o id da pessoa (opcional).

### Exemplo de link sem id da Pessoa:
> http://localhost:5000/api/Pessoa/4FA5A66F5B872103A4D1B755B40174B658AABF2021B3898E7DC72F4BCBC0C9E4

### Exemplo de link sem com id da Pessoa:
> http://localhost:5000/api/Pessoa/4FA5A66F5B872103A4D1B755B40174B658AABF2021B3898E7DC72F4BCBC0C9E4?id=1

### Exemplo Retorno sem id Informado:

```javascript
[
    {
        "nome": "Systems Way",
        "nomeFantasia": "Systems Way",
        "dataNascimento": "1996-05-30T00:00:00",
        "id": 1,
        "tipopessoa": [],
        "documentoPessoa": [],
        "emails": [],
        "telefones": [],
        "enderecos": []
    },
    {
        "nome": "PessoaTeste",
        "nomeFantasia": "PessoaTese",
        "dataNascimento": "2018-02-18T00:00:00",
        "id": 2,
        "tipopessoa": [
            "FISICA",
            "RESPONSAVEL"
        ],
        "documentoPessoa": [
            {
                "documento": "05744321160",
                "tipoDocumento": "CPF",
                "documentoPessoaId": 1
            },
            {
                "documento": "6205000",
                "tipoDocumento": "RG",
                "documentoPessoaId": 2
            }
        ],
        "emails": [
            {
                "email": "wayteste@test.com",
                "pessoaEmailId": 1,
                "ativo": true
            }
        ],
        "telefones": [
            {
                "ddd": "62",
                "telefoneDef": "996770058",
                "telefonePessoaId": 1
            },
            {
                "ddd": "62",
                "telefoneDef": "35773573",
                "telefonePessoaId": 2
            }
        ],
        "enderecos": [
            {
                "latitude": "-16.630662",
                "longitude": "-49.390210",
                "observacao": " Proximo a algum supermecado",
                "siglaEstado": "GO",
                "cidade": "Goiania",
                "bairro": "Um Bairro",
                "numero": "S/N",
                "descricao": "Rua num sei mais o nome",
                "cep": "75380000",
                "complemento": "Quadra 0, Lote 5",
                "ie": "INSENTO",
                "enderecoId": 1
            }
        ]
    }
]
```

## Post

 Recebe um json e o id da sessão do usuário
 Exemplo de link:
 > http://localhost:5000/api/Pessoa/EB078EB1ABFC9722EBAB9BA3DD303AFD37DD1AE50A791CBA16ABEE0A727029DF
 Arquivo json associado:

```javascript
{
    "Nome":"PessoaTeste",
    "NomeFantasia":"PessoaTese",
    "DataNascimento":"2018-02-18 00:00:00",
    "Tipopessoa": ["FISICA","RESPONSAVEL"],
    "DocumentoPessoa":[{
    		"Documento":"05744321160",
    		"TipoDocumento":"CPF"
    	},{
    		"Documento":"6205000",
    		"TipoDocumento":"RG"
    	}],
    "Emails":[
    	{
    		"Email":"wayteste@test.com"
    	}],
    "Telefones":[{
    	"DDD":"62",
    	"TelefoneDef":"996770058"
    	},{
    	"DDD":"62",
    	"TelefoneDef":"35773573"
    	}],
    "Enderecos":[
    {
    	"Latitude":"-16.630662",
    	"Longitude":"-49.390210",
    	"Observacao":" Proximo a algum supermecado",
    	"SiglaEstado":"GO",
    	"Cidade":"Goiania",
    	"Bairro":"Um Bairro",
    	"Numero":"S/N",
    	"Descricao":"Rua num sei mais o nome",
    	"Cep":"75380000",
    	"Complemento":"Quadra 0, Lote 5",
    	"IE":"INSENTO"
    }
    ]
}
```

Tipos de valores Padrões:

>   Tipopessoa 

	* ALUNO

	* RESPONSAVEL

	* EMPRESATRANSPORTE

	* MOTORISTA

	* ESCOLA

	* FISICA

	* JURIDICA

>  TipoDocumento

	* CPF

	* CNPJ

	* RG

	* CNH

>  IE

	* ISENTO

	* Valor númerico

Será retornado um Json, informando o Id da pessoa Cadastrada:

```javascript
{
	"idCadastro":5,
	"codigo":"OK",
	"message":null
}
```

## Delete

> http://localhost:5000/api/Pessoa/C0B55C03C5FF973D88520BD12E814918042E5F9A9160A16C30B1A8B1B8C65B01?id=2

Recebe o ID da sessão e o ID do usuário
Reotorna um código de erro, ou código OK, informando que a ação foi realizada.