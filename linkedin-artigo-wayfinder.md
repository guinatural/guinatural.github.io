# Rascunho — artigo LinkedIn

**Sugestão de título:** Como transformei um cenário hipotético de exposição de dados em um exercício de arquitetura AWS

**Formato:** artigo nativo no LinkedIn (colar o texto abaixo).  
**Hashtags no final.** Não publicar automaticamente — revisar datas, números e tom.

---

**VitaCore Health é um cenário hipotético**, criado para explorar um problema de governança: como identificar e tratar configurações que podem expor dados sensíveis. Não é um incidente real, e os materiais não afirmam multa, impacto financeiro, implantação produtiva ou tempo de detecção medido.

O **Wayfinder Cloud** é meu projeto de portfólio para estudar esse desenho. No repositório e no case, organizo uma arquitetura orientada a eventos com:

- **AWS Config** para avaliar regras de configuração
- **EventBridge** para roteamento de eventos
- **Lambda** para processar achados e aplicar guardrails propostos
- **CloudTrail, S3 Object Lock e Athena** como componentes considerados para auditoria
- **Terraform** e **GitHub Actions com OIDC** como práticas de infraestrutura e automação

O foco foi registrar decisões: quando uma ação automática pode ser arriscada? Quais controles precisam de revisão humana? Como evitar credenciais de longa duração no CI? As respostas do projeto são hipóteses técnicas que precisam ser validadas no ambiente em que forem aplicadas.

Os laboratórios AWS ajudaram a praticar VPC, IAM, KMS, Config e Lambda. No Wayfinder, o exercício foi relacionar esses serviços a requisitos e explicitar trade-offs, em vez de tratar a lista de serviços como arquitetura pronta.

Se você contrata Cloud / Security / DevOps júnior ou pleno e quer ver código, não slide:

Portfólio: https://guinatural.github.io  
Case: https://guinatural.github.io/wayfinder.html  
Labs: https://guinatural.github.io/labs.html  
Repo: https://github.com/guinatural/wayfinder-cloud

Aberto a conversas sobre Cloud Engineer, DevOps e AWS Solutions Architect.

#AWS #LGPD #CloudSecurity #Terraform #DevOps #Compliance #SolutionsArchitect

---

## Notas de publicação

1. Manter explícito que VitaCore é um cenário hipotético.
2. Antes de publicar qualquer quantidade, prazo, custo ou resultado de teste, conferir o dado no repositório e descrever como foi medido.
3. Não apresentar o desenho ou o case como serviço implantado, SLA ou garantia de conformidade.
4. Usar apenas capturas do projeto sem dados pessoais ou credenciais.
