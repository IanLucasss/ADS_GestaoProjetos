# Gerenciamento das Aquisições do Projeto — FieldOps

> **Disciplina:** Gestão de Projetos — 4º semestre ADS
> **Professor:** Me. Deivison S. Takatu
> **Aula 08:** Aquisições e Partes Interessadas — Atividade de Aquisições
> **Projeto:** FieldOps — Plataforma de Inspeção em Campo
> **Equipe:** 404 Not Found
> **Data:** 23/10/2026

---

## 1. Objetivo

Este documento reúne o **Gerenciamento das Aquisições do Projeto FieldOps**, organizado de acordo com a área 12 do PMBOK — **Gerenciamento das Aquisições do Projeto** —, que compreende quatro processos: planejar as aquisições, conduzi-las, controlá-las e encerrá-las.

A tabela de aquisições descreve **o que precisa ser comprado ou contratado**, indicando para cada item a urgência, o motivo da compra, os fornecedores em potencial, a quantidade, o custo unitário, o custo total e o responsável pela aquisição. As estimativas partem do Orçamento do Projeto — cuja linha de base autorizada é de **R$ 204.000,00** — e dos demais artefatos já produzidos pela equipe.

---

## 2. Planejamento das Aquisições

Antes de partir para a condução das aquisições, a equipe observou as etapas a seguir (PMBOK 12.1):

- **Especificar as características** da solução que será contratada para cada item.
- **Elaborar uma estimativa** de custo para integrar o orçamento.
- **Divulgar a oportunidade** de contratação e identificar fornecedores qualificados.
- **Receber e avaliar as propostas** dos fornecedores em potencial.

### 2.1 Escala de urgência

| Nível | Classificação | Descrição | Momento necessário |
|:--:|---|---|---|
| **5** | Muito Alta | Item crítico que bloqueia o funcionamento do sistema ou da demonstração sem ele. | Antes/no início da Sprint 1 |
| **4** | Alta | Exigido logo no início de uma frente de desenvolvimento. | Início da Sprint 1 |
| **3** | Média | Exigido ao longo do desenvolvimento, mas admite alternativa temporária. | Durante a Sprint 1 / início da Sprint 2 |
| **2** | Baixa | Exigido apenas nas fases finais (demonstração/entrega). | Sprint 2 / fechamento |
| **1** | Muito Baixa | Item complementar, sem efeito sobre o andamento do projeto. | Quando conveniente |

---

## 3. Tabela de Gerenciamento das Aquisições — FieldOps

> Estrutura adotada conforme o modelo da disciplina. **Cód. EAP** indica o pacote de trabalho ou subentrega da [EAP](../Aula%2003%20-%2021.08.2026/aula03-EAP.pdf) (Aula 03) que o item atende. **Cód. orçamento** refere-se ao item equivalente no [Orçamento](../Aula%2005%20-%2004.09.2026/aula05-orcamento-custos.md) (Aula 05), em que **B** = Infraestrutura e Nuvem, **C** = Ferramentas e Licenças e **D** = Equipamentos e Materiais. Legenda da coluna Qtde: **mês** = assinatura mensal ao longo dos cerca de 2 meses do projeto · **un** = unidade · **lic** = licença por integrante.

