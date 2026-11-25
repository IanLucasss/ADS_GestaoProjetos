# Análise de Riscos do Projeto — FieldOps

> **Disciplina:** Gestão de Projetos — 4º semestre ADS
> **Professor:** Me. Deivison S. Takatu
> **Aula 07:** Riscos — Atividade de Análise de Riscos
> **Projeto:** FieldOps — Plataforma de Inspeção em Campo
> **Equipe:** 404 Not Found
> **Data:** 25/09/2026

---

## 1. Objetivo

Neste documento está reunida a **Análise de Riscos do Projeto FieldOps**, construída de acordo com o processo de **Gerenciamento dos Riscos do Projeto** previsto no PMBOK (área 11). O processo percorre cinco etapas: planejar o gerenciamento dos riscos, identificá-los, executar as análises qualitativa e quantitativa, planejar as respostas e, por fim, controlar os riscos.

A base da análise são os artefatos que a equipe já produziu ao longo das aulas — o **Termo de Abertura do Projeto (TAP)**, a **EAP**, o **Cronograma**, o **Orçamento** (cuja linha de base é de R$ 204.000,00) e a **Análise da Qualidade**. Foi justamente nessa análise de qualidade que a **sincronização offline** apareceu como o ponto mais sensível do sistema. Os 12 riscos registrados no TAP foram agrupados nos riscos deste documento, conforme a coluna "Riscos do TAP" na seção 5.

Cada risco é descrito por **causa, risco (o evento em si) e consequência**, na linha do que foi orientado em aula: evitar registros vagos do tipo "o projeto pode atrasar".

---

## 2. Definição das Escalas

### 2.1 Escala de Probabilidade

| Nível | Classificação | Valor | Descrição |
|---|---|:---:|---|
| 1 | Muito baixa | 0,10 | Improvável de ocorrer no período do projeto |
| 2 | Baixa | 0,30 | Pode ocorrer, mas não é esperado |
| 3 | Média | 0,50 | Tão provável quanto improvável |
| 4 | Alta | 0,70 | Esperado que ocorra em algum momento |
| 5 | Muito alta | 0,90 | Quase certo de ocorrer |

### 2.2 Escala de Impacto

| Nível | Classificação | Valor | Prazo | Custo | Escopo/Qualidade |
|---|---|:---:|---|---|---|
| 1 | Muito baixo | 0,05 | Atraso desprezível | < 1% do orçamento | Impacto imperceptível |
| 2 | Baixo | 0,10 | Atraso de 1–2 dias | 1–3% do orçamento | Áreas secundárias afetadas |
| 3 | Moderado | 0,20 | Atraso de 3–5 dias | 3–7% do orçamento | Áreas principais afetadas |
| 4 | Alto | 0,40 | Atraso de 1–2 semanas | 7–15% do orçamento | Redução relevante do escopo |
| 5 | Muito alto | 0,80 | Inviabiliza a entrega | > 15% do orçamento | Produto final inutilizável |

> Para definir o nível de impacto de cada risco, considera-se a dimensão **mais grave** entre prazo, custo e escopo/qualidade. É por isso que um risco pode ter impacto alto em escopo/qualidade e, ainda assim, um custo de resposta pequeno (seção 7).

### 2.3 Matriz de Severidade (Probabilidade x Impacto)

A severidade resulta da multiplicação **Probabilidade × Impacto** e é classificada por faixa de cor:

| P \ I | 0,05 (MB) | 0,10 (B) | 0,20 (M) | 0,40 (A) | 0,80 (MA) |
|:---:|:---:|:---:|:---:|:---:|:---:|
| **0,90 (MA)** | 🟢 0,05 | 🟡 0,09 | 🟠 0,18 | 🔴 0,36 | 🔴 0,72 |
| **0,70 (A)** | 🟢 0,04 | 🟡 0,07 | 🟠 0,14 | 🔴 0,28 | 🔴 0,56 |
| **0,50 (M)** | 🟢 0,03 | 🟢 0,05 | 🟡 0,10 | 🟠 0,20 | 🔴 0,40 |
| **0,30 (B)** | 🟢 0,02 | 🟢 0,03 | 🟡 0,06 | 🟠 0,12 | 🟠 0,24 |
| **0,10 (MB)** | 🟢 0,01 | 🟢 0,01 | 🟢 0,02 | 🟢 0,04 | 🟡 0,08 |

