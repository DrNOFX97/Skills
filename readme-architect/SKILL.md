---
name: readme-architect
description: Analisa um repositório GitHub e cria ou reestrutura o README.md para um resultado profissional, visualmente consistente e tecnicamente verificável. Detecta automaticamente stack, versões, scripts, dependências, configuração, testes, CI/CD, deployment, arquitectura e licença. Gera badges segmentados de estilo profissional, diagramas Mermaid quando apropriado e valida comandos, paths e informação antes de escrever.
---

# README Architect

## Objectivo

Transformar o README.md de um projecto GitHub numa documentação profissional, clara e tecnicamente fiável.

A skill deve comportar-se como um arquitecto de documentação técnica, não como um simples formatador de Markdown.

O princípio central é:

> **Documentar aquilo que o repositório demonstra, sem inventar informação.**

## Fluxo de trabalho

Executar sempre que possível nesta ordem:

1. Inspeccionar o README.md existente.
2. Inspeccionar a estrutura do repositório — incluir sempre uma procura explícita por um logo/banner já existente (ver secção Hero) e por ficheiro de licença.
3. Identificar a stack tecnológica.
4. Detectar versões a partir dos ficheiros reais.
5. Identificar scripts e comandos disponíveis.
6. Identificar variáveis de ambiente.
7. Identificar testes.
8. Identificar CI/CD.
9. Identificar deployment.
10. Identificar licença.
11. Auditar o README actual.
12. Definir a nova arquitectura documental.
13. Gerar badges.
14. Gerar ou actualizar diagramas Mermaid quando úteis.
15. Reescrever o README.
16. Validar o resultado contra o próprio repositório.
17. Apresentar um resumo das alterações e eventuais informações que não puderam ser verificadas.

## Regra de não invenção

Nunca inventar:

- versões;
- dependências;
- funcionalidades;
- endpoints;
- comandos;
- variáveis de ambiente;
- URLs;
- métricas;
- screenshots;
- cobertura de testes;
- serviços cloud;
- arquitectura;
- estado de produção;
- licenças;
- modelos de IA.

Quando uma informação não puder ser confirmada, deve ser:

- omitida; ou
- claramente marcada como pendente.

Nunca utilizar placeholders como informação final, por exemplo:

`YOUR_API_KEY`
`your-username`
`your-project`
`example.com`

excepto dentro de uma secção explicitamente dedicada à configuração de exemplo.

## Auditoria inicial

Produzir internamente uma análise com:

### Estrutura

- presença de título;
- descrição;
- badges;
- demonstração;
- funcionalidades;
- instalação;
- configuração;
- utilização;
- testes;
- arquitectura;
- estrutura do projecto;
- deployment;
- contribuição;
- licença;
- roadmap.

### Qualidade técnica

Verificar:

- comandos contra `package.json`, `pyproject.toml`, `Makefile`, scripts e configuração;
- versões contra os ficheiros de dependências;
- paths contra a árvore do projecto;
- variáveis contra `.env.example`, código e configuração;
- comandos Docker contra `Dockerfile` e `docker-compose.yml`;
- workflows contra `.github/workflows`;
- licença contra `LICENSE` ou `LICENSE.md`;
- **números e contagens já escritos no README actual** (quantas abas, quantos endpoints, quantos testes, quantos scripts) contra o que o código tem agora. Um README mantido ao longo de várias sessões acumula facilmente contagens desactualizadas que ninguém volta a recontar — tratar qualquer número no README como uma afirmação a verificar, não como facto assumido.

## Score

Calcular um score interno de 0 a 100.

Critérios:

| Área | Peso |
|---|---:|
| Clareza do projecto | 15 |
| Estrutura documental | 15 |
| Instalação e configuração | 15 |
| Utilização | 10 |
| Stack e versões | 10 |
| Arquitectura | 10 |
| Qualidade visual | 10 |
| Testes e qualidade | 5 |
| Deployment | 5 |
| Contribuição e licença | 5 |

Apresentar, quando solicitado, o score antes e depois — mesmo numa passagem cirúrgica (ver secção seguinte), o score não exige uma reescrita completa para ser calculado.

## Quando o README já é maduro

