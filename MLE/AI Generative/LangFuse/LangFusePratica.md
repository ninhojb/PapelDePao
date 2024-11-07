---
Descricao: Passo a Passo para montar o ambiente local
tags:
  - AI
  - logs
Url: http://localhost:3000
Data: " 2024-10-03"
---

Criando o ambiente local
- Clone o repositório https://github.com/langfuse/langfuse.git
- cd langfuse
- docker compose up -d

Primeiros passos
- acessar o endereço http://localhost:3000
- crie o seu user
- criar uma organização
- criar um projeto
- criar a api key


`pip install langfuse`

`from langfuse import Langfuse langfuse = Langfuse( secret_key="sk-lf-55dcc5a4-b71e-42bd-aaf0-6c4ae8903075", public_key="pk-lf-a9002059-5a4f-40f5-870f-aac08caaba0b", host="http://localhost:3000" )`

Integração com LiteLLM 
https://langfuse.com/docs/integrations/litellm/tracing
1. LiteLLM Proxy com OpenAI SDK Wrapper, o proxy padroniza mais de 100 modelos no esquema da API OpenAI e o wrapper Langfuse OpenAI SDK instrumenta as chamadas LLM.
2. Proxy LiteLLM que pode enviar logs para o Langfuse se habilitado na interface do usuário.
3. LiteLLM Python SDK que pode enviar logs para o Langfuse se as variáveis ​​de ambiente estiverem definidas.

from langfuse import Langfuse langfuse = Langfuse( secret_key="sk-lf-72288252-3fde-4e92-ac48-2eba38b74244", public_key="pk-lf-9d291351-0443-4a2c-bd99-a3e45ac97465", host="http://localhost:3000" )

### Tamanho de instância recomendado[](https://langfuse.com/docs/deployment/self-host#recommended-instance-size)

Para ambientes de produção, sugerimos usar uma configuração de 2 núcleos de CPU e 3 GB de RAM para o contêiner Langfuse. Na AWS, isso equivaleria a uma `t3.medium`instância. O contêiner é stateless, permitindo que você o dimensione automaticamente com base no uso real de recursos.