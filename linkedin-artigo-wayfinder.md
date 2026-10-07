# Rascunho — artigo LinkedIn

**Sugestão de título:** Um bucket S3 com 2.340 laudos médicos ficou público por 18 dias. Eu construí o sistema que detecta isso em menos de 5 minutos.

**Formato:** artigo nativo no LinkedIn (colar o texto abaixo).  
**Hashtags no final.** Não publicar automaticamente — revisar datas, números e tom.

---

Um bucket S3 com **2.340 laudos médicos** ficou público por **18 dias**.

Ninguém no time de cloud percebeu. A ANPD percebeu. Multa: R$ 420 mil. Impacto total estimado: R$ 2,1 milhões.

Esse é o incidente de partida do cenário **VitaCore Health** — saúde digital, dado sensível, conta AWS “que já funcionava”. Não é um tutorial de certificação. É o tipo de falha que aparece quando Block Public Access está desligado, quando não há regra de Config, quando o alarme não existe e quando a correção depende de alguém abrir o console.

Eu construí o **Wayfinder Cloud** para esse problema.

Não é um dashboard bonito. É governança contínua:

- **AWS Config** com regras custom (WAYFINDER-001 a 014), cada uma mapeada a um artigo da LGPD  
- **EventBridge** dispara no `NON_COMPLIANT`  
- **Lambda (Python 3.12)** avalia, registra e — nas violações críticas — **remedia com guardrail**  
- **KMS CMK**, **S3 Object Lock**, **CloudTrail**, **GuardDuty**, **Security Hub**  
- Consulta da trilha com **Athena**  
- Infraestrutura em **Terraform** (8 módulos), state remoto, **GitHub Actions com OIDC** (sem access key)  
- **115 testes** com moto/pytest  

Detecção alvo: **menos de 5 minutos**. Sem click-ops no caminho feliz.

O que os 23 labs da Escola da Nuvem me deram foi o vocabulário (VPC, IAM, KMS, Config, Lambda). O que o Wayfinder me forçou foi **decisão**: o que auto-remediar, o que só alertar, como não apagar evidência, como não colocar chave de longa duração no CI.

Nove ADRs documentam o “porquê”. Cinco runbooks documentam o “e se quebrar”.

Se você contrata Cloud / Security / DevOps júnior ou pleno e quer ver código, não slide:

Portfólio: https://guinatural.github.io  
Case: https://guinatural.github.io/wayfinder.html  
Labs: https://guinatural.github.io/labs.html  
Repo: https://github.com/guinatural/wayfinder-cloud

Aberto a conversas sobre Cloud Engineer, DevOps e AWS Solutions Architect.

#AWS #LGPD #CloudSecurity #Terraform #DevOps #Compliance #SolutionsArchitect

---

## Notas de publicação

1. O incidente VitaCore é **cenário de projeto** (estudo / portfólio). Se o LinkedIn pedir clareza, acrescente no segundo parágrafo: *“cenário de estudo, inspirado em falhas reais de exposição de dado de saúde.”*  
2. Confira se o Pages já serve `labs.html` depois do próximo push.  
3. Primeiro comentário (alto alcance): uma frase só — “O repositório tem os 9 ADRs e os testes. Pode clonar e rodar `pytest`.”  
4. Imagem: captura do case (`wayfinder.html`) ou diagrama de Config → EventBridge → Lambda. Sem print de dado de paciente.  
5. Não cite multa ANPD como fato jornalístico da VitaCore; deixe explícito que é o **modelo de impacto do exercício**.
