# Como a Web Funciona

A web é uma conversa constante entre o seu navegador e servidores espalhados pelo mundo. Tudo que você acessa online passa por esse processo.

---

## HTTP e HTTPS

- **HTTP** — protocolo de transferência de dados na web
- **HTTPS** — versão segura do HTTP com criptografia
- Criptografia embaralha os dados com uma chave secreta
- Cada navegação gera uma chave aleatória única
- A chave é tão complexa que é praticamente indecifrável
- 🔒 Cadeado no navegador = conexão segura
- ⚠️ Sem cadeado = dados podem ser interceptados

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

Toda comunicação na web segue o modelo de pedido e resposta:

- **Request** — solicitação feita pelo navegador ao servidor
- **Response** — resposta do servidor a essa solicitação

### Métodos HTTP

O HTTP é o protocolo de comunicação entre navegador e servidor. Os métodos HTTP são os **tipos de pedido** que você pode fazer dentro dessa comunicação — eles indicam a intenção do pedido.

É como um formulário de atendimento onde você marca o que quer fazer:

| Método | Intenção | Exemplo real |
|---|---|---|
| GET | Buscar/consultar dados | Abrir o Instagram |
| POST | Enviar/cadastrar dados | Postar uma foto |
| PUT | Substituir dados inteiros | Reescrever o perfil completo |
| PATCH | Alterar parte dos dados | Editar só a bio |
| DELETE | Excluir dados | Deletar um story |

Quando o navegador faz um request ao servidor, ele diz não só *onde* quer chegar, mas *o que quer fazer* — e é isso que o método define.

### Exemplos práticos

- Abrir uma página → GET
- Criar uma conta → POST
- Atualizar seu perfil → PUT ou PATCH
- Deletar uma postagem → DELETE

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
