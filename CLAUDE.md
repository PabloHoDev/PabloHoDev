# CLAUDE.md: PabloHoDev/PabloHoDev

Repositório especial do perfil do GitHub. Ele publica duas coisas:

- `README.md`: aparece no topo de https://github.com/PabloHoDev.
- `docs/`: a página "sobre mim", publicada pelo GitHub Pages a partir de `main` + `/docs`
  em https://pablohodev.github.io/PabloHoDev/.

Não há build nem dependências. Qualquer merge na `main` vai direto para o perfil e para a página.

## Estrutura

| Caminho | O que é |
|---|---|
| `README.md` | README do perfil |
| `assets/header.svg`, `assets/og.svg` | Cabeçalho do README e fonte da imagem de compartilhamento |
| `docs/index.html` | Página "sobre mim" (HTML e CSS num arquivo só, sem JS) |
| `docs/og.png` | Imagem de compartilhamento, gerada a partir de `assets/og.svg` |
| `portfolio_profissional_pablo_henrique.md` | Documento de concepção, com as fases e a rotina de atualização |
| `divulgacao/` | Roteiros e legendas de posts, uma pasta por campanha. Os vídeos e imagens ficam fora do repositório. Não vai para o GitHub Pages |
| `.github/` | CI, template de PR e templates de issue |

## Fluxo de trabalho

A `main` está **protegida**. Não dá para commitar nem fazer push direto nela, nem como admin.

1. Atualize a `main` e crie uma branch `tipo/descricao-curta` (`feat/`, `fix/`, `docs/`, `ci/`, `chore/`...).
2. Faça commits em Conventional Commits, em português e agrupados por assunto.
3. Rode os checks locais (abaixo), dê push e abra o PR com o template preenchido e `Closes #N`.
4. Espere os três checks ficarem verdes.
5. O merge é sempre _Squash and merge_ (é o único método habilitado) e **precisa da aprovação do Pablo**.
   A branch é apagada automaticamente depois do merge.

Regras da proteção da `main`:

- Só entra por PR (0 aprovações exigidas).
- Os checks `Gitleaks`, `HTML da página` e `Links quebrados` precisam passar.
- A branch precisa estar atualizada com a `main`.
- Histórico linear e conversas resolvidas.
- Force-push e exclusão bloqueados.
- Tudo vale também para administradores.

Mudar a proteção, as opções de merge ou os secrets do repositório exige aprovação explícita.

## CI (`.github/workflows/ci.yml`)

Roda em todo PR, em push na `main` e manualmente (`workflow_dispatch`).

| Job | O que faz | Configuração |
|---|---|---|
| **Gitleaks** | Procura segredos em todo o histórico | Versão e SHA-256 do binário fixos no workflow (`GITLEAKS_VERSION`, `GITLEAKS_SHA256`) |
| **HTML da página** | `html-validate` em `docs/**/*.html` | `.htmlvalidate.json`: regras recomendadas, só `doctype-style` desligada |
| **Links quebrados** | `lychee` no README, no documento de concepção e na página | `.lycheeignore`: LinkedIn excluído, porque responde 999 para robôs |

Regras do workflow:

- Toda action é fixada por **SHA de commit**, com a versão em comentário (`# v7.0.1`).
- `permissions: contents: read` no topo e `persist-credentials: false` no checkout.
- O nome de cada job é o nome do check exigido na proteção da `main`. **Se renomear um job,
  atualize a proteção na mesma tarefa**, senão os PRs ficam travados esperando um check que não existe mais.
- Para atualizar uma action: pegue o SHA da nova tag (`gh api repos/<dono>/<action>/commits/<tag> --jq .sha`)
  e troque o SHA e o comentário.
- Para atualizar o Gitleaks: troque a versão e o SHA-256 do `linux_x64.tar.gz`, tirado do
  `gitleaks_<versão>_checksums.txt` da release.

## Checks locais (antes do push)

```bash
npx --yes html-validate@11.23.0 "docs/**/*.html"   # HTML
gitleaks git --redact --no-banner .                # segredos (Gitleaks instalado via winget)
```

Os links só são conferidos no CI. Antes de linkar um repositório novo, confira se ele é público
(`gh api repos/PabloHoDev/<repo> --jq .visibility`). Um repositório privado dá 404 e quebra o check.

## Releases

Marcos fechados viram tag SemVer anotada na `main` (`git tag -a vX.Y.Z`) com release no GitHub
(`gh release create`) listando os PRs. A última é a `v1.0.0`.

## Conteúdo

- Cada projeto mostra a situação real dele (`em construção`, `funcionando`...). Não anuncie o que não existe.
- Os números (ex.: ~40 mil registros por dia, 55 min → < 1 s) vêm dos READMEs dos projetos. Não arredonde para cima.
- Ao mudar a fase de um projeto em destaque, siga a **Rotina de atualização** do documento de concepção:
  README, `docs/index.html`, `assets/header.svg`, `assets/og.svg` → `docs/og.png` e os repositórios fixados.
- Nada de dados internos, de empresa ou de pessoas reais nos textos e nas imagens.
