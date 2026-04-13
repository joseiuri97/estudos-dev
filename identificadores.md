# Regras de Nomeação de Identificadores

Identificadores são os nomes que você dá para variáveis, funções, classes e qualquer outra coisa que você cria no código.

---

## Regras Obrigatórias

Se quebrar uma dessas regras, o código não funciona:

- Não pode começar com número → `1nome` ❌ | `nome1` ✅
- Não pode ter espaço → `minha variavel` ❌ | `minhaVariavel` ✅
- Não pode usar palavras reservadas → `var`, `function`, `if`, `return`, `class` etc.
- Pode usar letras, números, `_` e `$`

---

## Convenções de Nomenclatura

Não quebra o código, mas é o padrão usado no mercado:

| Estilo | Exemplo | Usado para |
|---|---|---|
| camelCase | `minhaVariavel` | Variáveis e funções em JavaScript |
| PascalCase | `MinhaClasse` | Classes em JavaScript e Java |
| snake_case | `minha_variavel` | Python e banco de dados |
| SCREAMING_SNAKE_CASE | `VALOR_MAXIMO` | Constantes |
| kebab-case | `minha-classe` | Classes CSS e nomes de arquivos HTML |

---

## Exemplos Práticos

```javascript
// camelCase → variáveis e funções
let minhaVariavel = 10;
function calcularTotal() {}

// PascalCase → classes
class ContaBancaria {}

// SCREAMING_SNAKE_CASE → constantes
const TAXA_DE_JUROS = 0.05;
```

```css
/* kebab-case → classes no CSS */
.meu-botao {}
.nota-card {}
```

```python
# snake_case → Python
minha_variavel = 10
def calcular_total():
    pass
```

---

## No Mundo Real

Boas práticas que todo dev segue:

- **Seja descritivo** → `calcularTotal()` é melhor que `ct()`
- **Evite abreviações** → `usuario` é melhor que `usr`
- **Use o idioma do projeto** → se o time usa inglês, use inglês em tudo
- **Seja consistente** → escolha um estilo e mantenha em todo o projeto

---

## Referência Rápida

| Linguagem | Variáveis | Funções | Classes | Constantes |
|---|---|---|---|---|
| JavaScript | camelCase | camelCase | PascalCase | SCREAMING_SNAKE |
| Python | snake_case | snake_case | PascalCase | SCREAMING_SNAKE |
| Java | camelCase | camelCase | PascalCase | SCREAMING_SNAKE |
| CSS | kebab-case | — | kebab-case | — |

---

*Fonte: estudos próprios — Sistemas de Informação*