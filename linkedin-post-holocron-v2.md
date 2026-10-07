# Rascunho — post LinkedIn (Holocron Sentinel V2)

**Formato:** post curto (não artigo). Colar no LinkedIn.  
**Gancho original:** “Quando a I.A. para de conversar e começa a trabalhar.”  
**Não confundir com o Wayfinder:** aqui o agente **consulta a conta agora** (Boto3 + Bedrock). Lá, Config **vigia o tempo todo**.

---

Quando a I.A. para de conversar e começa a trabalhar.

Parei de só consumir conteúdo e construí o **Holocron Sentinel V2** — capstone da Escola da Nuvem, agora com o próximo passo na trilha **AWS Developer**.

Não é chatbot. É um agente de auditoria AWS: **Amazon Bedrock** (Claude via Strands) chama ferramentas **Boto3** reais. Um prompt dispara o trabalho. O relatório sai em PDF, no tenant certo.

**1 — Due diligence em uma passagem**  
O agente orquestra, na mesma sessão:

- perímetro: Security Groups com SSH (22) ou protocolo `-1` aberto em `0.0.0.0/0`  
- identidade: usuários IAM **sem MFA**  
- FinOps: volumes **EBS available** (não anexados), custo ocioso  
- (e S3 sem Block Public Access, no mesmo kit de scanners)

Isso é o lab de SG, o lab de IAM e o hábito do Boto3 (labs 04, 03/identidade, 19) **em ferramenta**, não em tutorial.

**2 — Partição de memória (teste de vazamento)**  
Sessão **Empresa Alpha** gera cache de auditoria. Sessão **Empresa Beta** pede o dado da rival por prompt injection.

Bloqueio: cada tenant tem `FileSessionManager` com `session_id` próprio (`empresa_{tenant_id}`). O modelo não herda o contexto do outro cliente. LGPD aqui é **isolamento de sessão**, não um parágrafo na política.

PoC que escala **como produto de consultoria**: cada scanner vira um serviço (hardening, FinOps, perímetro). O mapa labs → oferta está no repositório. Wayfinder Cloud é outro eixo — governança contínua com Config e Terraform.

Portfólio: https://guinatural.github.io  
Labs (de onde veio o padrão): https://guinatural.github.io/labs.html  
Código: https://github.com/guinatural/Holocron-Sentinel-AWS-AgentCore

#AWS #EscolaDaNuvem #DevSecOps #AmazonBedrock #Boto3 #ZeroTrust #FinOps #LGPD #Python

---

## Notas (não colar)

1. “SaaS” no post original: o núcleo é agente + sessão em disco. Pode dizer SaaS *como desenho* (tenant_id em tudo); não diga “multi-tenant em produção na AWS” se ainda é PoC local/AgentCore.  
2. “6 Gigs ativos”: no material interno isso é **catálogo de linhas de serviço** (backup, bill shock, hardening, tuning, HA, IaC), não necessariamente seis contratos fechados. Se não houver seis clientes atuais, use a frase do rascunho acima.  
3. SOC2: MFA sem MFA é risco de identidade; não precisa citar SOC2 se o avaliador for pedante. LGPD + menor privilégio basta.  
4. Distinguir **Holocron** (agente sob demanda) de **Wayfinder** (Config 24/7) — quem lê os dois posts no perfil não deve achar que é o mesmo repo.  
5. Link `lnkd.in/dvkiisuR`: manter se ainda aponta para o GitHub/vitrine; senão trocar pelos URLs do Pages.
