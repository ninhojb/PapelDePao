---
Descricao: Como criar um App no Núcleo Cliditas
tags:
  - cliditas
  - deploy
Url: https://github.com/Creditas/cliditas/blob/master/docs/examples/app-manifest-walkthrough/README.md
Data: " 2024-10-18"
---

# Deploy aplicativos

O núcleo contem uma abstração de objetos do kubernetes, Deployment, Service, PodDisruptionBudget, Ingress e Secret, como esses objetos é possível deixar no ar um app, toda a configuração é feita através de arquivos `yaml`

Um exemplo básico de um app.

`apiVersion: apps.creditas.io/v2alpha1
`kind: App
`metadata:
	`name: <nomeApp>
`spec:
	`processes:
		`web: {}
	`routes:
		`<nomeApp>.<env>.creditas.io:
			`paths:
			`- path: /
			  `process: web`

Com esse arquivo `ymal`, utilizamos um o comando do `cliditas` para fazer o deploy utilizamos o comando `cliditas -c main -a <appNome> deploy <arquivo.ymal>`

Depois da execução do comando é gerados os pods e objetos do kubernetes seguindo o desenho abaixo


![[Captura de Tela 2024-10-18 às 19.37.12.png]]
Esse processo eh o básico para subir um app. Mas pode acontecer de algum app precisar de configurações ou objetos a mais. Para isso podemos utilizar o `kustomize`


sk-f27JITEoFFc6o5bqeTnFkA

[ ] Pr de config no liteLLM

[ ] Criar ApiKey


um unico user 
user admin 
senha nZQHo418s1!O

from langfuse import Langfuse

langfuse = Langfuse(
  secret_key="sk-lf-da57d073-89b1-4227-aa1c-0c5bb1eab471",
  public_key="pk-lf-a13f2a2c-ed26-4e95-9411-49eb596002ef",
  host="https://langfuse.stg.creditas.io"
)
|   |
|---|
|fb80cf22-dd26-4287-ba25-82c4bab794ff|

|                                      |     |
| ------------------------------------ | --- |
| fb80cf22-dd26-4287-ba25-82c4bab794ff |     |
|                                      |     |
|                                      |     |
|                                      |     |

teste 2
from langfuse import Langfuse langfuse = Langfuse( secret_key="sk-lf-36725284-1ee2-4f9c-8ac0-f2d97bfd2df9", public_key="pk-lf-3e735c26-6a3a-4417-8b59-2eaaf176fd54", host="https://langfuse.stg.creditas.io" )