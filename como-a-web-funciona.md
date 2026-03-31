# Como a Web Funciona

## HTTP vs HTTPS
- HTTP: protocolo de transferência de dados na web
- HTTPS: versão segura do HTTP com criptografia
- Criptografia embaralha os dados com uma chave secreta
- Cada navegação gera uma chave aleatória única
- A chave é tão complexa que é praticamente indecifrável
- 🔒 Cadeado no navegador = conexão segura
- ⚠️ Sem cadeado = dados podem ser interceptados

## Servidor
- Computador ligado 24h esperando pedidos
- Armazena os arquivos do site (HTML, CSS, JS)
- Responde com os arquivos quando recebe um pedido

## DNS (Domain Name System)
- Funciona como uma agenda telefônica da internet
- Transforma nomes (google.com) em endereços IP (142.250.80.46)
- Sem o DNS teríamos que decorar números para acessar sites

## Como o navegador carrega uma página
1. Você digita o endereço no navegador
2. O DNS transforma o nome em IP
3. O navegador faz um pedido ao servidor
4. O servidor responde com os arquivos HTML, CSS e JS
5. O navegador lê os arquivos e monta a página na tela

## Velocidade
- Todo esse processo acontece em milissegundos
- Depende da velocidade da internet, localização do servidor e tamanho dos arquivos
- Sites pesados demoram mais porque têm mais arquivos para carregar