---
Descricao: Langfuse é uma plataforma de engenharia LLM
tags:
  - logs
  - AI
Url: https://langfuse.com/docs
Data: " 2024-10-03"
---


LangFuse é uma plataforma de engenharia LLM de código aberto que ajuda equipes a depurar, analisar e iterar colaborativamente em seus aplicativos LLM.

observabilidade

ele precisa de postgres

aws https://github.com/aws-samples/deploy-langfuse-on-ecs-with-fargate


### Desenvolver[](https://langfuse.com/docs#develop)

- **Observabilidade:** Instrumente seu aplicativo e comece a ingerir rastros no Langfuse ( [Início rápido](https://langfuse.com/docs/get-started) , [Rastreamento](https://langfuse.com/docs/tracing) )
    - Rastreie todas as chamadas LLM e todas as outras lógicas relevantes em seu aplicativo
    - [SDKs assíncronos](https://langfuse.com/docs/sdk) para Python e JS/TS
    - [`@observe()`decorador](https://langfuse.com/docs/sdk/python/decorators) para Python
    - [Integrações](https://langfuse.com/docs/integrations/overview) para OpenAI SDK, Langchain, LlamaIndex, LiteLLM, Flowise e Langflow
    - [API](https://api.reference.langfuse.com/)
- **Langfuse UI:** inspecionar e depurar logs complexos e sessões de usuário ( [demonstração](https://langfuse.com/docs/demo) , [rastreamento](https://langfuse.com/docs/tracing) , [sessões](https://langfuse.com/docs/tracing-features/sessions) )
- **Gerenciamento de prompts:** gerencie, versione e implante prompts de dentro do Langfuse ( [Gerenciamento de prompts](https://langfuse.com/docs/prompts/get-started) )
- **Engenharia de prompts:** teste e itere seus prompts com o [LLM Playground](https://langfuse.com/docs/playground)

### Monitor[](https://langfuse.com/docs#monitor)

- **Análise:** rastreie métricas (custo de LLM, latência, qualidade) e obtenha insights de painéis e exportações de dados ( [Analytics](https://langfuse.com/docs/analytics) , [Daily Metrics API](https://langfuse.com/docs/analytics/daily-metrics-api) )
- **Avaliações:** colete e calcule pontuações para suas conclusões de LLM ( [Pontuações e avaliações](https://langfuse.com/docs/scores) )
    - Execute [avaliações baseadas em modelos](https://langfuse.com/docs/scores/model-based-evals/overview) no Langfuse
    - Coletar [feedback do usuário](https://langfuse.com/docs/scores/user-feedback)
    - [Anotar](https://langfuse.com/docs/scores/annotation) observações no Langfuse
- ## O que é avaliação LLM?[](https://langfuse.com/docs/scores/overview#what-is-llm-evaluation)

A avaliação é um aspecto crítico do desenvolvimento e da implantação de aplicativos LLM. Normalmente, as equipes usam uma infinidade de métodos de avaliação diferentes para pontuar o desempenho de seu aplicativo de IA, dependendo do caso de uso e do estágio do processo de desenvolvimento.

O Langfuse fornece um [sistema de pontuação](https://langfuse.com/docs/scores/getting-started) flexível para capturar todas as suas avaliações em um só lugar e torná-las acionáveis.


Como usar [[LangFusePratica]]

- baixar o repositorio
- adicionar o arquivo de .env
- preencher a variavel de email
- rodar docker compose up

acessar o link [[LangFusePratica]] 


ele consegue criar prompts e testa no playgrand


api https://api.reference.langfuse.com/#tag--DatasetItems

cliditas -a langfuse -c main render -k deploy/staging