Nem todo o README a rever está desactualizado ou mal estruturado. Alguns já são tecnicamente exactos, mantidos a cada sessão de trabalho, só com lacunas estruturais pontuais (falta um logo, uma tabela de stack, uma secção de testes, um número desactualizado).

Quando a auditoria mostrar isto, **não fazer uma reescrita completa**. Uma reescrita larga arrisca perder detalhe verificado com esforço (notas de incidentes, troubleshooting exacto, histórico de decisões, avisos específicos do projecto) só para o encaixar num template genérico — e isso é pior do que o README original, mesmo que visualmente mais "limpo".

Nesse caso, o trabalho correcto é uma passagem de correcções cirúrgicas:

- corrigir só as secções desactualizadas (números errados, listas que já não batem certo com o código, secções que descrevem uma versão antiga da funcionalidade);
- acrescentar só o que falta claramente, nos sítios onde a estrutura já existente sugerir (badges, logo, tabela de stack, secção de testes), sem forçar a reordenação de secções já boas só para bater com a "Ordem preferencial" abaixo;
- nunca apagar ou reescrever uma secção só porque não está no template recomendado, se já for tecnicamente correcta e útil ao leitor.

A "Ordem preferencial" e a lista de secções da próxima secção são o ponto de partida para um README novo ou muito desorganizado — não uma checklist a impor sobre um README já maduro.

## Estrutura recomendada

A estrutura deve ser adaptada ao projecto. Não criar secções vazias.

Ordem preferencial:

```text
# Project Name

Short project description

Badges

Optional hero image / demo

## Overview

## Features

## Tech Stack

## Architecture

## Getting Started

### Prerequisites

### Installation

### Configuration

### Usage

## Testing

## Project Structure

## API

## Deployment

## Roadmap

## Contributing

## License
```

Eliminar secções que não tenham conteúdo útil.

## Hero

Quando existir uma imagem ou demonstração real, pode ser colocada perto do topo.

**Procurar sempre um logo já existente antes de assumir que não há nenhum** — não esperar que o utilizador o peça. Verificar na raiz e em pastas óbvias: `logo.png`, `logo.svg`, `banner.png`, `icon.png`, `.github/logo.*`, `docs/logo.*`, `assets/logo.*`, `assets/banner.*`. Um logo real que já existe no repositório mas nunca foi usado no README é uma peça em falta, não uma imagem fictícia — inserir.

Não criar imagens fictícias.

Pode utilizar:

```html
<p align="center">
  <img src="..." alt="Project preview">
</p>
```

**Logos com texto/traços claros sobre fundo transparente** costumam só ler bem em fundo escuro — testar mentalmente a legibilidade nos dois temas do GitHub (claro e escuro) antes de o inserir tal como está. Se o logo só funcionar sobre fundo escuro, envolvê-lo num contentor com uma cor de fundo explícita — a cor de marca do próprio projecto, não um cinzento genérico — em vez de o deixar invisível em modo claro:

```html
<p align="center">
  <img src="logo.png" alt="Project" width="420"
       style="background:#0a1622;border-radius:14px;padding:20px 30px;">
</p>
```

Isto não é inventar uma imagem nova; é tornar legível a imagem real que já existe, em qualquer tema.

Quando o projecto for essencialmente uma biblioteca, CLI ou ferramenta técnica, preferir uma apresentação textual limpa em vez de uma imagem decorativa.

## Badges segmentados

O estilo visual preferencial é inspirado em badges segmentados profissionais:

```text
┌──────────┬────────┐
│  PYTHON  │  3.12+ │
└──────────┴────────┘
```

Usar Shields.io quando apropriado.

Template:

```markdown
<p align="center">
  <img src="https://img.shields.io/badge/PYTHON-3.12%2B-3776AB?style=flat-square&logo=python&logoColor=white" alt="Python 3.12+">
  <img src="https://img.shields.io/badge/FLASK-3.1.2-000000?style=flat-square&logo=flask&logoColor=white" alt="Flask 3.1.2">
</p>
```

### Regras dos badges

