# Guia de Padronização — dev-joaocarvalho

> Convenções adotadas em todos os repositórios a partir de agora.
> Baseado em PEP 8, Conventional Commits e boas práticas de OSS.

---

## 1. Nomenclatura de Repositórios

| Padrão | Exemplo |
|---|---|
| `kebab-case` sempre | ✅ `immunity-dashboard` |
| Sem `-main`, `-master`, `-v2` no nome | ✅ `jogo-memoria` ❌ `Jogo-Da-Memoria-main` |
| Sem `Projeto-`, `Desafio-`, `teste-` genéricos | ✅ `clip-check` ❌ `projeto-clipcheck` |
| Sem letras maiúsculas | ✅ `virtual-pet` ❌ `Virtual-Pet-Simulator` |
| Descritivo e curto (máx. 4 palavras) | ✅ `analise-algoritmos-unb` |

**Repositórios atuais → nomes sugeridos:**
```
Desafio-Jogo-Da-Memoria-De-Numeros-main  →  jogo-memoria-numeros
Projeto-Immunity-Dashboard-main          →  immunity-dashboard
projeto-clipcheck                        →  clip-check
virtual-pet-simulator-main               →  virtual-pet
a-algo-2026-1                            →  algoritmos-unb-2026
sandbox                                  →  manter (nome intencional ✅)
```

---

## 2. Nomenclatura de Arquivos Python (PEP 8)

```
✅  snake_case para tudo
❌  hífens, espaços, CamelCase em nomes de arquivo
```

| Tipo | Padrão | Exemplo |
|---|---|---|
| Scripts | `snake_case.py` | `analise_dados.py` |
| Módulos | `snake_case.py` | `processador_csv.py` |
| Classes (dentro do .py) | `PascalCase` | `class AnaliseDados:` |
| Funções e variáveis | `snake_case` | `def carregar_dados():` |
| Constantes | `UPPER_SNAKE_CASE` | `MAX_LINHAS = 1000` |
| Arquivos de teste | `test_<nome>.py` | `test_analise_dados.py` |

**Exemplos práticos:**
```python
# ❌ Errado
def calculaMedia(lista):
    totalItens = len(lista)
    return sum(lista)/totalItens

# ✅ Certo (PEP 8)
def calcula_media(lista: list[float]) -> float:
    total_itens = len(lista)
    return sum(lista) / total_itens
```

---

## 3. Estrutura de Projeto Python

```
meu-projeto/
├── src/
│   └── meu_projeto/
│       ├── __init__.py
│       └── main.py
├── tests/
│   └── test_main.py
├── data/               # datasets, CSVs (nunca commitar dados sensíveis)
│   └── .gitkeep
├── notebooks/          # Jupyter notebooks de exploração
│   └── exploracao.ipynb
├── .flake8
├── pyproject.toml
├── requirements.txt
├── .gitignore
└── README.md
```

---

## 4. Mensagens de Commit (Conventional Commits)

```
<tipo>(<escopo>): <descrição curta em português>
```

| Tipo | Quando usar |
|---|---|
| `feat` | nova funcionalidade |
| `fix` | correção de bug |
| `docs` | alteração em documentação |
| `style` | formatação, PEP 8, sem mudança de lógica |
| `refactor` | refatoração sem nova feature |
| `test` | adição ou correção de testes |
| `chore` | tarefas de manutenção (deps, config) |
| `data` | adição ou atualização de dados/datasets |

**Exemplos:**
```
feat(dashboard): adiciona filtro por período no gráfico
fix(scraper): corrige encoding UTF-8 na leitura do CSV
docs(readme): atualiza instruções de instalação
style: aplica PEP 8 em todos os módulos
refactor(analise): separa lógica de limpeza em função própria
chore: atualiza dependências do requirements.txt
data: adiciona base de beneficiários 2025-Q1
```

**Regras:**
- Máximo 72 caracteres na primeira linha
- Imperativo: "adiciona", "corrige", "remove" — não "adicionado" ou "adicionando"
- Sem ponto final
- Escopo opcional mas recomendado

---

## 5. Branches

```
main          →  produção / versão estável
dev           →  desenvolvimento contínuo
feat/<nome>   →  nova funcionalidade
fix/<nome>    →  correção
docs/<nome>   →  documentação
```

**Exemplos:**
```
feat/filtro-data-dashboard
fix/encoding-csv
docs/atualiza-readme
```

---

## 6. .gitignore padrão para projetos Python/Data Science

```gitignore
# Python
__pycache__/
*.py[cod]
*.egg-info/
dist/
build/
.eggs/
venv/
.env

# Jupyter
.ipynb_checkpoints/
*.ipynb_checkpoints

# Dados sensíveis
*.csv
*.xlsx
*.json
data/raw/
!data/.gitkeep

# IDEs
.vscode/
.idea/
*.DS_Store

# Relatórios gerados
reports/
*.html
!README.md
```

---

## 7. Descrições de Repositório

Todo repo deve ter:
- ✅ Descrição curta (1 linha) preenchida no GitHub
- ✅ Topics/tags relevantes (ex: `python`, `data-analysis`, `unb`, `machine-learning`)
- ✅ README.md com pelo menos: o que é, como rodar, tecnologias usadas

---

*Guia criado em junho/2026 — revisar a cada semestre.*
