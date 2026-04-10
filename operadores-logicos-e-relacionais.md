# Operadores Relacionais e Lógicos

## Operadores Relacionais
Comparam dois valores e retornam verdadeiro ou falso.

| Operador | Significado | Exemplo |
|---|---|---|
| `>` | maior que | 5 > 3 → verdadeiro |
| `<` | menor que | 2 < 1 → falso |
| `>=` | maior ou igual | 5 >= 5 → verdadeiro |
| `<=` | menor ou igual | 3 <= 4 → verdadeiro |
| `=` | igual a | 2 = 2 → verdadeiro |
| `<>` | diferente de | 3 <> 4 → verdadeiro |

## Operadores Lógicos
Combinam duas ou mais condições.

| Operador | Significado | Quando é verdadeiro |
|---|---|---|
| `e` | E (and) | Quando ambas as condições são verdadeiras |
| `ou` | OU (or) | Quando pelo menos uma condição é verdadeira |
| `nao` | NÃO (not) | Inverte o resultado |

## Exemplo prático
- `idade >= 18 e temCarteira = verdadeiro` → pode dirigir
- `temDinheiro ou temCartao` → pode pagar
- `nao estaChovendo` → pode sair sem guarda-chuva

## Nas linguagens de programação
| O que faz | Portugol | Python | JavaScript |
|---|---|---|---|
| Igual a | `=` | `==` | `===` |
| Diferente de | `<>` | `!=` | `!==` |
| E | `e` | `and` | `&&` |
| OU | `ou` | `or` | `\|\|` |
| NÃO | `nao` | `not` | `!` |