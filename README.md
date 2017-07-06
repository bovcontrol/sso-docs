# Bovcontrol - Single Sign On
Agora você pode integrar seu applicativo com o login do Bovcontrol, de maneira super simples, prática e rápida.

## Como fazer?
Primeiro, entre em contato com a BovControl para solicitar sua chave de acesso ao sistema, pelo email hello@bovcontrol.com, indicando a finalidade desta integração.

Uma vez recebida as chaves, basta inserir uma div com o id ssobov, seguida dos atributos, clientID, clientSecret e callback. Siga o [exemplo] (example.html). 

Um botão será inserido em sua aplicação e uma vez que o usuário faça o login no Bovcontrol, um token será enviado junto com o callback. Com esse token, é possível acessar a página do usuário e coletar algumas informações como nome e email.

## Acessando a página do usuário
Uma vez recebido o token do usuário, sua aplicação pode acessar o endereço https://api.bovcontrol.com/me/v1/clientId/ (Subistitua o <ClientId> pelo Id recebido), enviando no headers o token do usuário.

A resposta será no seguinte formato:
```json
{
    "email": "joao@silva.com.br",
    "language": "pt-BR",
    "name": "João",
    "surname": "Silva",
    "phone": "555555555",
    "bov_public_id": "PoQW",
    "farm_name": "Nome da Fazenda",
    "valid_user": 1
}
```