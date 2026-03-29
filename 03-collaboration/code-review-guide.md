# Code Review Guide / Guia de Revisão de Código

## What reviewers check / O que os revisores verificam

- Logic: the code must produce the correct result and follow the intended architecture.
- Lógica: o código deve produzir o resultado correto e seguir a arquitetura pretendida.
- Security: avoid vulnerabilities, secrets in code, and unsafe data handling.
- Segurança: evite vulnerabilidades, segredos no código e manipulação insegura de dados.
- Performance: ensure the implementation does not create unnecessary bottlenecks.
- Performance: garanta que a implementação não crie gargalos desnecessários.
- Readability: the code should be easy to understand and maintain.
- Legibilidade: o código deve ser fácil de entender e manter.
- Tests: every change should include tests or be covered by existing test cases.
- Testes: toda alteração deve incluir testes ou ser coberta por casos de teste existentes.

## Reviewer mindset / Mentalidade do revisor

A reviewer should ask: / Um revisor deve perguntar:

- Does this solve the problem clearly?
- Isso resolve o problema de forma clara?
- Is the change consistent with the repository style?
- A mudança está consistente com o estilo do repositório?
- Are there edge cases or failure modes missing?
- Há casos de borda ou modos de falha faltando?
- Can the code be simplified without losing clarity?
- O código pode ser simplificado sem perder clareza?

## Review feedback / Feedback de revisão

Good feedback is: / Um bom feedback é:

- specific
- específico
- constructive
- construtivo
- linked to the code
- vinculado ao código
- focused on outcomes, not personal preference
- focado em resultados, não em preferência pessoal

A strong code review culture reflects technical leadership and helps the team ship better software.
Uma cultura forte de revisão de código reflete liderança técnica e ajuda o time a entregar software melhor.
