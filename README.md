# Explorando Práticas de Teste

Neste exercício, vamos explorar práticas de teste em sistemas reais utilizando a ferramenta [TestMiner](https://andrehora.github.io/testminer).

O TestMiner permite visualizar e analisar testes de software em repositórios do GitHub, fornecendo dados sobre como os projetos organizam seus testes, como eles evoluem entre versões e quais bibliotecas de teste são utilizadas.
Explore a ferramenta antes de começar para se familiarizar com seu funcionamento.

Mais detalhes no GitHub da ferramenta: https://github.com/andrehora/testminer.

---

## Passo 1: Selecionar DOIS repositórios

Escolha dois repositórios reais que possuam testes de software.
Abaixo estão alguns links para ajudá-lo a encontrar projetos interessantes:

- Python: https://github.com/topics/python?l=python
- JavaScript: https://github.com/topics/javascript?l=javascript
- TypeScript: https://github.com/topics/typescript?l=typescript
- Java: https://github.com/topics/java?l=java

- Tópicos: [ai](https://andrehora.github.io/testminer/#topic:ai), [llm](https://andrehora.github.io/testminer/#topic:llm), [api](https://andrehora.github.io/testminer/#topic:api), [nodejs](https://andrehora.github.io/testminer/#topic:nodejs), [android](https://andrehora.github.io/testminer/#topic:android)

- Por organização: [Google](https://andrehora.github.io/testminer/#google), [Microsoft](https://andrehora.github.io/testminer/#microsoft), [Apple](https://andrehora.github.io/testminer/#apple), [Facebook](https://andrehora.github.io/testminer/#facebook), [Netflix](https://andrehora.github.io/testminer/#netflix), 
[GitHub](https://andrehora.github.io/testminer/#github), [Apache](https://andrehora.github.io/testminer/#apache), [HuggingFace](https://andrehora.github.io/testminer/#huggingface)

## Passo 2: Explorar os repositórios selecionados

Busque os repositórios escolhidos no [TestMiner](https://andrehora.github.io/testminer) e analise os dados de teste gerados pela ferramenta.

## Passo 3: Explicar as prática de teste

Para cada repositório, escolha uma prática ou dado de teste relevante e explique com suas próprias palavras.

---

## Instruções de entrega

1. Faça um `fork` deste repositório (saiba mais sobre forks [aqui](https://docs.github.com/pt/pull-requests/collaborating-with-pull-requests/working-with-forks/fork-a-repo)).
2. Responda às questões abaixo diretamente neste arquivo `README.md` do seu fork. Pode adicionar imagens para enriquecer sua explicação.
3. No Moodle, submeta apenas a URL do seu fork.

---

## Respostas

### Repositório 1 

Repositório: `https://github.com/PostHog/posthog`

URL TestMiner: `https://andrehora.github.io/testminer/#PostHog/posthog`

Explicação: `<SUA_EXPLICAÇÃO>`

<img width="957" height="932" alt="image" src="https://github.com/user-attachments/assets/646bb8f6-5605-4124-9470-1c5f9e1f7ab9" />

O PostHog é um projeto de software de grande porte, escrito principalmente em Python. A captura do TestMiner mostra 36.391 arquivos de código-fonte e 10330 diferentes categorias relacionadas a testes.
Prática de teste identificada: Integração contínua de testes end-to-end com seleção de testes baseada nas alterações.

O projeto PostHog utiliza GitHub Actions para automatizar a execução de testes end-to-end (E2E) com Playwright. O workflow analisado pode ser acionado por eventos do repositório e possui mecanismos para selecionar testes relevantes em determinados pull requests, além de permitir execuções completas da suíte em outras situações.
`https://github.com/PostHog/posthog/blob/master/.github/workflows/ci-e2e-playwright.yml`

Essa prática busca reduzir o tempo de feedback durante o desenvolvimento sem abandonar a verificação integrada da aplicação. A execução paralela dos testes e as tentativas adicionais para lidar com falhas também demonstram preocupações com o desempenho e a confiabilidade do pipeline.

Na análise realizada pelo TestMiner, foram identificados 112 itens na categoria E2E e 62 na categoria CI Tests, reforçando o comportamento visto.

### Repositório 2

Repositório: `https://github.com/soxoj/maigret`

URL TestMiner: `https://andrehora.github.io/testminer/#soxoj/maigret`

Explicação: 
### Análise das práticas de teste do Maigret

A análise do repositório Maigret identifiquei alguns testes automatizados, integração contínua, medição de cobertura e análise estática de código. Um aspecto relevante é que o projeto precisa lidar com dependências externas: como sua funcionalidade envolve consultar diversos sites, os resultados dos testes podem ser afetados por indisponibilidade ou mudanças nos serviços consultados.

Para lidar com esse problema, o projeto utiliza o Pytest e define uma marcação chamada `slow` para testes que acessam a rede ou demandam mais tempo. A integração contínua permite repetir testes com falha, utilizando três repetições e intervalos de cinco segundos. Essas decisões ajudam a reduzir a dependência da disponibilidade de serviços externos e tornam a execução dos testes mais adequada a diferentes ambientes.

O projeto também adota a integração contínua, executando as verificações definidas pelo projeto em cada pull request. Essa combinação permite detectar regressões funcionais, problemas de sintaxe e tipagem e inconsistências de estilo antes da integração das alterações. Essas práticas contribuem para a manutenção do software porque oferecem feedback sistemático sobre mudanças no código, ajudam a identificar áreas pouco testadas e reduzem a possibilidade de incorporar alterações que afetem comportamentos existentes.