| ID | Cód. EAP | Cód. orçamento | Item a ser adquirido | Urgência | Motivo da Decisão de Compra | Fornecedores potenciais | Qtde | Custo unitário | Custo total | Previsão entrega | Observações |
|:--:|:--:|:--:|---|---|---|---|:--:|---:|---:|---|---|
| 1 | 4.1.1 | B1 | Servidor de aplicação (hospedagem da API Spring Boot) | 5-Muito Alta | Serve para hospedar a API, permitindo rodar os testes integrados e a demonstração de ponta a ponta. | AWS, Google Cloud, Render, Railway | 2 mês | R$ 180,00 | R$ 360,00 | Sprint 1 | Responsável: Júlia (PBI-070, PBI-072) |
| 2 | 4.1.2 | B2 | Banco de dados PostgreSQL gerenciado | 5-Muito Alta | Armazena os dados de usuários, clientes, equipamentos e inspeções. | AWS RDS, Supabase, Neon, Railway | 2 mês | R$ 150,00 | R$ 300,00 | Sprint 1 | Responsável: Marcela (PBI-004) |
| 3 | 4.1.3 | B3 | Armazenamento de objetos (evidências/fotos) | 3-Média | Guarda as fotos de evidência e de não conformidades registradas em campo. | AWS S3, Cloudflare R2, Backblaze B2 | 2 mês | R$ 90,00 | R$ 180,00 | Sprint 1 | Responsável: Júlia (PBI-042, PBI-043) |
| 4 | 4.1 | B4 | Domínio e certificado SSL | 3-Média | Garante o acesso em HTTPS ao painel web e à API. | Registro.br, GoDaddy, Cloudflare | 1 ano | R$ 120,00 | R$ 120,00 | Sprint 1 | Responsável: Júlia |
| 5 | 4.1 | B5 | Serviço de notificações push | 2-Baixa | Permite avisar os técnicos sobre novas atribuições e prazos (funcionalidade P1). | Firebase Cloud Messaging, Expo Push, OneSignal | 2 mês | R$ 60,00 | R$ 120,00 | Sprint 3 | Responsável: Marcela (PBI-075) |
| 6 | 4.2.1 | B6 | Pipeline CI/CD (build e deploy) | 3-Média | Automatiza a build, a execução dos testes e a publicação. | GitHub Actions, GitLab CI, CircleCI | 2 mês | R$ 80,00 | R$ 160,00 | Sprint 1 | Responsável: Júlia (PBI-005, PBI-069) |
| 7 | 4.1.4 | B7 | Ambiente de homologação/testes | 3-Média | Permite validar a integração antes da demonstração e reduz o risco de indisponibilidade. | AWS, Google Cloud, Render | 2 mês | R$ 120,00 | R$ 240,00 | Sprint 1 | Responsável: Marcela (risco R02) |
| 8 | 2.1 / 3.1 | C1 | Licença Figma (design/protótipo) | 4-Alta | Serve para prototipar a UI/UX e as telas antes de iniciar o desenvolvimento. | Figma | 2 mês | R$ 75,00 | R$ 150,00 | Sprint 1 | Responsável: Andressa |
| 9 | 4.2.4 | C2 | Conta Expo (Expo Build/EAS) — plano gratuito | 4-Alta | Permite gerar o APK Android de demonstração pelo Expo Build; o plano gratuito oferece até 15 builds Android por mês. | Expo | 1 conta | R$ 0,00 | R$ 0,00 | Sprint 1 | Responsável: Rodrigo (PBI-002, PBI-068); fila de baixa prioridade, com builds disparadas com antecedência |
| 10 | 5.3.1 | C3 | Ferramenta de gestão de projeto (board/backlog) | 4-Alta | Permite acompanhar o backlog e os cards (PBIs) como fonte única da verdade. | GitHub Projects, Jira, Trello | 2 mês | R$ 50,00 | R$ 100,00 | Sprint 1 | Responsável: Natália |
| 11 | 1 / 2 / 3 | C4 | IDEs e plugins premium | 3-Média | Aumenta a produtividade no desenvolvimento das três frentes. | JetBrains, VS Code, Cursor | 9 lic | R$ 40,00 | R$ 360,00 | Sprint 1 | Responsável: Equipe completa |
| 12 | 1.1.2 / 1.1.3 | C5 | Ferramenta de testes de API | 3-Média | Permite validar os endpoints e o contrato OpenAPI. | Postman, Insomnia, Bruno | 2 mês | R$ 60,00 | R$ 120,00 | Sprint 1 | Responsável: Lucas (PBI-006, PBI-071) |
| 13 | 3.4 / 4.3.1 | D1 | Dispositivo Android para testes de campo | 4-Alta | Serve para testar o app mobile, o QR Code, o GPS e o fluxo offline em campo. | Samsung, Motorola, Xiaomi | 2 un | R$ 900,00 | R$ 1.800,00 | Sprint 1 | Responsável: Equipe Mobile (PBI-041, PBI-045, PBI-048) |
| 14 | 3.4.1 | D2 | Impressão de etiquetas QR Code para equipamentos | 3-Média | Permite a identificação única dos equipamentos durante a inspeção. | Gráfica local, Pimaco | 100 un | R$ 1,20 | R$ 120,00 | Sprint 1 | Responsável: Natália (PBI-016) |
| 15 | 4.3.3 | D3 | Material de transporte para visita de campo (demo) | 2-Baixa | Cobre o deslocamento para a validação e a demonstração em campo. | Uber, transporte próprio | 2 visita | R$ 50,00 | R$ 100,00 | Sprint 2 | Responsável: Equipe |
| 16 | 5.4 | D4 | Impressão de documentação e material de apresentação | 2-Baixa | Cobre o material impresso da entrega final. | Gráfica local | 1 pacote | R$ 80,00 | R$ 80,00 | Sprint 3 | Responsável: Natália |
| | | | | | | | | **TOTAL** | **R$ 4.310,00** | | |