**Legenda:** 🟢 Baixo (≤ 0,05) · 🟡 Moderado (0,06–0,11) · 🟠 Alto (0,12–0,24) · 🔴 Crítico (≥ 0,25)

---

## 3. Estratégias de Resposta aos Riscos

Seguindo o processo *11.5 — Planejar as respostas aos riscos*, adotamos as seguintes estratégias:

**Para ameaças (riscos negativos):**
- **Prevenir (eliminar):** eliminar a causa do risco ou proteger o projeto contra seu impacto.
- **Transferir:** repassar o impacto a um terceiro (ex.: serviço gerenciado).
- **Mitigar:** diminuir a probabilidade e/ou o impacto até um nível aceitável.
- **Aceitar:** não agir de forma preventiva, tratando o risco somente caso ocorra (com ou sem reserva de contingência).

**Para oportunidades (riscos positivos):**
- **Explorar, Melhorar, Compartilhar, Aceitar.**

---

## 4. Registro de Riscos (Causa → Risco → Consequência)

### R01 — Perda/inconsistência de respostas na sincronização offline
- **Causa:** O reenvio de respostas não é idempotente e as regras de conflito entre o app mobile e a API estão mal definidas; o técnico ainda trabalha em locais sem cobertura de internet.
- **Risco:** Ao sincronizar com o servidor, as respostas gravadas offline podem sumir ou aparecer duplicadas.
- **Consequência:** Há retrabalho de inspeção, dados inconsistentes e atraso na aprovação e na entrega do MVP.

### R02 — Indisponibilidade dos serviços de nuvem de terceiros
- **Causa:** O projeto depende de hospedagem em nuvem, de um banco PostgreSQL gerenciado, do armazenamento de evidências e de um serviço de notificações push, todos contratados de fornecedores externos.
- **Risco:** Durante o desenvolvimento ou a demonstração, os serviços de nuvem que abrigam a API podem ficar indisponíveis.
- **Consequência:** Os testes integrados ficam bloqueados, o cronograma atrasa e há risco de a demo ponta a ponta falhar (PBI-072).

### R03 — Falha de autenticação e gestão de sessão (token)
- **Causa:** Implementar JWT com refresh token e autorização por perfil traz complexidade (PBI-007, PBI-010, PBI-012).
- **Risco:** Usuários podem perder a sessão sem motivo ou acessar recursos para os quais não têm permissão.
- **Consequência:** Aparecem falhas de segurança, os técnicos ficam impedidos de usar o sistema e é preciso refazer a correção.

### R04 — Subestimação de esforço nos pacotes de maior incerteza
- **Causa:** As estimativas de três pontos mostraram alta variação em três pacotes: sincronização offline, construtor de modelos e checklist dinâmico.
- **Risco:** O esforço real nesses pacotes pode passar do estimado.
- **Consequência:** Há estouro de horas, consumo da reserva de contingência (R$ 14.740,00) e pressão sobre o prazo das sprints.

### R05 — Indisponibilidade de membros da equipe
- **Causa:** A equipe é acadêmica, com 9 integrantes que conciliam o projeto com outras disciplinas, e o conhecimento fica concentrado em poucas pessoas.
- **Risco:** Em momentos críticos das sprints, um ou mais integrantes podem ficar indisponíveis.
- **Consequência:** Os demais ficam sobrecarregados, PBIs dependentes atrasam e há perda de conhecimento (bus factor).

### R06 — Defeitos em checklists com muitos itens
- **Causa:** A Aula 05 identificou uma correlação positiva: quanto mais itens no checklist, mais defeitos por inspeção.
- **Risco:** Modelos de inspeção grandes tendem a apresentar mais falhas de validação e de desempenho no mobile.
- **Consequência:** Não conformidades deixam de ser detectadas, inspeções são reprovadas e o cliente fica insatisfeito.

