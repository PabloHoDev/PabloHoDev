# Portfólio Profissional --- Pablo Henrique Oliveira

> Documento inicial de concepção do projeto.\
> Objetivo: transformar o perfil do GitHub em uma apresentação
> profissional, autêntica, organizada e tecnicamente relevante.

## 1. Visão do projeto

Criar um repositório especial do GitHub que funcione como uma **central
de identidade profissional**.

A página deve permitir que recrutadores, desenvolvedores e possíveis
colaboradores entendam rapidamente:

-   Quem sou e como me posiciono profissionalmente.
-   Quais áreas da engenharia de software são meu foco.
-   Quais tecnologias utilizo e como as organizo.
-   Que tipo de problema consigo resolver.
-   Quais projetos demonstram minhas habilidades.
-   Onde acompanhar meu trabalho e entrar em contato.

A proposta não é reproduzir um catálogo genérico de tecnologias ou
copiar outro perfil. O objetivo é construir uma apresentação com
identidade própria, conteúdo verdadeiro e evidências concretas de
capacidade técnica.

## 2. Posicionamento profissional

### Mensagem central

~~Transformando problemas complexos em soluções de software.~~ A frase
era genérica e servia para qualquer perfil.

A mensagem passa a vir do que os projetos de fato têm em comum. Quase
todos nascem de operação baseada em planilhas e bases diárias:
conciliação de extratos, sincronização de planilhas de controle,
automação de fluxos com arquivos. A apresentação conta essa origem
(análise de dados e operação) e o foco atual (backend).

### Apresentação adotada no README

> Venho da análise de dados e da operação, onde todo dia chega uma base
> nova, a planilha de controle tem uma aba por equipe e alguém confere
> tudo linha por linha. Quase tudo o que está aqui nasceu desse tipo de
> problema. Hoje meu foco é backend: regras de negócio que precisam
> estar certas, dados que não podem se perder e sistemas que registram o
> que fizeram.

### Título profissional: pendente de decisão

-   Este documento propunha **Software Engineer \| Backend**.
-   A bio atual do GitHub diz **Fullstack Developer in transition \|
    Data Scientist background**.
-   Os repositórios mostram backend forte (Java/Spring, motores de
    regra, Postgres), mas também aplicações Next.js completas.

Proposta: **Desenvolvedor de software · backend, automação e dados**.
Alinhar a bio do GitHub e o LinkedIn ao mesmo título.

### Princípio de comunicação

O perfil deve transmitir que não se trata apenas de alguém que conhece
várias linguagens, mas de alguém que utiliza engenharia de software para
transformar problemas em soluções.

## 3. Direção visual

### Conceito recomendado

**Terminal / Engineering**

Uma identidade visual técnica, minimalista e moderna, inspirada em
ambientes de desenvolvimento, terminais, arquitetura de software e
ferramentas de engenharia.

### Características visuais

-   Fundo escuro, preferencialmente grafite ou azul muito fechado.
-   Cores de destaque em verde, ciano ou turquesa.
-   Tipografia e elementos que remetam ao universo técnico.
-   Ícones consistentes para tecnologias e áreas de atuação.
-   Badges personalizados, sem excesso de informação.
-   Seções bem delimitadas e leitura rápida.
-   Elementos dinâmicos usados com propósito, não apenas como decoração.

### O que evitar

-   Excesso de badges e tecnologias sem contexto.
-   Estatísticas que não acrescentem informação relevante.
-   Animações exageradas ou que prejudiquem a leitura.
-   Aparência de template genérico.
-   Afirmar domínio de ferramentas ou competências sem evidências.

## 4. Estrutura proposta para o README

### 4.1. Identidade --- Sobre mim

Apresentar nome, especialidade, resumo profissional e links de contato.

Conteúdo previsto:

-   Nome: Pablo Henrique Oliveira.
-   Título profissional: Software Engineer \| Backend.
-   Mensagem central do portfólio.
-   Links para GitHub e LinkedIn.

### 4.2. Stack tecnológica

Organizar as tecnologias por área, em vez de apresentar uma sequência
única de badges.

Revisada em 27/11/2026 contra os repositórios públicos. Regra: só entra
o que aparece em algum projeto.

  Área            Tecnologias                                   Evidência
  --------------- --------------------------------------------- ------------------------------------------
  Linguagens      TypeScript, Java, Python, C#                  todos os projetos em destaque
  Backend         Node.js, Spring Boot, Next.js, .NET           pending-reconciliation, crowslot, workflow engine
  Arquitetura     REST, domínio isolado, ADRs                   workflow engine (10 ADRs), dungeon crawler
  Dados           PostgreSQL, Prisma, Drizzle, pandas, openpyxl pending-reconciliation, crowslot, excel-sync-tool
  Qualidade       Vitest, Playwright, pytest, xUnit, CodeQL     CI em 4 dos 5 projetos em destaque
  Infra           Docker Compose, GitHub Actions, Vercel, Neon  workflow engine, excel-sync-tool

