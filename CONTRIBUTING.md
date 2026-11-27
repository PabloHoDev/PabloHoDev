# Contribuindo

Este é o repositório do meu perfil pessoal do GitHub, então não recebo contribuições de código.
Se encontrar um link quebrado, uma informação desatualizada ou algo errado na
[página](https://pablohodev.github.io/PabloHoDev/), abra uma
[issue](https://github.com/PabloHoDev/PabloHoDev/issues/new/choose) com o template **Problema**.

## Como as mudanças entram

1. Branch `tipo/descricao-curta` criada a partir da `main` (`feat/`, `fix/`, `docs/`, `ci/`...).
2. Commits em [Conventional Commits](https://www.conventionalcommits.org/pt-br/), em português.
3. Pull Request com o template preenchido e `Closes #N`.
4. Os três checks do CI verdes: **Gitleaks**, **HTML da página** e **Links quebrados**.
5. _Squash and merge_. A branch é apagada automaticamente.

A `main` é protegida: ninguém faz push direto nela. Os detalhes do CI e de como atualizá-lo
estão no [CLAUDE.md](CLAUDE.md).
