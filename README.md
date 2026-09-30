# 🧪 Dois Caminhos • Simulador de Desenvolvimento de Software com IA

> **Laboratório de entrega e modelo exploratório de fluxo de valor**  
> Compare o impacto da Inteligência Artificial no ciclo de vida do desenvolvimento de software (SDLC) sob as mesmas premissas de backlog, gargalos de revisão, custos e limites de paralelismo.

---

## 🎯 Sobre o Projeto

O **Simulador de Desenvolvimento de Software com IA** é uma aplicação web interativa e autocontida desenvolvida para explorar uma pergunta fundamental da engenharia de software contemporânea:  
*Como diferentes formas de adoção de IA (assistentes, desenvolvimento orientado por especificações ou orquestração de agentes) afetam velocidade, qualidade, retrabalho e custo real de entrega?*

Em vez de olhar apenas para linhas de código geradas por minuto, o simulador modela o fluxo completo de ponta a ponta:
- **Descoberta / Refinamento** (12% do esforço base)
- **Implementação** (53% do esforço base)
- **Validação / Testes** (25% do esforço base)
- **Deploy / Entrada em Produção** (10% do esforço base)
- **Retrabalho e ciclo de vida de bugs** (rejeições funcionais e defeitos que escapam para produção)

---

## ✨ Principais Funcionalidades

- **Comparação Lado a Lado**: O mesmo backlog gerado via semente determinística percorre em paralelo o fluxo **Manual** e o fluxo **Com IA**.
- **Três Modos de Trabalho com IA**:
  - **IA como Assistente**: O desenvolvedor humano executa todas as etapas com ganho de velocidade pontual.
  - **Desenvolvimento Dirigido por Especificações (Specs)**: Descoberta e validação intensiva com humanos (+50% esforço de especificação), agentes executando implementação e deploy.
  - **Orquestração de Agentes / Fábrica de IA**: Múltiplos agentes paralelos executam as tarefas de ponta a ponta, com bloqueio humano apenas em decisões críticas de arquitetura e validações de alto impacto.
- **Cenários de Produtividade Baseados em Evidências Reais**:
  - *Echoes of AI (Borg et al., 2026/2024)*: Redução de ~30,7% do tempo de desenvolvimento em Java.
  - *METR (2025/2026)*: Avaliações empíricas em repositórios maduros e tarefas complexas.
  - *Estudos de Campo Microsoft (Cui et al.)*: Aumento de throughput em tarefas concluídas.
  - *Experimentos controlados (Peng et al., 2023)*.
  - Referências adicionais contextualizadas: *DORA 2025*, *Maier et al. (Meta-análise 2026)* e *Anthropic (2026)*.
- **Práticas de Engenharia Configuráveis**:
  - Test-Driven Development (TDD)
  - Programação em Par (Pair Programming)
  - Refatoração Contínua
  - Integração Contínua (CI)
  - Deploy Contínuo (CD)
  - Observabilidade e Monitoramento
  - QA dedicado / Validação formal
- **Modelo Econômico Completo**:
  - Custo por hora de trabalho humano (inclui custos de fila, espera e revisão).
  - Custo de tokens de IA (tokens de entrada, tokens de saída e assinaturas mensais).
  - Cálculo transparente de **Custo por Entrega Útil**.
- **Análise Estatística (Monte Carlo / 100 Execuções)**:
  - Permite rodar 100 simulações com sementes sequenciais para avaliar distribuição de probabilidade e medianas com intervalos **P10–P90**.
- **Exportação de Dados**:
  - Exportação completa das métricas, parâmetros e histórico em formato JSON (`resultado-simulacao.json`).

---

## 🚀 Demonstração Online (GitHub Pages)

A aplicação está configurada para ser servida diretamente pelo **GitHub Pages**:

```
https://<seu-usuario>.github.io/<nome-do-repositorio>/
```

*(Substitua `<seu-usuario>` e `<nome-do-repositorio>` pelos dados do seu repositório no GitHub).*

---

## 🛠️ Como Executar Localmente

Como a aplicação é 100% autocontida (HTML5, CSS moderno e Vanilla JavaScript sem dependências externas), você não precisa instalar bibliotecas adicionais:

### Opção 1: Abrir diretamente no navegador
Basta dar um duplo clique no arquivo [`index.html`](index.html) ou abri-lo pelo seu navegador favorito.

### Opção 2: Servidor estático local

Com **Python**:
```bash
python3 -m http.server 8080
```
Acesse em: `http://localhost:8080`

Com **Node.js**:
```bash
npx serve .
```

---

## 🌐 Publicação no GitHub Pages

O projeto já está estruturado com `index.html` na raiz e inclui um workflow automatizado do GitHub Actions.

Você pode habilitar o GitHub Pages de duas maneiras:

### Método A: Deploy via GitHub Actions (Recomendado)

O repositório já inclui o arquivo [`.github/workflows/deploy.yml`](.github/workflows/deploy.yml).

1. No seu repositório no GitHub, acesse a aba **Settings** (Configurações).
2. No menu lateral esquerdo, clique em **Pages**.
3. Em **Build and deployment** > **Source**, selecione **GitHub Actions**.
4. Faça um push para a branch `main`. A esteira irá compilar e publicar a página automaticamente!

### Método B: Deploy clássico direto da Branch

1. Acesse **Settings** > **Pages**.
2. Em **Build and deployment** > **Source**, selecione **Deploy from a branch**.
3. Em **Branch**, selecione `main` e a pasta `/ (root)`.
4. Clique em **Save**. O GitHub Pages disponibilizará o link em poucos instantes.

---

## 📊 Estrutura de Arquivos

```text
├── .github/
│   └── workflows/
│       └── deploy.yml               # Workflow de publicação automática no GitHub Pages
├── index.html                       # Ponto de entrada principal da aplicação (GitHub Pages)
├── simulador-desenvolvimento.html   # Cópia de referência da simulação
└── README.md                        # Documentação do projeto
```

---

## 📖 Como Interpretar os Resultados

- **Entregas Úteis**: Itens implantados em produção que foram devidamente aprovados e continuam íntegros (sem defeito latente).
- **Lead Time vs. Cycle Time**: Mede desde a chegada do item até o deploy e desde o início do trabalho ativo até o deploy.
- **Incidentes e Bugs**: O modelo diferencia defeitos identificados internamente na validação daqueles que escapam para produção. Falhas em produção retornam ao backlog com prioridade máxima, consumindo capacidade do time e impactando o WIP.
- **Relação Custo / Valor**: Mais velocidade nem sempre significa menor custo se a taxa de retrabalho ou a dependência de validações humanas gerar estrangulamento de fluxo.

> ⚠️ **Aviso Metodológico**: Este simulador é um modelo exploratório e didático voltado para reflexão e debate sobre gargalos de processo. Ele não substitui medições empíricas no contexto específico de cada organização.

---

## 📄 Licença

Distribuído sob a licença [MIT](LICENSE). Sinta-se à vontade para utilizar, estudar e adaptar para o seu time ou organização.