Saíram da lista por falta de evidência pública: **Redis, RabbitMQ,
SQLite, SQL Server**. Se forem usados no trabalho, entram quando houver
um projeto que mostre isso, ou numa seção de experiência profissional,
sem dados da empresa.

TypeScript e Next.js deixaram de ser "frontend complementar". Eles estão
no centro de três projetos principais.

### 4.3. Projetos em destaque

Apresentar projetos como estudos de caso curtos. Cada cartão ou seção
deve explicar:

1.  Qual problema ou objetivo o projeto aborda.
2.  Qual solução foi construída.
3.  Quais decisões técnicas merecem destaque.
4.  Quais tecnologias foram utilizadas.
5.  Onde acessar o repositório.

Projetos em destaque (revisado em 27/11/2026, na ordem do README):

#### pending-reconciliation (em construção)

-   TypeScript, Node.js, Next.js, Drizzle, PostgreSQL, Vitest,
    Playwright.
-   Motor de conciliação diária de um extrato com cerca de 40 mil
    repasses. É idempotente e transacional, usa Postgres em camadas com
    SCD2 e auditoria, e roda só com dados sintéticos.
-   Atenção: a descrição do repositório fala em "+ de 400 mil linhas" e
    o README fala em "cerca de 40 mil". É preciso unificar.

#### crowslot-saas (em desenvolvimento)

-   Next.js, Prisma, PostgreSQL, Auth.js, Zod, Stripe.
-   SaaS multi-tenant com isolamento reforçado pelo banco, RBAC, limites
    por plano e agenda sem sobreposição garantida pelo Postgres.
-   Ainda faltam a agenda completa, o Stripe, os testes E2E e o deploy.

#### excel-sync-tool (funcionando, com demo online)

-   CLI em Python (openpyxl, pytest) e demo web em Next.js.
-   Na demo, a conferência de 160 processos em 4 abas cai de cerca de
    55 min para menos de 1 s.

#### Enterprise Workflow Engine (funcional)

-   Java 25, Spring Boot, PostgreSQL, Docker. API REST, console web, 10
    ADRs, CI e CodeQL.
-   Domínio em Java puro, sem Spring nem JPA.

#### Dungeon Crawler (em andamento)

-   C#, .NET 10, xUnit. **Ainda não usa Unity.** Hoje roda no terminal,
    e a camada Unity está planejada.
-   Direção das dependências verificada por testes. Ainda não tem CI.

#### Fora do destaque

-   **CorporateFlow Automation** (Python): vai para "outros projetos".
    Tem um tema parecido com o do excel-sync-tool, que está mais
    completo e tem demo.
-   **elt-pipeline**, **file-organizer**: estudos.
-   **Darkbound / Duel Academy**: é um fan game de uma franquia
    registrada. Não entra no portfólio profissional.

Os projetos devem ser apresentados de acordo com seu estado real:
concluído, em desenvolvimento ou estudo. Não apresentar funcionalidades
planejadas como se já estivessem implementadas.

### 4.4. Experiência prática --- Engineering in Practice

Destacar experiências de construção de soluções para problemas reais,
respeitando confidencialidade e sem divulgar dados internos.

Possíveis frentes de apresentação:

-   Automação de processos.
-   Engenharia e tratamento de dados.
-   Desenvolvimento de ferramentas internas.
-   Indicadores e dashboards.
-   Padronização e controle operacional.
-   Integração e consolidação de informações.

Indicadores que podem ser avaliados para inclusão, desde que possam ser
divulgados e contextualizados:

-   Processos com abrangência em 13 unidades federativas.
-   Operações envolvendo mais de 27 profissionais.

Os números precisam ser apresentados com contexto e sem expor
informações confidenciais da organização.

### 4.5. Atualmente construindo --- Currently Building

Uma seção curta para mostrar evolução e projetos em andamento.

Decisão: a lista genérica de áreas foi trocada por projetos reais. O
cabeçalho do README (`ls projetos/`) e as etiquetas de situação de cada
projeto (`em construção`, `em desenvolvimento`) cumprem esse papel. Ao
mudar o que está ativo, atualize os dois.

### 4.6. Contato

Manter links objetivos para:

-   GitHub.
-   LinkedIn.
-   Outros canais profissionais que sejam definidos posteriormente.

## 5. Elementos dinâmicos

A inspiração é criar uma página visualmente interessante, com recursos
dinâmicos que funcionem bem dentro das limitações do GitHub.

Possibilidades:

-   Animação de texto para apresentar especialidades.
-   Badges tecnológicos com ícones.
-   Estatísticas de contribuições do GitHub.
-   Gráfico de atividade.
-   Cards dos principais repositórios.
-   Indicadores de projetos em desenvolvimento.
-   Links para redes profissionais.

