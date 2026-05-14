# Git e GitHub

## Criação de pasta via terminal do VS Code

- `cd ~/nome-da-pasta-destino` — acessa a pasta onde quero salvar a nova pasta
  - Se a pasta estiver fora da home (pasta principal do computador): `cd ~/nome-da-primeira-pasta/nome-da-nova-pasta`
- `mkdir nome-da-pasta` — cria a pasta. Vem de *make directory* (criar diretório)
- `cd nome-da-pasta` — entra na pasta criada
- `code .` — abre a pasta no VS Code

---

## Iniciando um novo projeto

```bash
git init
git remote add origin + url do repositório do GitHub
git add .
git commit -m "mensagem"
git push -u origin main
```

- `git init` — inicializa um repositório Git dentro da pasta. Cria uma pasta oculta chamada `.git` que guarda todo o histórico
- `git remote add origin + url` — conecta o repositório local ao repositório remoto no GitHub
- `git push -u origin main` — apenas na primeira vez de cada repositório novo
- Nos pushes seguintes do mesmo repositório: apenas `git push`

> Depois que a pasta já existe e o Git já está ativado, você nunca mais precisa repetir esses passos para aquele projeto.

---

## Boas práticas de mensagem de commit

✅ "adiciona formulário de cadastro"  
✅ "corrige bug no botão de salvar"  
✅ "atualiza cores do header"  
❌ "arrumei"  
❌ "mudanças"  
❌ "asjdklasd"  

---

## O que é um repositório

É onde o código vai ser armazenado. Cada projeto conta com um repositório.

---

## Comandos Git

- `git status` — verifica o estado atual das alterações no repositório. Mostra:
  - em qual branch você está
  - quais arquivos foram modificados mas ainda não foram adicionados
  - quais arquivos foram adicionados com `git add` mas ainda não foram commitados
  - se está tudo limpo: *"nothing to commit"*

- `git add .` — adiciona todos os arquivos modificados de uma vez
- `git add nome-do-arquivo.html` — adiciona apenas um arquivo específico

- `git pull` — puxa as alterações feitas no GitHub para a máquina local

- `git clone https://github.com/usuario/repositorio.git .` — clona um repositório. O ponto simboliza clonar no diretório atual

- `git rm` — remove um arquivo

- `git log` — mostra o histórico de alterações no terminal. No macOS pressione `Q` para sair

- `git mv` — move ou renomeia arquivos
  - Renomear: `git mv nome-antigo.ext nome-novo.ext`
  - Mover: `git mv arquivo.ext pasta/arquivo.ext`

- `git checkout -- arquivo` — retorna o arquivo ao último estado commitado, descartando alterações não salvas. Também usado para mudar de branch: `git checkout nome-da-branch`

- `.gitignore` — arquivo que lista pastas e arquivos que o Git deve ignorar e não rastrear no repositório

- `git reset` — reseta mudanças feitas

---

## Branches

Branch é uma ramificação independente do projeto onde você pode trabalhar sem afetar o código principal. Quando um projeto é criado ele inicia na branch `master` ou `main`.

- `git branch` — lista as branches do projeto
- `git branch nome-da-branch` — cria uma nova branch
- `git branch -d nome-da-branch` ou `git branch --delete nome-da-branch` — remove uma branch
- `git checkout nome-da-branch` — muda para outra branch
- `git checkout -b nome-da-branch` — cria a branch e já entra nela

> **Boa prática:** sempre commitar antes de mudar de branch para não arrastar alterações de uma branch para outra.  
> **Boa prática:** não deletar branches, a não ser que seja extremamente necessário.

---

## Merge

- `git merge nome-da-branch` — une o código de duas branches distintas

---

## Stash

- `git stash` — guarda temporariamente alterações não commitadas para mudar de branch sem perder o trabalho em andamento
- `git stash list` — verifica as stashes criadas
- `git stash apply número` — recupera uma stash (ex.: 0, 1, 2)
- `git stash drop número` — exclui uma stash específica
- `git stash clear` — limpa todas as stashes de uma branch

---

## Tags

- `git tag` — demarca estágios do desenvolvimento, como um checkpoint de uma branch

---

## Outros comandos úteis

- `ls` — mostra os arquivos da pasta atual no terminal
- `cd` — muda de diretório. Vem de *change directory*