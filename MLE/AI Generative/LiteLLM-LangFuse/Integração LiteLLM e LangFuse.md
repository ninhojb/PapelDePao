---
Descricao: Processo de utilização e integração das Plataformas
tags:
  - integração
  - LiteLLM
  - LangFuse
Url: 
Data: " 2024-10-23"
---

![[Captura de Tela 2024-10-23 às 11.28.08.png]]


## LiteLLM

![[lite.png]]

Essa Doc irá mostrar com é feita a integração e utilização das plataformas LiteLLM e LangFuse.
Através do arquivo de `config.yaml` do LiteLLM indicamos em qual plataforma utilizaremos para a observabilidade no nosso caso é o LangFuse.

``` Config.yaml
litellm_settings:

default_team_settings:
	- team_id: os.environ/SECRET_PROJECT_MLE
	  success_callback: ["langfuse"]
	  langfuse_public_key: os.environ/LANGFUSE_PUB_KEY_MLE
	  langfuse_secret: os.environ/LANGFUSE_PRIVATE_KEY_MLE
	  langfuse_host: "https://langfuse.stg.creditas.io"
	- team_id: os.environ/SECRET_PROJECT_HOME_RENTALS
	  success_callback: ["langfuse"]
	  langfuse_public_key: os.environ/LANGFUSE_PUB_KEY_HOME-RENTALS
	  langfuse_secret: os.environ/LANGFUSE_PRIVATE_KEY_HOME-RENTALS
	  langfuse_host: "https://langfuse.stg.creditas.io"
```
Neste exemplo do arquivo `config.yaml` temos configurado dois times.
- team_id: Id do time
- success_callback: Plataforma de observabilidade
- langfuse_public_key: Public Key gerada no LangFuse
- langfuse_secret: Secret Key gerada no LangFuse

`Obs: os valores das variaveis são inseridos dentro do Cliditas através do comando de exemplo:`
`clitidas config -a litellm SECRET-PROJECT-<valor>`

## LangFuse

![[langfuse_logo.png]]

No LangFuse precisamos seguir alguns passos para poder receber os logs do LiteLLM.
- Criar a Organização
- Adicionar os membros utilizando o e-mail da Creditas.
- Adicionar as permissões de cada membro
- Criar o projeto
- Gerar as Api Keys

## Na prática
Apos o cliente faz uma requisição para o endereço do LiteLLM.
abaixo um exemplo de request:
```
curl --location https://litellm.stg.creditas.io/chat/completions\ 
--header 'Content-Type: application/json' \ 
--header 'Authorization: Bearer CHAVE_AKI' \ 
--data ' { 
"model": "NameModel", 
"messages": [ 
	{ "role": "user",
	  "content": "what llm are you" 
	  } 
	] 
} '
```

O LiteLLM recebe a request e passa para o `BedRock`.
O response é recepcionado pelo LiteLLM e enviado para o cliente e para o LangFuse por meio das `Api Keys` ele consegue direcionar par ao projeto e gerar os gráficos.

![[Captura de Tela 2024-10-23 às 11.44.43.png]]