### R07 — Falha no upload de evidências (fotos)
- **Causa:** A rede é instável e não há tratamento para foto pendente (PBI-044).
- **Risco:** As fotografias podem não ser enviadas ou podem ficar desvinculadas do item correto.
- **Consequência:** As inspeções ficam sem a comprovação da não conformidade, o que compromete a auditoria e a qualidade da entrega.

### R08 — Atraso na build/entrega para demonstração
- **Causa:** As tarefas de fechamento (seed, Docker, build APK, demo) estão concentradas no fim da Sprint 2, e as funcionalidades P1 e a homologação final, na Sprint 3.
- **Risco:** Os builds de demonstração (APK Android e painel web) podem não ficar prontos a tempo.
- **Consequência:** Ficam comprometidos os marcos "MVP funcional P0" (02/10/2026, fim da Sprint 2) e "Entrega final com P1" (24/11/2026, fim da Sprint 3).

### R09 — Alterações de escopo durante o desenvolvimento
- **Causa:** Novas funcionalidades ou mudanças de requisitos entram sem passar pelo controle de mudanças.
- **Risco:** O escopo cresce além do backlog planejado para as sprints.
- **Consequência:** Aumenta a complexidade e atrasam as funcionalidades prioritárias (P0) do MVP.

### R10 — Falhas de integração e dependência entre frentes
- **Causa:** Backend, Web e Mobile são desenvolvidos em paralelo e dependem do mesmo contrato de API e do mesmo modelo de dados.
- **Risco:** Se o contrato da API divergir do que Web e Mobile consomem, ou se uma frente atrasar, as demais podem ficar bloqueadas.
- **Consequência:** Há retrabalho de integração e não é possível testar o fluxo completo da inspeção no prazo.

### R11 — Incompatibilidade de dispositivos e recursos indisponíveis
- **Causa:** Há diferenças entre versões e modelos de Android, além de permissões negadas de câmera, QR Code ou geolocalização.
- **Risco:** O aplicativo pode se comportar de modo diferente entre dispositivos ou perder funções de evidência.
- **Consequência:** Falham a captura de fotos, a leitura de QR Code ou o registro de localização durante a inspeção.

### R12 — Baixa qualidade das informações coletadas
- **Causa:** A interface é pouco clara para o uso em campo ou as validações dos componentes de resposta são insuficientes.
- **Risco:** Os técnicos podem registrar respostas incompletas ou incorretas.
- **Consequência:** Inspeções são reprovadas, há retrabalho em campo e os supervisores perdem a confiança nos dados.

---

## 5. Análise Qualitativa (Probabilidade × Impacto)

Os riscos foram ordenados pela severidade (P × I), do maior para o menor:

| ID | Risco | Riscos do TAP | Prob. | Impacto | Severidade (P×I) | Classificação |
|---|---|:---:|:---:|:---:|:---:|:---:|
| R01 | Perda na sincronização offline | 1, 2, 3 | 0,70 | 0,80 | **0,56** | 🔴 Crítico |
| R03 | Falha de autenticação/sessão | 8 | 0,50 | 0,40 | **0,20** | 🟠 Alto |
| R08 | Atraso na build para demo | 12 | 0,50 | 0,40 | **0,20** | 🟠 Alto |
| R10 | Integração e dependência entre frentes | 4, 10 | 0,50 | 0,40 | **0,20** | 🟠 Alto |
| R02 | Indisponibilidade da nuvem de terceiros | — | 0,30 | 0,40 | **0,12** | 🟠 Alto |
| R05 | Indisponibilidade da equipe | — | 0,30 | 0,40 | **0,12** | 🟠 Alto |
| R04 | Subestimação de esforço | 12 | 0,50 | 0,20 | **0,10** | 🟡 Moderado |
| R06 | Defeitos em checklists grandes | 11 | 0,50 | 0,20 | **0,10** | 🟡 Moderado |
| R09 | Alterações de escopo | 9 | 0,50 | 0,20 | **0,10** | 🟡 Moderado |
| R07 | Falha no upload de evidências | 5 | 0,30 | 0,20 | **0,06** | 🟡 Moderado |
| R11 | Incompatibilidade de dispositivos/recursos | 6, 7 | 0,30 | 0,20 | **0,06** | 🟡 Moderado |
| R12 | Baixa qualidade das informações coletadas | 11 | 0,30 | 0,20 | **0,06** | 🟡 Moderado |

