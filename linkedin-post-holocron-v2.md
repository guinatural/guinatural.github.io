# Rascunho — post LinkedIn (Holocron Sentinel V2)

**Formato:** post curto (não artigo). Colar no LinkedIn.
**Gancho original:** “Quando a I.A. para de conversar e começa a trabalhar.”  
**Não confundir com o Wayfinder:** este case explora um agente acionado sob demanda (Boto3 + Bedrock). O Wayfinder explora avaliação de configuração orientada a eventos.

---

Quando a I.A. para de conversar e começa a trabalhar.

Parei de só consumir conteúdo e passei a documentar projetos de portfólio para praticar AWS e IA generativa. O **Holocron Sentinel / AgentCore** é o capstone; o **Sentinel V2** fica em um repositório separado.

O capstone explora um agente de auditoria AWS: **Amazon Bedrock** (Claude via Strands) e ferramentas **Boto3**. O repositório e o case descrevem uma prova de conceito; não é um serviço multi-tenant em produção.

**1 — Due diligence em uma passagem**
O agente orquestra, na mesma sessão:

- perímetro: Security Groups com SSH (22) ou protocolo `-1` aberto em `0.0.0.0/0`
- identidade: usuários IAM **sem MFA**
- FinOps: volumes **EBS available** (não anexados), custo ocioso
- (e S3 sem Block Public Access, no mesmo kit de scanners)

Isso é o lab de SG, o lab de IAM e o hábito do Boto3 (labs 04, 03/identidade, 19) **em ferramenta**, não em tutorial.

**2 — Sessões e limites de isolamento**
O desenho usa `tenant_id` na identificação da sessão. Isso ajuda a organizar o estado, mas **não prova isolamento entre clientes**: autorização, validação de caminhos, permissões de armazenamento e proteção dos dados também precisam ser testadas.

O projeto é uma prova de conceito e material de estudo, não uma oferta de consultoria pronta nem um produto implantado. O Wayfinder Cloud é outro eixo do portfólio — uma arquitetura de governança orientada a eventos.

Portfólio: https://guinatural.github.io
Labs (de onde veio o padrão): https://guinatural.github.io/labs.html
Capstone AgentCore: https://github.com/guinatural/Holocron-Sentinel-AWS-AgentCore
Sentinel V2: https://github.com/guinatural/Holocron-Sentinel-Startup-V2

#AWS #EscolaDaNuvem #DevSecOps #AmazonBedrock #Boto3 #ZeroTrust #FinOps #LGPD #Python

---

## Notas (não colar)

1. Distinguir os repositórios do capstone AgentCore e do Sentinel V2.
2. Não afirmar que um `session_id` isolado, sozinho, impede vazamento entre tenants.
3. Antes de publicar detalhes de implementação, conferir o estado atual de cada repositório.
4. Distinguir Holocron (agente sob demanda) de Wayfinder (arquitetura de governança orientada a eventos).
