###

### DHCP — Dynamic Host Configuration Protocol

O DHCP é o protocolo responsável por distribuir endereços IP automaticamente para os dispositivos que se conectam à rede.

Quando um dispositivo se conecta ao Wi-Fi, ele ainda não tem um IP — ele envia uma mensagem para a rede perguntando se há algum servidor disponível para atribuir um endereço. O roteador, que funciona como servidor DHCP, responde e atribui um IP disponível, junto com outras informações necessárias: a máscara de sub-rede, o endereço do gateway (o próprio roteador) e o endereço do servidor DNS.

Esse IP tem um prazo de validade chamado **lease** (concessão). Quando o prazo vence, o roteador pode renovar o mesmo IP ou atribuir outro disponível. Por isso o IP do seu celular pode mudar de um dia para o outro.

Sem o DHCP, você teria que configurar manualmente em cada dispositivo: o IP, a máscara de sub-rede, o gateway e o DNS — garantindo que nenhum dois aparelhos usassem o mesmo número. Em redes com dezenas ou centenas de dispositivos, isso seria inviável.

###

### DNS — Domain Name System

O DNS é o sistema que traduz nomes de domínio legíveis por humanos em endereços IP que os computadores entendem.

Quando você digita `google.com` no navegador, seu sistema operacional consulta um servidor DNS — geralmente configurado automaticamente pelo roteador via DHCP — e pergunta: "qual é o IP de google.com?". O servidor DNS responde com o endereço IP correspondente, por exemplo `142.250.80.46`. Só então o navegador consegue iniciar a conexão com o servidor do Google.

Essa consulta acontece em milissegundos e é transparente para o usuário. Sem o DNS, você teria que digitar o endereço IP de cada site que quisesse acessar.

Os servidores DNS formam uma hierarquia distribuída ao redor do mundo. Quando um servidor não sabe a resposta, ele repassa a consulta para outro acima dele na hierarquia até encontrar o responsável por aquele domínio.

---

## HTTP e HTTPS

O **HTTP** (HyperText Transfer Protocol) é o protocolo de comunicação da web. Ele define as regras de como o navegador faz pedidos ao servidor e como o servidor responde. Toda troca de informações entre navegador e servidor segue esse protocolo.

O **HTTPS** é a versão segura do HTTP. A diferença é que no HTTPS os dados são criptografados usando o protocolo **TLS** (Transport Layer Security) antes de serem enviados. Isso significa que mesmo que alguém intercepte o tráfego no meio do caminho, não conseguirá ler o conteúdo — os dados aparecem como texto embaralhado sem a chave correta para descriptografar.

- 🔒 Cadeado no navegador = conexão HTTPS — dados criptografados
- ⚠️ Sem cadeado = conexão HTTP — dados trafegam em texto aberto e podem ser interceptados

**O que o HTTP define:**

- **Request e Response** — o modelo de comunicação: o navegador faz um pedido (request) e o servidor devolve uma resposta (response)
- **Métodos** — o tipo de operação que está sendo solicitada (GET, POST, PUT, PATCH, DELETE)
- **Status codes** — códigos numéricos que o servidor envia para informar o resultado da requisição
- **Headers** — informações extras que acompanham cada requisição e resposta (tipo de conteúdo, idioma, cookies, etc.)
- **Cookies** — mecanismo de memória entre requisições

---

## Servidor

Um servidor web é um computador — geralmente ligado 24 horas por dia — que armazena os arquivos de um site (HTML, CSS, JavaScript, imagens, etc.) e fica aguardando requisições. Quando recebe um request de um navegador, processa o pedido e devolve os arquivos correspondentes como response.

Diferente do seu computador pessoal, servidores são otimizados para lidar com muitas conexões simultâneas e ficam em datacenters — locais com energia redundante, refrigeração e conexão de alta velocidade com a internet.

---

## Request e Response

Toda comunicação na web segue o modelo de pedido e resposta:

1. O navegador envia um **request** (pedido) ao servidor — especificando o que quer, usando qual método, e para qual endereço
2. O servidor processa o pedido e devolve um **response** (resposta) — contendo um status code e, geralmente, os dados solicitados

Esse ciclo acontece várias vezes só para carregar uma única página — uma requisição para o HTML, outra para o CSS, outra para cada imagem, etc.

---