> **Análise:** apenas o **R01 (sincronização offline)** é **crítico** e, por isso, concentra a maior atenção — o que é coerente com a Análise da Qualidade (Aula 05), em que essa categoria liderou o Diagrama de Pareto (35% dos defeitos). Já os riscos **altos** (R02, R03, R05, R08, R10) referem-se a dependências externas, segurança, pessoas, integração entre frentes e ao fechamento do cronograma.

---

## 6. Análise Quantitativa (Valor Monetário Esperado)

Pelo processo *11.4 — Realizar a análise quantitativa dos riscos*, cada risco recebe um **custo estimado caso ocorra**, obtido em horas de retrabalho ao custo-hora de desenvolvimento do orçamento (R$ 50,00). O **Valor Monetário Esperado (VME)** é a probabilidade multiplicada por esse custo:

```
VME = Probabilidade × Custo se ocorrer
```

| ID | Probabilidade | Horas de retrabalho | Custo se ocorrer (R$) | VME (R$) |
|---|:---:|:---:|---:|---:|
| R01 | 0,70 | 160 h | 8.000,00 | 5.600,00 |
| R02 | 0,30 | 40 h | 2.000,00 | 600,00 |
| R03 | 0,50 | 60 h | 3.000,00 | 1.500,00 |
| R04 | 0,50 | 80 h | 4.000,00 | 2.000,00 |
| R05 | 0,30 | 60 h | 3.000,00 | 900,00 |
| R06 | 0,50 | 20 h | 1.000,00 | 500,00 |
| R07 | 0,30 | 30 h | 1.500,00 | 450,00 |
| R08 | 0,50 | 30 h | 1.500,00 | 750,00 |
| R09 | 0,50 | 30 h | 1.500,00 | 750,00 |
| R10 | 0,50 | 40 h | 2.000,00 | 1.000,00 |
| R11 | 0,30 | 20 h | 1.000,00 | 300,00 |
| R12 | 0,30 | 26 h | 1.300,00 | 390,00 |
| **Total** | | | **29.800,00** | **14.740,00** |

> **Análise:** o VME total de **R$ 14.740,00** corresponde à reserva de contingência do orçamento (Aula 05). O R01 sozinho responde por 38% do VME, o que confirma a priorização feita na análise qualitativa.

---

## 7. Plano de Respostas aos Riscos

