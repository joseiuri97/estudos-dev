# Como a Web Funciona

A web é uma conversa constante entre o seu navegador e servidores espalhados pelo mundo. Tudo que você acessa online passa por esse processo.

---

## HTTP e HTTPS

O **HTTP** é o protocolo de comunicação da web — um conjunto de regras que define como navegador e servidor se comunicam. Tudo que acontece quando você acessa um site segue essas regras.

O **HTTPS** é a versão segura do HTTP, com criptografia:
- Embaralha os dados com uma chave secreta
- Cada navegação gera uma chave aleatória única
- A chave é tão complexa que é praticamente indecifrável
- 🔒 Cadeado no navegador = conexão segura
- ⚠️ Sem cadeado = dados podem ser interceptados

### O HTTP é como um idioma

Tudo que acontece na web faz parte desse idioma:

- **Request e Response** → o modelo de comunicação (pedido e resposta)
- **Métodos** → o tipo do pedido (GET, POST, PUT, PATCH, DELETE)
- **Status codes** → o resultado da resposta (200, 404, 500...)
- **Cookies** → o mecanismo de memória entre as comunicações

---

## Servidor

- Computador ligado 24h esperando pedidos
- Armazena os arquivos do site (HTML, CSS, JS)
- Responde com os arquivos quando recebe um pedido

---

## DNS (Domain Name System)

- Funciona como uma agenda telefônica da internet
- Transforma nomes (google.com) em endereços IP (142.250.80.46)
- Sem o DNS teríamos que decorar números para acessar sites

---

## Request e Response

Toda comunicação na web segue o modelo de pedido e resposta — como um restaurante:

- Cliente (você) → digita o endereço no navegador
- Garçom (navegador) → envia o **request** via HTTP ao servidor
- Cozinha (servidor) → processa e envia o **response**
- Garçom (navegador) → recebe e exibe a página na tela

---

## Métodos HTTP

Os métodos HTTP são os **tipos de pedido** que você pode fazer — eles indicam a intenção do pedido. Usando a analogia do restaurante:

| Método | Intenção | Exemplo real |
|---|---|---|
| GET | Buscar/consultar dados | Abrir o Instagram |
| POST | Enviar/cadastrar dados | Postar uma foto |
| PUT | Substituir dados inteiros | Reescrever o perfil completo |
| PATCH | Alterar parte dos dados | Editar só a bio |
| DELETE | Excluir dados | Deletar um story |

Quando o navegador faz um request ao servidor, ele diz não só *onde* quer chegar, mas *o que quer fazer* — e é isso que o método define.

---

## Status Codes

São os códigos que o servidor envia na response para informar o resultado do pedido:

| Código | Significado |
|---|---|
| 200 | OK — deu certo |
| 301 | Redirecionamento permanente |
| 404 | Página não encontrada |
| 500 | Erro interno no servidor |

Na analogia do restaurante: é o garçom voltando e dizendo "seu pedido está pronto" (200) ou "não temos esse prato" (404).

---

## Cookies

O HTTP não tem memória — cada request é tratado como se fosse o primeiro. Os cookies resolvem isso.

Usando a analogia do restaurante: é como um cartãozinho que o restaurante te entrega na primeira visita:

- 🍪 Nome: José Iuri
- 🍪 Pedido favorito: X-Burguer sem cebola
- 🍪 Última visita: hoje

Na próxima vez que você chega, você mostra o cartão e o garçom já sabe quem você é.

**O que os cookies guardam:**
- Sessão de login → para não precisar logar toda hora
- Preferências → idioma, tema, configurações
- Carrinho de compras → itens que você adicionou
- Histórico de navegação → para anúncios personalizados

> **Importante:** cookies não são maliciosos por natureza, mas podem ser usados para rastrear seus hábitos de navegação — por isso os sites são obrigados a pedir sua permissão.

---

## Como o navegador carrega uma página

1. Você digita o endereço no navegador
2. O DNS transforma o nome em IP
3. O navegador envia um **request** ao servidor via HTTP/HTTPS
4. O servidor processa e envia um **response** com os arquivos HTML, CSS e JS
5. O navegador lê os arquivos e monta a página na tela

---

## Velocidade

- Todo esse processo acontece em milissegundos
- Depende da velocidade da internet, localização do servidor e tamanho dos arquivos
- Sites pesados demoram mais porque têm mais arquivos para carregar
