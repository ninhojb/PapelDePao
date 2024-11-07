---
Descricao: Deploy do LanFuse
tags:
  - deploy
Url: https://langfuse.com/docs/deployment/self-host
Data: " 2024-10-08"
---
Para fazer deploy do LangFuse precisamos seguir algumas documentações do app e também a do Núcleo Cliditas.
Na doc do app ele pede para criar uma apontamento para efetuar o build usando o comando `docker build -t langfuse/langfuse -f ./web/Dockerfile .

temos 3 formas de deploy 
- build do codigo fonte
- helm
- baixar imagem

Optamos em fazer o deploy via Helm, usando o repositório 
helm repo add langfuse https://langfuse.github.io/langfuse-k8s
helm repo update

1 - Rodar comandos Cliditas para criar o app
- cliditas init -a langfuse --squad=data-engineering --tribe=machine-learning

2 - Criar a DLC do banco postgres
- cliditas -a langfuse -c master dlc apply -f deploy/prod/dlc/postgres.yaml

3 - Criar a serviceAccount - nao precisa

4 - Gerar o arquivo de deploy .yaml
- kubectl kustomize --enable-helm deploy/staging > deploy/staging/release-langfuse.yaml - nao esta usando

5 - adicionar as variaveis EM PROD
- LANGFUSE_INIT_USER_EMAIL = langfuse@creditas.com
- LANGFUSE_INIT_USER_NAME =admin
- LANGFUSE_INIT_USER_PASSWORD = nZQHo418s1O prod stg=nZQHo418s1!O
- DATABASE_HOST
- DATABASE_NAME
- DATABASE_PASSWORD
- DATABASE_URL
- DATABASE_USERNAME
- ENABLE_EXPERIMENTAL_FEATURES=false-ok
- ENCRYPTION_KEY=82c9dabc39dd40f2849a89b63233eaa63c18a19756831b6d8f36d833de2a84f3 -ok
- HOSTNAME= 0.0.0.0 -ok
- JDBC_DATABASE_URL
- NEXT_PUBLIC_SIGN_UP_DISABLED=false -ok
- NEXTAUTH_SECRET=upvjysvSKg6xFQCpr49B98Nze5UABetLA4vOSyFxUO0= -ok
- NEXTAUTH_URL=https://langfuse.prod.creditas.io -ok
- NODE_ENV=production -ok
- SALT=creditas-langfuse -ok
- TELEMETRY_ENABLED=false -ok

cliditas -a langfuse -c main render -k deploy/staging

u0EH#d0rbJp9u[JtqQ$MV+n


deploy-prod:

runs-on: ubuntu-latest

environment:

name: prod

url: https://langfuse.prod.creditas.io/

steps:

- uses: actions/checkout@v3

- uses: creditas/nucleon-actions/actions/setup-cliditas@v1

with:

env: prod.creditas.io

cliditas-version: "latest"

- run: cliditas -c main -a langfuse deploy -k deploy/prod --yes


mle
prod sk-w1SHi7lKQhMNs28jqNkbkg

langfuse = Langfuse( secret_key="sk-lf-f6e1a0e5-9149-4209-8474-8ebb00ea9ce8", public_key="pk-lf-118c03a4-4e6f-421f-a333-16584474496a", host="https://langfuse.prod.creditas.io" )