## Métodos HTTP

Os métodos indicam a **intenção** da requisição — o que o navegador ou a aplicação quer fazer com aquele recurso no servidor:

| Método | Intenção | Exemplo real |
|---|---|---|
| GET | Buscar/consultar dados | Abrir uma página, carregar o feed do Instagram |
| POST | Enviar dados para criar algo novo | Criar uma conta, postar uma foto |
| PUT | Substituir um recurso inteiro | Reescrever todos os dados de um perfil |
| PATCH | Atualizar parte de um recurso | Editar só a bio do perfil |
| DELETE | Excluir um recurso | Deletar uma publicação |

---

## Status codes

São códigos numéricos que o servidor inclui na response para informar o resultado da requisição. Estão agrupados por faixas:

| Faixa | Significado geral |
|---|---|
| 2xx | Sucesso |
| 3xx | Redirecionamento |
| 4xx | Erro do lado do cliente |
| 5xx | Erro do lado do servidor |

Códigos mais comuns:

| Código | Significado |
|---|---|
| 200 | OK — requisição bem-sucedida |
| 201 | Created — recurso criado com sucesso |
| 301 | Moved Permanently — redirecionamento permanente |
| 400 | Bad Request — requisição mal formada |
| 401 | Unauthorized — autenticação necessária |
| 403 | Forbidden — acesso negado |
| 404 | Not Found — recurso não encontrado |
| 500 | Internal Server Error — erro interno no servidor |

---

## Cookies

O HTTP é um protocolo **stateless** — sem estado. Isso significa que cada requisição é completamente independente: o servidor não tem memória de requisições anteriores. Do ponto de vista do servidor, cada request é como se fosse o primeiro contato.

Os cookies resolvem isso. Quando você faz login em um site, o servidor cria um cookie — um pequeno arquivo de texto — e o envia para o seu navegador junto com a response. O navegador armazena esse cookie e o inclui automaticamente em todas as requisições seguintes para aquele site. Assim o servidor consegue identificar que você já está autenticado sem precisar pedir login a cada clique.

**O que os cookies armazenam:**

- **Sessão de login** — um token que identifica sua sessão autenticada, para não precisar logar toda hora
- **Preferências** — idioma escolhido, tema, configurações de layout
- **Carrinho de compras** — itens adicionados antes de finalizar a compra
- **Rastreamento** — identificadores usados para registrar seu comportamento de navegação entre sites, geralmente para fins publicitários

Os cookies de rastreamento são o motivo pelo qual os sites são legalmente obrigados a pedir sua permissão antes de os ativarem.

---

## Como o navegador carrega uma página

1. Você digita o endereço no navegador (ex: `https://google.com`)
2. O sistema operacional consulta o servidor DNS para descobrir o IP correspondente ao domínio
3. O navegador abre uma conexão TCP com o servidor no IP retornado pelo DNS, na porta 443 (HTTPS)
4. É feito o handshake TLS — negociação da criptografia entre navegador e servidor
5. O navegador envia um request GET para o servidor pedindo a página
6. O servidor processa e responde com o arquivo HTML
7. O navegador lê o HTML e identifica que precisa de outros recursos: arquivos CSS, JavaScript, imagens
8. Para cada recurso, um novo request é feito
9. Com todos os arquivos recebidos, o navegador monta e exibe a página na tela

---

## Velocidade de carregamento

O tempo que uma página leva para carregar depende de vários fatores:

- **Latência** — o tempo que os pacotes levam para ir do seu dispositivo ao servidor e voltar. Servidores geograficamente mais próximos têm menor latência.
- **Largura de banda** — a quantidade de dados que sua conexão consegue transferir por segundo (Mbps, Gbps). Conexões mais rápidas baixam os arquivos em menos tempo.
- **Tamanho dos arquivos** — páginas com muitas imagens em alta resolução, vídeos e scripts pesados demoram mais para carregar.
- **CDN** (Content Delivery Network) — rede de servidores distribuídos geograficamente que armazenam cópias dos arquivos do site. Quando você acessa um site que usa CDN, os arquivos vêm do servidor mais próximo de você, reduzindo a latência.

---

## Portas

A porta é um número que identifica qual serviço ou aplicação dentro de um dispositivo deve receber os dados. O endereço IP encontra a máquina na rede; a porta encontra o programa correto rodando dentro dessa máquina.

