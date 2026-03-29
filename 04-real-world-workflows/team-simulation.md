# Team Simulation / Simulação de Time

## Team scenario / Cenário de Time

Imagine a team working on a data platform with:

- 5 developers
- 1 data engineer
- 1 reviewer

Imagine um time trabalhando em uma plataforma de dados com:

- 5 desenvolvedores
- 1 engenheiro de dados
- 1 revisor

This simulation helps show how a real team collaborates and how a Tech Lead defines the process.
Esta simulação ajuda a mostrar como um time real colabora e como um Tech Lead define o processo.

## Workflow / Fluxo de Trabalho

1. Create a feature branch for each task:
   ```bash
git checkout -b feature/123-add-data-pipeline
   ```
1. Crie uma feature branch para cada tarefa:
   ```bash
git checkout -b feature/123-add-data-pipeline
   ```
2. Implement the change and run local checks.
2. Implemente a mudança e execute verificações locais.
3. Open a pull request to `main`.
3. Abra um pull request para `main`.
4. Require at least 2 approvals.
4. Exija pelo menos 2 aprovações.
5. Ensure CI passes before merge.
5. Garanta que o CI passe antes de mesclar.
6. Merge only after review and tests are green.
6. Mescle somente após revisão e testes aprovados.

## Why this matters / Por que isso importa

This pattern improves quality by:

- enforcing review discipline
- keeping branches small and focused
- making failures visible early
- ensuring the merge target remains stable

Este padrão melhora a qualidade ao:

- reforçar a disciplina de revisão
- manter branches pequenas e focadas
- tornar falhas visíveis cedo
- garantir que o alvo do merge permaneça estável

## Example roles / Papéis de exemplo

- Developer: builds the feature and writes tests.
- Desenvolvedor: constrói a feature e escreve testes.
- Data engineer: validates pipeline logic and data quality.
- Engenheiro de dados: valida a lógica do pipeline e a qualidade dos dados.
- Reviewer: checks correctness, readability, and architecture.
- Revisor: verifica correção, legibilidade e arquitetura.
- Tech Lead: defines the process, ensures the workflow is followed, and decides when to adopt changes.
- Tech Lead: define o processo, garante que o fluxo seja seguido e decide quando adotar mudanças.
