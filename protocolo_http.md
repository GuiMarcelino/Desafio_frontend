# protocolo http

## o que é http?

http (hypertext transfer protocol) é um protocolo de comunicação utilizado para transferir dados na web. ele define como mensagens são formatadas e transmitidas, e como os servidores e navegadores devem agir em resposta a vários comandos, basicamente é pergunta e resposta.

#### Request -> Pergunta
#### Response <- Responde

## como funciona o http?

o http funciona no modelo cliente-servidor, onde o cliente (geralmente um navegador) faz uma requisição http para um servidor, que então responde com os dados solicitados.

## estrutura de uma requisição http

uma requisição http consiste em:

- linha de requisição: indica o método http, a url e a versão do protocolo.
    ```bash
    get /index.html http/1.1
    ```
- cabeçalhos: fornecem informações adicionais sobre a requisição.
    ```makefile
    host: www.exemplo.com
    user-agent: mozilla/5.0
    ```
- corpo: contém dados enviados com a requisição (usado principalmente em métodos post).


## Métodos HTTP Comuns

- **GET**: Solicita a representação de um recurso específico.
- **POST**: Envia dados ao servidor para criar/atualizar um recurso.
- **PUT**: Atualiza um recurso existente.
- **DELETE**: Remove um recurso específico.
- **HEAD**: Igual ao GET, mas sem o corpo de resposta.

## Métodos HTTP Adicionais

- **PATCH**: Aplica modificações parciais a um recurso.
- **OPTIONS**: Descreve as opções de comunicação para o recurso alvo.

## estrutura de uma resposta http

uma resposta http consiste em:

- linha de status: indica a versão do protocolo, um código de status, e uma mensagem.
    ```plaintext
    http/1.1 200 ok
    ```
- cabeçalhos: fornecem informações adicionais sobre a resposta.
    ```yaml
    content-type: text/html
    content-length: 1234
    ```
- corpo: contém os dados solicitados pelo cliente (por exemplo, html, json).

## códigos de status http

- **1xx (informativo)**: a solicitação foi recebida e o processo continua.

- **2xx (sucesso)**: a solicitação foi recebida com sucesso.
  - 200 ok: a requisição foi bem-sucedida.


- **3xx (redirecionamento)**: é necessário tomar mais ações para completar a solicitação.
    - 301 moved permanently: o recurso solicitado foi movido permanentemente.

- **4xx (erro do cliente)**: a solicitação contém erros.
    - 404 not found: o recurso solicitado não foi encontrado.

- **5xx (erro do servidor)**: o servidor falhou ao completar a solicitação.
    - 500 internal server error: erro genérico do servidor.

## Cookies

### O que são Cookies?

Cookies são pequenos arquivos de dados que são armazenados no navegador do usuário. Eles são utilizados para guardar informações sobre a interação do usuário com um site, permitindo que o site "lembre" dessas informações em visitas futuras.

### Tipos de Cookies

- **Cookies de Sessão**: Armazenados temporariamente no navegador e são apagados quando o navegador é fechado.
- **Cookies Persistentes**: Permanecem no dispositivo do usuário por um período especificado, mesmo após o navegador ser fechado.

### Uso dos Cookies

- **Autenticação**: Armazenam informações de login para que o usuário não precise se autenticar novamente.
- **Preferências do Usuário**: Guardam preferências, como tema ou idioma.
- **Rastreamento**: Monitoram o comportamento do usuário para fins de análise e marketing.

#### Exemplo de Cabeçalho de Resposta com Cookie

```http
Set-Cookie: nome=valor; Expires=Wed, 21 Oct 2021 07:28:00 GMT; Path=/; Secure; HttpOnly
```

## conclusão

http é a base da comunicação na web, permitindo a transferência de documentos de hipertexto e a interação entre clientes e servidores. compreender seu funcionamento é essencial para o desenvolvimento web eficiente e seguro.