Quando seu navegador abre uma conexão com um servidor, ele especifica tanto o IP quanto a porta de destino. O sistema operacional do servidor recebe o dado e o direciona para o processo que está "escutando" naquela porta.

| Protocolo | Porta padrão |
|---|---|
| HTTP | 80 |
| HTTPS | 443 |
| SSH | 22 |
| DNS | 53 |
| SMTP (e-mail) | 25 |
| FTP | 21 |

As portas de 0 a 1023 são chamadas de **portas bem conhecidas** e são reservadas para serviços padrão. Portas acima de 1024 podem ser usadas livremente por aplicações.

---

## TCP e UDP

São os dois principais protocolos de transporte — responsáveis por controlar como os dados são enviados entre dois dispositivos.

**TCP — Transmission Control Protocol**

O TCP garante que todos os dados chegam ao destino, na ordem correta e sem erros. Antes de enviar qualquer dado, ele realiza um processo chamado **handshake de três vias**: os dois dispositivos trocam mensagens para estabelecer a conexão. Durante a transmissão, o receptor confirma o recebimento de cada pacote — se algum se perder no caminho, o remetente reenvia automaticamente.

É mais lento por causa desse controle, mas confiável. Usado em: HTTP/HTTPS, e-mail, transferência de arquivos, qualquer situação onde perder dados não é aceitável.

**UDP — User Datagram Protocol**

O UDP envia os pacotes sem estabelecer conexão prévia e sem confirmar se chegaram. É mais rápido e tem menos overhead, mas não garante entrega nem ordem dos pacotes.

Usado em: jogos online, chamadas de vídeo, transmissões ao vivo (live streaming), DNS. Nessas aplicações, a velocidade importa mais do que a perfeição — um frame perdido num vídeo é menos prejudicial do que um atraso causado por reenvios.

---

## Conceitos complementares

### Pacotes

Quando você envia dados pela rede — seja um arquivo, uma mensagem ou uma requisição HTTP — esses dados não são enviados de uma vez só. Eles são divididos em pequenos blocos chamados **pacotes**, cada um com um tamanho limitado.

Cada pacote carrega um pedaço dos dados junto com informações de controle: o endereço IP de origem, o endereço IP de destino, o número do pacote na sequência, entre outros. Pacotes diferentes podem percorrer caminhos diferentes pela rede e chegam ao destino em ordens variadas — o protocolo TCP se encarrega de remontá-los na ordem correta.

---

### LAN, MAN e WAN

- **LAN** (Local Area Network) — rede local de curto alcance: sua casa, sua empresa, sua faculdade. Alta velocidade, gerenciada pelo roteador local.
- **MAN** (Metropolitan Area Network) — rede que cobre uma cidade ou região metropolitana. Usada por operadoras e grandes empresas.
- **WAN** (Wide Area Network) — rede de longa distância. A internet é a maior WAN existente — uma rede global que interliga milhões de redes menores.

---

### VPN — Virtual Private Network

A VPN cria um túnel criptografado entre o seu dispositivo e um servidor VPN. Todo o seu tráfego de internet passa por esse túnel antes de chegar ao destino final — o que significa que sua operadora e outros intermediários na rede veem apenas dados criptografados indo para o servidor VPN, não o conteúdo real nem os sites que você está acessando.

Além da privacidade, a VPN também mascara seu IP real: os sites que você acessa enxergam o IP do servidor VPN, não o seu.

Muito usada em ambientes corporativos para que funcionários acessem sistemas internos da empresa de forma segura remotamente.

---

### Largura de banda e latência

**Largura de banda** é a capacidade máxima de dados que sua conexão consegue transferir por segundo, medida em Mbps (megabits por segundo) ou Gbps (gigabits por segundo). Quanto maior a largura de banda, mais dados podem trafegar ao mesmo tempo.

**Latência** é o tempo que um pacote leva para sair do seu dispositivo, chegar ao servidor e a resposta voltar — medida em milissegundos (ms). Uma latência baixa significa que a rede responde rápido.

Em um download de arquivo grande, a largura de banda importa mais — quanto maior, mais rápido o arquivo chega. Em jogos online e chamadas de vídeo, a latência importa mais — mesmo com banda alta, uma latência elevada causa atraso perceptível nas ações e na comunicação.