### Decisão (27/11/2026)

-   O único elemento dinâmico é o cabeçalho `assets/header.svg`. É um
    terminal próprio, animado com CSS dentro do SVG e hospedado no
    próprio repositório. Não depende de serviço externo, a animação roda
    uma única vez e respeita `prefers-reduced-motion`. Sem animação, o
    estado final aparece completo.
-   Sem widgets de estatística de terceiros e sem parede de badges. As
    tecnologias aparecem numa tabela que aponta onde cada uma é usada.

### Restrições técnicas

O README do GitHub utiliza Markdown e oferece suporte limitado a HTML.
Não possui a mesma liberdade de interação de um site convencional.

Recursos dinâmicos poderão depender de SVGs, imagens hospedadas e
serviços externos de estatísticas. É importante avaliar disponibilidade,
manutenção, privacidade e confiabilidade de cada serviço antes de
adotá-lo.

O conteúdo essencial deve continuar compreensível mesmo se uma imagem
externa ou animação deixar de carregar.

## 6. Princípios de qualidade

O portfólio deverá seguir estes princípios:

-   **Autenticidade:** apresentar experiências e competências reais.
-   **Clareza:** permitir que o visitante compreenda o perfil
    rapidamente.
-   **Evidência:** associar habilidades a projetos, entregas ou
    experiências.
-   **Consistência:** manter uma identidade visual e textual uniforme.
-   **Manutenibilidade:** facilitar atualizações do README.
-   **Responsividade:** funcionar bem em telas menores.
-   **Acessibilidade:** não depender exclusivamente de cores, animações
    ou imagens.
-   **Confidencialidade:** não publicar dados, nomes ou informações
    internas de empresas sem autorização.

## 7. Plano de execução

### Fase 01 --- Identidade e posicionamento

-   [ ] Definir a mensagem principal.
-   [ ] Confirmar o título profissional.
-   [ ] Revisar o texto de apresentação.
-   [ ] Definir as áreas de atuação prioritárias.
-   [ ] Confirmar links profissionais.

### Fase 02 --- Arquitetura do README

-   [ ] Definir a ordem das seções.
-   [ ] Organizar a stack por especialidade.
-   [ ] Selecionar os projetos em destaque.
-   [ ] Escrever descrições curtas e objetivas.
-   [ ] Definir a seção de experiência prática.
-   [ ] Definir a seção de projetos em andamento.

### Fase 03 --- Identidade visual

-   [ ] Definir paleta de cores.
-   [ ] Escolher estilo de ícones e badges.
-   [ ] Criar cabeçalho visual.
-   [ ] Definir padrões para cards e divisórias.
-   [ ] Testar leitura em desktop e dispositivos móveis.

### Fase 04 --- Recursos dinâmicos

-   [ ] Avaliar animação de apresentação.
-   [ ] Integrar estatísticas do GitHub, se agregarem valor.
-   [ ] Avaliar cards de repositórios.
-   [ ] Testar recursos externos e definir alternativas.
-   [ ] Garantir que o README continue útil sem esses recursos.

### Fase 05 --- Publicação e manutenção

-   [ ] Criar o repositório especial com o mesmo nome de usuário do
    GitHub.
-   [ ] Publicar o README.md.
-   [ ] Conferir links, imagens e badges.
-   [ ] Revisar a apresentação em diferentes tamanhos de tela.
-   [ ] Estabelecer uma rotina de atualização dos projetos e
    informações.

## 8. Decisões iniciais recomendadas

A direção sugerida para começar é:

  -----------------------------------------------------------------------
  Decisão                             Proposta inicial
  ----------------------------------- -----------------------------------
  Identidade visual                   Terminal / Engineering

  Posicionamento                      Backend e Engenharia de Software

  Primeiro produto                    README profissional e dinâmico

  Estilo                              Escuro, minimalista e técnico

  Diferencial                         Projetos e experiências
                                      apresentados como evidências de
                                      capacidade
  -----------------------------------------------------------------------

Essas escolhas são uma hipótese inicial de trabalho, não decisões
irreversíveis. Devem ser confirmadas antes da implementação.

## 9. Critério de sucesso

O projeto estará cumprindo seu objetivo quando uma pessoa que acessar o
perfil conseguir, em poucos minutos:

1.  Entender quem é Pablo Henrique Oliveira.
2.  Identificar seu foco profissional.
3.  Reconhecer suas principais áreas técnicas.
4.  Encontrar projetos que demonstrem suas habilidades.
5.  Compreender sua experiência prática sem exposição de informações
    confidenciais.
6.  Encontrar facilmente seus canais profissionais.

------------------------------------------------------------------------

**Essência do projeto:** um portfólio que não apenas diz quais
tecnologias o desenvolvedor conhece, mas demonstra como ele pensa,
constrói e resolve problemas.