---

## 4. Resumo das Aquisições

| Categoria | Total (R$) | Nº de itens |
|---|---:|:--:|
| Infraestrutura e Nuvem | 1.480,00 | 7 |
| Ferramentas e Licenças | 730,00 | 5 |
| Equipamentos e Materiais | 2.100,00 | 4 |
| **TOTAL DAS AQUISIÇÕES** | **4.310,00** | **16** |

> O montante de aquisições externas (**R$ 4.310,00**) equivale a aproximadamente **2,1%** da linha de base de custos de R$ 204.000,00, o que é coerente com o orçamento do projeto, no qual os Recursos Humanos representam 90,7% do investimento.

---

## 5. Condução das Aquisições

Na seleção de fornecedores e na adjudicação dos contratos, serão avaliados os seguintes elementos (PMBOK 12.2):

- **Preço e condições de pagamento** — dar prioridade a planos mensais sem fidelidade extensa, por causa do prazo de cerca de 2 meses.
- **Critérios de inspeção, qualidade e aceitação** — exigir SLA de disponibilidade nos serviços de nuvem (o que mitiga o risco R02).
- **Garantia e suporte futuro** — contar com suporte técnico dos serviços gerenciados.
- **Incentivos e penalidades** — prever créditos por indisponibilidade (SLA).
- **Seguros e obrigações de realização** — não se aplica ao contexto acadêmico.
- **Cláusula de rescisão** — optar por serviços canceláveis a qualquer momento.

---

## 6. Controle das Aquisições

Após a contratação dos fornecedores, o desempenho de cada um será acompanhado em relação ao contrato (PMBOK 12.3):

- Monitorar o **consumo e os custos** dos serviços de nuvem durante as sprints, confrontando com o que foi orçado.
- Checar o **SLA de disponibilidade** dos ambientes de aplicação, banco e homologação (gatilho do risco R02: indisponibilidade superior a 1h em homologação).
- Confirmar que as **licenças e ferramentas** adquiridas permanecem ativas para toda a equipe.
- Registrar eventuais mudanças e ajustes de contrato.

---

## 7. Encerramento das Aquisições

Ao término do projeto (PMBOK 12.4):

- **Encerrar as assinaturas mensais** de nuvem e ferramentas depois da entrega final (marco de 24/11/2026, ao final da Sprint 3).
- **Confirmar o fechamento** de cada contrato e a quitação dos pagamentos.
- **Guardar** os comprovantes e registrar as aquisições realizadas na pasta `docs/` do repositório do FieldOps (pacote 5.4.2 da EAP).

---

## 8. Considerações Finais

- Foram identificadas **16 aquisições** externas, repartidas em 3 categorias, somando **R$ 4.310,00**, em total conformidade com o orçamento do projeto.
- As aquisições de **urgência muito alta (nível 5)** — servidor de aplicação e banco PostgreSQL — são as únicas **bloqueadoras**: sem elas o sistema deixa de funcionar, e por isso precisam ser providenciadas antes ou logo no início da Sprint 1.
- As aquisições de **urgência alta (nível 4)** — Figma, conta Expo, board de gestão e dispositivos Android — não chegam a bloquear o sistema, mas são exigidas logo no início das frentes de desenvolvimento, ainda na Sprint 1.
- A opção por **serviços gerenciados com SLA** dá suporte direto à resposta do risco **R02 (indisponibilidade dos serviços de nuvem de terceiros)** constante no registro de riscos do projeto.
- Este documento representa o **plano de aquisições** do FieldOps e deve ser acompanhado pelos processos *12.3 — Controlar as aquisições* e *12.4 — Encerrar as aquisições* ao longo do projeto e ao seu término.