| ID | Estratégia | Ações de resposta | Responsável | Gatilho de monitoramento |
|---|---|---|---|---|
| R01 | **Mitigar** | Garantir a idempotência no reenvio (PBI-052), estabelecer as regras de conflito (PBI-055), manter uma fila outbox persistente (PBI-050) e aplicar testes automatizados nos fluxos críticos (PBI-065). | Lucas / Marcela / Felipe | Taxa diária de falha de sync > 13,7% (LSC do gráfico de controle da Aula 05) |
| R02 | **Transferir / Mitigar** | Adotar serviços gerenciados com SLA e preparar um ambiente de contingência local (Docker) para a demo (PBI-070). | Júlia / Marcela | Indisponibilidade > 1h em ambiente de homologação |
| R03 | **Prevenir** | Fazer a revisão de segurança do fluxo JWT com refresh; realizar testes de autorização por perfil; e adotar a renovação automática de sessão (PBI-010). | Lucas | Erros de sessão reportados nos testes |
| R04 | **Mitigar / Aceitar** | Monitorar as horas por pacote e acionar a reserva de contingência (R$ 14.740,00) quando o esforço de um pacote ultrapassar o estimado. | Natália (GP) | Consumo de horas > 110% do estimado no pacote |
| R05 | **Mitigar** | Programar em par, manter a documentação (READMEs — PBI-067) e distribuir o conhecimento entre as frentes. | Natália (GP) | Ausência não planejada > 2 dias |
| R06 | **Mitigar** | Aplicar testes de regressão para checklists com mais de 25 itens e fazer validação e prévia antes de publicar (PBI-022). | Júlia / Andressa (Web) e Rodrigo (testes mobile — PBI-065) | Nº de defeitos por inspeção acima da tendência |
| R07 | **Mitigar** | Marcar a foto como pendente e reenviá-la (PBI-044); associar a fotografia ao item correto (PBI-043). | Natália / Rodrigo | Fotos pendentes acumuladas na outbox |
| R08 | **Prevenir** | Congelar o escopo P0 antes do fim da Sprint 2; ensaiar a demo ponta a ponta (PBI-072) antes do marco de 02/10; e, na Sprint 3, reservar o período de homologação antes da entrega de 24/11. | Equipe completa | Marco em risco na revisão de sprint |
| R09 | **Mitigar** | Manter os itens P1 como opcionais (conforme a EAP); toda mudança de escopo deve passar pela gerente antes de entrar no backlog. | Natália (GP) | PBI novo adicionado fora do planejamento da sprint |
| R10 | **Mitigar** | Adotar o contrato OpenAPI primeiro, com dados simulados para os frontends (PBI-006); e fazer coordenação técnica semanal entre os líderes. | Marcela / Júlia / Natália | Endpoint divergente do contrato ou frente bloqueada > 2 dias |
| R11 | **Mitigar** | Testar em 2 dispositivos Android diferentes (orçamento D1) e tratar as permissões negadas com uma mensagem que oriente o técnico. | Rodrigo / Felipe | Falha de câmera, QR Code ou GPS em algum dispositivo de teste |
| R12 | **Mitigar** | Aplicar validação de obrigatórios no mobile (PBI-040), componentes de resposta por tipo de item (PBI-036) e a revisão do supervisor (PBI-057). | Natália / Rodrigo (Mobile) e Carol (Web) | Inspeções reprovadas por dados incompletos |

---

## 8. Reserva de Contingência

A **reserva de contingência de R$ 14.740,00** do Orçamento (Aula 05), que equivale a **~7,8% dos custos diretos e 7,2% do total geral**, é igual ao VME total calculado na seção 6. Os riscos que mais pesam nessa reserva são:

| Risco | VME (R$) | Uso previsto da reserva |
|---|---:|---|
| R01 — Sincronização offline | 5.600,00 | Retrabalho e testes adicionais de sincronização/idempotência |
| R04 — Subestimação de esforço | 2.000,00 | Horas adicionais nos pacotes de checklist dinâmico e construtor de modelos |
| R03 — Autenticação/sessão | 1.500,00 | Correções de segurança e ajustes de autorização |
| R10 — Integração entre frentes | 1.000,00 | Retrabalho de integração entre API, Web e Mobile |
| Demais riscos (R02, R05–R09, R11, R12) | 4.640,00 | Retrabalho pontual caso ocorram |
| **Total** | **14.740,00** | |

---

## 9. Considerações Finais

- Foram identificados **12 riscos**: **1 crítico** (R01 — sincronização offline), **5 altos** (R02, R03, R05, R08, R10) e **6 moderados** (R04, R06, R07, R09, R11, R12). Todos são descritos no formato **causa → risco → consequência** e cobrem os riscos registrados no TAP.
- O risco crítico coincide com as conclusões da **Análise da Qualidade (Aula 05)**, o que reforça a coerência entre os artefatos do FieldOps.
- A análise quantitativa (VME) dimensiona a reserva de contingência do orçamento, conectando riscos e custos.
- As respostas dão prioridade à **prevenção e à mitigação** dos riscos de maior severidade, com **gatilhos de monitoramento** objetivos vinculados aos indicadores já definidos (ex.: LSC de falhas de sincronização).
- Ao longo das sprints, este registro de riscos deverá ser **monitorado no processo 11.6 — Controlar os riscos**, com revisão de probabilidades, impactos e da eficácia das respostas, além do registro de eventuais riscos residuais e de novos riscos.
