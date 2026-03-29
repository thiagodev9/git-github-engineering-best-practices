# Engineering Decisions / Decisões de Engenharia

## Why Gitflow? / Por que Gitflow?

Gitflow is useful when a team needs clear release phases, long-lived branches, and defined hotfix workflows.
Gitflow é útil quando uma equipe precisa de fases de lançamento claras, branches duradouros e fluxos de hotfix bem definidos.

Use Gitflow when: / Use Gitflow quando:

- there are scheduled releases
- há lançamentos programados
- you need separate `release/*` branches
- você precisa de branches `release/*` separados
- hotfixes must be isolated from ongoing development
- hotfixes devem ser isolados do desenvolvimento em andamento
- the team is comfortable with branch discipline
- a equipe está confortável com disciplina de branches

## When to use trunk-based development? / Quando usar trunk-based?

Trunk-based development works well for teams that want fast feedback, continuous integration, and small incremental changes.
O desenvolvimento trunk-based funciona bem para equipes que querem feedback rápido, integração contínua e pequenas mudanças incrementais.

Use it when: / Use quando:

- you want frequent merges to `main`
- você deseja merges frequentes para `main`
- branches are short-lived
- branches são de curta duração
- automated testing is strong
- testes automatizados são robustos
- the team prefers fewer branch management steps
- a equipe prefere menos etapas de gerenciamento de branches

## How teams decide workflow / Como as equipes decidem o workflow

Teams choose a workflow based on team size, release cadence, risk level, tooling, and deployment process.
As equipes escolhem um workflow com base no tamanho do time, cadência de lançamentos, nível de risco, ferramentas e processo de deploy.

Key factors include: / Fatores chave incluem:

- frequency of releases
- frequência de lançamentos
- need for isolated patch branches
- necessidade de branches de patch isolados
- amount of automated testing
- quantidade de testes automatizados
- organizational compliance requirements
- requisitos de conformidade organizacional
- developer experience with Git
- experiência dos desenvolvedores com Git

## Tradeoffs between strategies / Compensações entre estratégias

- Gitflow offers structure but more branch overhead.
- Gitflow oferece estrutura, mas mais overhead de branches.
- Trunk-Based reduces branching complexity but requires strong CI/CD.
- Trunk-Based reduz complexidade de branching, mas requer CI/CD forte.
- Feature branches support isolated work, yet can create integration pain if long-lived.
- Feature branches suportam trabalho isolado, mas podem causar dor de integração se durarem muito.

A Tech Lead guides these decisions by balancing delivery speed, risk, and maintainability.
Um Tech Lead orienta essas decisões equilibrando velocidade de entrega, risco e manutenibilidade.
