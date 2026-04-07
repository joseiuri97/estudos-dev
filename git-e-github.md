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