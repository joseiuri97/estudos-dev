# Indentação

Indentação é o recuo (espaçamento) no início das linhas que mostra a hierarquia do código — quem está dentro de quem.

---

## Por que é importante?

- Torna o código mais fácil de ler e entender
- Ajuda a identificar erros de lógica
- É esperado por qualquer desenvolvedor que ler seu código
- Algumas linguagens como Python **exigem** indentação correta para funcionar

---

## Como funciona

Cada vez que abre um bloco `{}`, o conteúdo interno recua um nível.
Cada vez que fecha `}`, volta um nível.

**Sem indentação** (difícil de ler):
```javascript
function calcular(x) {
if (x > 0) {
return x * 2;
} else {
return 0;
}
}
```

**Com indentação** (fácil de ler):
```javascript
function calcular(x) {
  if (x > 0) {
    return x * 2;
  } else {
    return 0;
  }
}
```

---

## Padrões do mercado

| Linguagem | Padrão |
|---|---|
| JavaScript | 2 espaços |
| Python | 4 espaços (obrigatório) |
| Java | 4 espaços |
| HTML/CSS | 2 espaços |

> A maioria dos times escolhe um padrão e usa em todo o projeto. O mais importante é ser consistente.

---

## Níveis de indentação

Cada bloco aberto adiciona um nível de recuo:

```javascript
function renderizarNotas() {        // nível 0
  notas.forEach(nota => {           // nível 1
    const card = document           // nível 2
      .createElement('div');
    card.innerHTML = `
      <h3>${nota.titulo}</h3>       // nível 3
    `;
  });
}
```

---

## No VS Code

- A tecla `Tab` já adiciona a indentação automaticamente
- Para indentar várias linhas de uma vez: selecione as linhas e pressione `Tab`
- Para remover a indentação: selecione as linhas e pressione `Shift + Tab`
- Para formatar o arquivo inteiro automaticamente: `Shift + Alt + F`

---

## Em HTML

```html
<div>                          <!-- nível 0 -->
  <header>                     <!-- nível 1 -->
    <h1>Minhas Notas</h1>      <!-- nível 2 -->
  </header>
  <main>                       <!-- nível 1 -->
    <div class="nota-card">    <!-- nível 2 -->
      <h3>Título</h3>          <!-- nível 3 -->
    </div>
  </main>
</div>
```

---

## Em CSS

```css
.nota-card {                   /* nível 0 */
  background: #fde68a;         /* nível 1 */
  border-radius: 12px;         /* nível 1 */
}

.nota-card h3 {                /* nível 0 */
  font-size: 16px;             /* nível 1 */
  color: #1e293b;              /* nível 1 */
}
```

---

*Fonte: estudos próprios — Sistemas de Informação*