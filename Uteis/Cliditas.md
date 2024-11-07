---
Descricao: O que é Cliditas e alguns comandos uteis
tags:
  - cliditas
Url: https://creditas.dev/docs/default/component/cliditas/howto/troubleshooting/
Data: " 2024-10-02"
---

Cliditas é uma ferramenta com as melhores práticas de implantação de Apps no ambiente AWS da Creditas.
Ele é composto com algumas ferramentas OpenSource como Kubernets usando o EKS da AWS), Prometheus e DataDog(Observability).

### Estrutura de diretório

Para utilizar o cliditas o seu projeto no GitHub precisa conter um arquivo Dockerfile em sua raiz:
├── ProjetoName
├── Dockerfile 
├── requirements.txt
├── app.py

https://github.com/Creditas/cliditas/blob/master/docs/tutorials/creating_a_manifest.md


buscar variavel
cliditas init --squad= tribe= 

cliditas config get ROLE
cliditas config list
cliditas -a app -n namespace -c master cfg get variavel
cliditas -a app -n namespace -c master cfg list

setar variaveis
cliditas config set ENV prod
cliditas config -a fagocitas set SLACK_URL https://hooks.slack.com/services/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

ver os pods
cliditas -a fagocitas -n fagocitas -c master explore

ver os logs
cliditas -a langfuse -n langfuse logs

Criar DLC
cliditas -a langfuse -c master dlc apply -f deploy/prod/dlc/serviceaccount.yaml --yes

cliditas -a langfuse -c main render -k deploy/staging

kubectl get namespace langfuse --show-labels

kubectl get pods -n langfuse
kubectl logs -f pod/lang-f044-web-6b6f7fd8cb-nmr45 -n langfuse

kubectl get replicaset -n langfuse
kubectl describe replicaset lang-f044-web-66945f5d65 -n langfuse

kubectl -n langfuse get events

kubectl -n langfuse get all

kubectl -n langfuse describe ingress lang-f044-f2f4d7c8