- Preferir `style=flat-square`.
- Usar texto em maiúsculas na etiqueta.
- Usar logos oficiais quando disponíveis.
- Manter dimensões e espaçamento consistentes.
- Não exagerar no número de badges.
- Priorizar tecnologias relevantes.
- Incluir versões apenas quando verificadas.
- Usar badges de estado, CI, licença ou cobertura apenas quando a origem puder ser confirmada.
- Não criar badges para tecnologias que apenas aparecem em documentação ou comentários sem utilização demonstrável.
- O texto de um badge (label e value, na URL do Shields.io) tem de ser seguro em URL — acentos e outros caracteres especiais não codificados partem o badge ou tornam-no imprevisível. Usar `_` para espaços (já é a convenção do Shields.io) e preferir a forma sem acentos de uma palavra em vez de a percent-encodar à mão.

### Categorias

Prioridade:

1. Linguagem principal.
2. Framework principal.
3. Runtime ou plataforma relevante.
4. Base de dados.
5. IA/modelo principal.
6. Testes.
7. CI/CD.
8. Deployment.
9. Licença.

Exemplo:

```markdown
<p align="center">

<img src="https://img.shields.io/badge/PYTHON-3.12%2B-3776AB?style=flat-square&logo=python&logoColor=white">
<img src="https://img.shields.io/badge/FASTAPI-0.115-009688?style=flat-square&logo=fastapi&logoColor=white">
<img src="https://img.shields.io/badge/POSTGRESQL-16-4169E1?style=flat-square&logo=postgresql&logoColor=white">
<img src="https://img.shields.io/badge/LICENSE-MIT-D4B900?style=flat-square">

</p>
```

Não copiar estes valores para projectos diferentes. Detectá-los.

## Paleta dos badges

Quando for necessário criar badges personalizados, preferir cores associadas à tecnologia.

Exemplos:

- Python: `3776AB`
- Flask: `000000`
- FastAPI: `009688`
- PostgreSQL: `4169E1`
- Docker: `2496ED`
- Node.js: `339933`
- React: `61DAFB`
- TypeScript: `3178C6`
- GitHub Actions: `2088FF`
- OpenAI: usar a identidade visual disponível no Shields.io, sem assumir uma cor como facto técnico.

O badge de licença pode utilizar uma cor dourada discreta quando o estilo visual do projecto justificar.

## Descrição

A primeira descrição deve responder rapidamente:

1. O que é?
2. Para quem é?
3. Qual o problema que resolve?
4. Qual a principal característica diferenciadora?

Evitar frases vagas como:

> This is an innovative project that uses cutting-edge technology.

Preferir:

> A local-first Python service that extracts structured data from X and exposes it through a REST API.

## Features

Usar uma lista curta.

Exemplo:

```markdown
## Features

- Fast REST API
- Automatic data validation
- Persistent PostgreSQL storage
- Docker-based development environment
- Automated test suite
```

Não listar funcionalidades apenas planeadas como se já existissem.

Separar funcionalidades futuras no `Roadmap`.

## Tech Stack

Mostrar apenas tecnologias efectivamente utilizadas.

Exemplo:

```markdown
| Layer | Technology |
|---|---|
| Language | Python |
| API | FastAPI |
| Database | PostgreSQL |
| Testing | Pytest |
| Deployment | Docker |
```

## Architecture

Criar Mermaid quando a arquitectura tiver relações que beneficiem de representação visual.

Exemplo:

```mermaid
flowchart LR
    Client --> API
    API --> Service
    Service --> Database
```

O diagrama deve reflectir a arquitectura real detectada.

Não criar diagramas ornamentais sem informação.

## Installation

Os comandos devem corresponder aos ficheiros do projecto.

Python:

```bash
git clone <verified-repository-url>
cd <verified-directory>

python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

Windows, quando relevante:

```powershell
python -m venv .venv
.venv\Scripts\Activate.ps1
pip install -r requirements.txt
```

Node:

```bash
npm install
npm run dev
```

Nunca escrever comandos que não existam ou não sejam compatíveis com o projecto.

## Configuration

Detectar `.env.example`, ficheiros de configuração e variáveis utilizadas.

Apresentar uma tabela:

```markdown
| Variable | Required | Description |
|---|---|---|
| `DATABASE_URL` | Yes | Database connection string |
| `API_KEY` | Yes | API authentication key |
```

Nunca expor secrets.

Nunca colocar valores reais de credenciais.

## Usage

Dar primeiro o caminho mais simples para executar o projecto.

Quando existir uma CLI, API ou aplicação web, incluir exemplos reais.

## API

Só criar documentação de API se existirem endpoints verificáveis.

Para REST:

```markdown
| Method | Endpoint | Description |
|---|---|---|
| GET | `/health` | Health check |
| GET | `/items` | List items |
```

Não inventar endpoints.

## Testing

Detectar framework e comandos.

Exemplos:

```bash
pytest
```

ou:

```bash
npm test
```

Só apresentar o comando correspondente ao projecto.

Não afirmar que os testes passam sem os executar ou sem evidência fornecida.

## Project Structure

Representar apenas paths relevantes.

Exemplo:

```text
project/
├── src/
│   ├── api/
│   ├── services/
│   └── models/
├── tests/
├── .env.example
├── Dockerfile
└── README.md
```

Não gerar árvores gigantescas.

## Deployment

Documentar apenas plataformas detectadas.

Exemplos possíveis:

- Docker
- GitHub Actions
- Vercel
- Netlify
- Cloud Run
- AWS
- Azure

Se apenas existir configuração parcial, dizê-lo explicitamente.

## Roadmap

Separar:

```markdown
### Planned

- Feature not yet implemented
```

de:

```markdown
### Completed

- Feature already implemented
```

Nunca transformar ideias ou TODOs em funcionalidades existentes.

## Contributing

Para projectos públicos, incluir instruções mínimas quando fizer sentido:

```text
Fork
→ Create branch
→ Make changes
→ Run tests
→ Open pull request
```

Não criar regras de contribuição complexas sem evidência no projecto.

## License

Detectar a licença existente.

Se existir `LICENSE`, usar o nome correcto.

Se não existir, não assumir MIT.

## GitHub discoverability

Melhorar a capacidade de compreensão do projecto por:

- GitHub;
- developers;
- recrutadores;
- ferramentas de pesquisa;
- sistemas de IA.

Usar termos técnicos naturais.

Não fazer keyword stuffing.

O nome do projecto, descrição, funcionalidades e stack devem aparecer de forma clara e coerente.

## Estilo editorial

Escrever em inglês por defeito quando o README estiver orientado para uma audiência internacional.

Preservar o idioma existente quando o projecto estiver claramente dirigido a uma audiência local.

Preferir:

- frases curtas;
- linguagem técnica precisa;
- títulos consistentes;
- tabelas quando melhoram a leitura;
- exemplos reais;
- código directamente executável;
- pouco texto decorativo.

Evitar:

- marketing exagerado;
- emojis em excesso;
- frases genéricas;
- secções vazias;
- texto redundante;
- afirmações não verificadas.

## Validação final

Antes de concluir, verificar:

```text
[ ] README.md é Markdown válido
[ ] Título identifica correctamente o projecto
[ ] Descrição corresponde ao projecto
[ ] Badges correspondem ao stack real
[ ] Versões foram verificadas
[ ] Comandos existem ou são coerentes com os scripts reais
[ ] Paths apresentados existem
[ ] Variáveis de ambiente foram verificadas
[ ] Endpoints foram verificados
[ ] Arquitectura corresponde ao código/configuração
[ ] Licença corresponde ao ficheiro existente
[ ] Não existem secrets
[ ] Não existem placeholders acidentais
[ ] Funcionalidades futuras estão separadas
[ ] Não existem secções vazias
[ ] Mermaid representa arquitectura real
```

## Resultado

Quando o trabalho estiver concluído, devolver:

1. README final.
2. Score antes/depois, quando houver README anterior.
3. Resumo das principais melhorias.
4. Itens que ficaram por confirmar.
5. Eventuais ficheiros que deveriam ser actualizados em conjunto, como `.env.example` ou documentação adicional.

## Princípio final

Um README profissional não é o README mais longo.

É aquele que permite a alguém perceber o projecto, instalar, executar, testar e compreender a arquitectura com o mínimo de fricção possível.
