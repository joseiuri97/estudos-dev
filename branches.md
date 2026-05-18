# Branches no Git

Branch é uma ramificação do projeto — uma cópia paralela onde você trabalha sem mexer no código principal.

---

## Por que usar branches?

- A `main` sempre fica com o código funcionando
- Você testa coisas novas sem risco de quebrar o projeto
- Se algo der errado, descarta a branch — a `main` continua intacta
- Só une com a `main` quando tiver certeza que está funcionando

---

## master vs main

São a mesma coisa — apenas o nome da branch principal:

| Nome | Quando |
|---|---|
| `master` | Nome antigo, repositórios criados antes de 2020 |
| `main` | Nome atual, padrão do GitHub desde 2020 |

A mudança foi feita por questões culturais pela comunidade de tecnologia. Funcionam exatamente igual, só o nome é diferente.

---

## Fluxo seguro de trabalho

```bash
# 1. Cria uma branch nova para o que vai trabalhar
git checkout -b minha-feature

# 2. Faz as alterações e commita normalmente
git add .
git commit -m "descrição do que fiz"

# 3. Quando estiver pronto, volta para a main
git checkout main

# 4. Une a branch testada com a main (merge)
git merge minha-feature

# 5. Envia para o GitHub
git push origin main

# 6. Deleta a branch que não precisa mais
git branch -d minha-feature
```

---

## Comandos úteis

```bash
# Ver todas as branches
git branch

# Criar branch nova e já entrar nela
git checkout -b nome-da-branch

# Trocar de branch
git checkout nome-da-branch

# Unir branch com a main
git checkout main
git merge nome-da-branch

# Deletar branch
git branch -d nome-da-branch

# Ver branch atual
git status
```

---

## Exemplo prático

No projeto app-notas, cada funcionalidade poderia ter sido uma branch:

```bash
git checkout -b funcionalidade-lixeira
# trabalhou, testou, ficou bom...
git checkout main
git merge funcionalidade-lixeira
git branch -d funcionalidade-lixeira
```

---

## Boas práticas

- Nunca commite direto na `main` em projetos importantes
- Dê nomes descritivos para as branches → `funcionalidade-lixeira` é melhor que `teste`
- Delete as branches após o merge para manter o repositório limpo
- Uma branch por funcionalidade — não misture coisas diferentes na mesma branch

---