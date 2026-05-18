---

### DHCP

Protocolo que distribui IPs automaticamente para os dispositivos que se conectam à rede. Sem ele, você teria que configurar o IP manualmente em cada aparelho.

> **Analogia:** recepcionista que entrega um número de mesa quando você chega no restaurante.

---

### DNS — Domain Name System

Traduz nomes de domínio (`google.com`) em endereços IP (`142.250.80.46`). Sem o DNS você teria que decorar o IP de cada site.

> **Analogia:** agenda telefônica — você procura o nome, ela te dá o número.

---

## HTTP e HTTPS

O **HTTP** é o protocolo de comunicação da web — um conjunto de regras que define como navegador e servidor se comunicam. Tudo que acontece quando você acessa um site segue essas regras.

O **HTTPS** é a versão segura do HTTP, com criptografia:

- Embaralha os dados com uma chave secreta
- Cada navegação gera uma chave aleatória única
- A chave é tão complexa que é praticamente indecifrável
- 🔒 Cadeado no navegador = conexão segura
- ⚠️ Sem cadeado = dados podem ser interceptados

**O HTTP é como um idioma**

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

## Request e Response

Toda comunicação na web segue o modelo de pedido e resposta — como um restaurante:

- Cliente (você) → digita o endereço no navegador
- Garçom (navegador) → envia o **request** via HTTP ao servidor
- Cozinha (servidor) → processa e envia o **response**
- Garçom (navegador) → recebe e exibe a página na tela

---

## Métodos HTTP

Os métodos HTTP são os **tipos de pedido** que você pode fazer — eles indicam a intenção do pedido:

| Método | Intenção | Exemplo real |
|---|---|---|
| GET | Buscar/consultar dados | Abrir o Instagram |
| POST | Enviar/cadastrar dados | Postar uma foto |
| PUT | Substituir dados inteiros | Reescrever o perfil completo |
| PATCH | Alterar parte dos dados | Editar só a bio |
| DELETE | Excluir dados | Deletar um story |

---

## Status codes

Códigos que o servidor envia na response para informar o resultado do pedido:

| Código | Significado |
|---|---|
| 200 | OK — deu certo |
| 301 | Redirecionamento permanente |
| 404 | Página não encontrada |
| 500 | Erro interno no servidor |

---

## Cookies

O HTTP não tem memória — cada request é tratado como se fosse o primeiro. Os cookies resolvem isso.

É como um cartãozinho que o restaurante te entrega na primeira visita. Na próxima vez que você chega, você mostra o cartão e o garçom já sabe quem você é.

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

---

## Portas

Número que identifica qual serviço ou aplicação deve receber os dados dentro de um dispositivo. O IP encontra a máquina; a porta encontra o programa certo dentro dela.

> **Analogia:** IP = prédio. Porta = apartamento específico.

| Protocolo | Porta |
|---|---|
| HTTP | 80 |
| HTTPS | 443 |
| SSH | 22 |
| DNS | 53 |
| SMTP | 25 |

---

## TCP e UDP

**TCP** — garante que todos os dados chegam na ordem certa. Mais lento, mas confiável. Usado em e-mails, downloads, HTTP.

**UDP** — envia sem confirmar recebimento. Mais rápido, mas pode perder pacotes. Usado em games, chamadas de vídeo, live streaming.

> TCP = carta registrada. UDP = grito pela janela.

---

## Conceitos complementares

### Pacotes

Dados são divididos em pequenos blocos chamados **pacotes** antes de serem enviados pela rede. Cada pacote pode tomar um caminho diferente e são remontados no destino.

> **Analogia:** livro desmontado em páginas avulsas, cada uma enviada por uma transportadora diferente, e remontadas na chegada.

---

### LAN, MAN e WAN

- **LAN** (Local Area Network) — rede de curto alcance: sua casa, sua empresa.
- **MAN** (Metropolitan Area Network) — escala de uma cidade.
- **WAN** (Wide Area Network) — a própria internet é uma WAN global.

---

### VPN

Virtual Private Network — cria um "túnel" criptografado entre seu dispositivo e um servidor, escondendo seu tráfego e IP real.

> **Analogia:** tubo subterrâneo privado dentro da rodovia pública.

---

### Largura de banda e latência

- **Largura de banda** — quantidade de dados que pode trafegar ao mesmo tempo (Mbps, Gbps).
- **Latência** — tempo que um pacote leva para ir e voltar (ms). Em games online, a latência importa mais do que a banda.

> **Analogia:** banda = largura da estrada. Latência = velocidade dos carros.