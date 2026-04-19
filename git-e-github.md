# Git e GitHub

## Inicializando um repositório Git
1. Criar pasta para o projeto
2. Clicar com botão direito dentro da pasta → "Open Git Bash Here"
3. Digitar `git init` → cria uma subpasta oculta `.git`

> O `git init` é o ponto de partida do projeto. Feito apenas uma vez por projeto.

## Comandos principais
| Comando | O que faz |
|---|---|
| `git add .` | Seleciona todos os arquivos para a próxima versão |
| `git add arquivo.txt` | Seleciona apenas um arquivo específico |
| `git status` | Verifica se os arquivos foram adicionados |
| `git commit -m "mensagem"` | Salva/registra a versão com uma descrição |
| `git push` | Envia as versões salvas para o GitHub |

## Conectando ao GitHub
| Comando | O que faz |
|---|---|
| `git remote add origin URL` | Liga o repositório local ao repositório remoto |

> Feito apenas uma vez por projeto, antes do primeiro push.

## Processo completo — primeira vez
1. `git init` → cria repositório local
2. `git add .` → seleciona os arquivos
3. `git commit -m "primeiro commit"` → salva a primeira versão
4. `git remote add origin URL` → liga ao repositório remoto
5. `git push -u origin main` → envia para o GitHub

## Após a primeira vez
1. `git add .` → seleciona os arquivos
2. `git commit -m "descrição da mudança"` → salva a primeira versão
3. `git push` → envia para o GitHub

## Conceitos importantes
- **Main** — tronco principal do projeto
- **Branch** — ramificação ou galho. Usado para desenvolver uma funcionalidade sem estragar o código principal

## Observação pessoal
- O GitHub Desktop facilita o processo de commit com uma interface visual

## Versionamento
É o controle das diferentes versões do projeto ao longo do tempo.
Cada commit é uma versão salva. Se algo der errado, é possível voltar para uma versão anterior.

**Exemplo:**
- Versão 1 → portfólio simples com nome e contato
- Versão 2 → adicionou seção de projetos
- Versão 3 → reformulou o visual completo

O GitHub armazena esse histórico de versões.

## Issue
É uma forma de comunicação dentro de um repositório no GitHub. Pode ser usada para:

- 🐛 Reportar um bug — "Encontrei um erro na calculadora"
- 💡 Sugerir uma melhoria — "Seria legal adicionar modo escuro"
- ❓ Fazer uma pergunta — "Como faço para rodar o projeto?"
- 📋 Registrar uma tarefa — "Preciso criar a página de contato"

Qualquer pessoa pode abrir uma issue em repositórios públicos.

## Fork
É uma cópia de um repositório de outra pessoa para a sua conta no GitHub.

**Para que serve:**
- Estudar o código de outra pessoa
- Fazer melhorias sem afetar o original
- Enviar um Pull Request com suas alterações

**Diferença entre Fork e Clone:**
- Fork → copia o repositório para sua conta no GitHub
- Clone → baixa o repositório para o seu computador

Geralmente os dois são feitos juntos:
1. Fork → copia para sua conta
2. Clone → baixa para o PC

## Pull Request (PR)
É uma solicitação para que o dono de um repositório aceite suas alterações.

**Como funciona:**
1. Você faz um fork do projeto
2. Faz suas alterações
3. Envia um Pull Request: "Fiz melhorias, pode aceitar?"
4. O dono analisa e decide se aceita ou não

**Resumindo:**
- Issue → "Encontrei um problema"
- Pull Request → "Resolvi o problema, pode aceitar?"

## Markdown
É uma linguagem simples para formatar texto.
Usando símbolos como #, - e ** você cria títulos, listas e negritos.
É usada nos arquivos .md do GitHub.

**Principais símbolos:**
- `#` → título grande
- `##` → título médio
- `###` → título pequeno
- `-` → item de lista
- `**texto**` → **negrito**
- `*texto*` → *itálico*
- `` `texto` `` → código inline
- `---` → linha divisória

É como um Word simplificado, mas em texto puro.

# GitHub Pages

## O que é?

O GitHub Pages é um serviço gratuito do GitHub que transforma seu repositório em um site publicado na internet — acessível por qualquer pessoa.

---

## Como funciona?

O GitHub pega os arquivos do seu repositório (HTML, CSS, JS) e os publica automaticamente como um site. Não precisa pagar hospedagem, não precisa configurar servidor.

---

## Como ativar?

1. Acessa o repositório no GitHub
2. Clica em **Settings**
3. Clica em **Pages** no menu lateral
4. Em **Source** seleciona **Deploy from a branch**
5. Seleciona a branch **main** e a pasta **/ (root)**
6. Clica em **Save**
7. Aguarda alguns minutos e o site estará no ar

---

## Onde fica publicado?

O site fica disponível no endereço:

https://seu-usuario.github.io/nome-do-repositorio

Exemplos reais:
- joseiuri97.github.io/calculadora
- joseiuri97.github.io/app-notas
- joseiuri97.github.io/portfolio

---

## Observações importantes

- Após cada commit, o GitHub Pages demora alguns minutos para atualizar
- Funciona apenas com arquivos estáticos (HTML, CSS, JS) — não suporta backend
- É gratuito para repositórios públicos
