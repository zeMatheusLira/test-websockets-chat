# WebSocket Chat Application

## Descrição

Este é um projeto de aplicação de chat em tempo real utilizando **WebSockets** com o protocolo **STOMP**. O backend foi desenvolvido com **Spring Boot** e o frontend utiliza **HTML**, **CSS** e **JavaScript**. Usuários podem se conectar, enviar mensagens para um tópico público e ver outros usuários entrando e saindo do chat.

## Funcionalidades

- Conexão em tempo real usando WebSockets.
- Suporte a múltiplos usuários.
- Envio de mensagens em um canal público.
- Notificações de entrada e saída de usuários.
- Interface simples e responsiva.

## Tecnologias Utilizadas

### Backend
- **Java 17**
- **Spring Boot** (2.7+)
- **Spring WebSocket** com STOMP
- **Lombok** para simplificação do código
- **Maven** como gerenciador de dependências

### Frontend
- **HTML5**
- **CSS3**
- **JavaScript** 
- **SockJS** para fallback de WebSockets
- **STOMP.js** para a comunicação sobre WebSockets

## Requisitos

- **JDK 17** ou superior
- **Maven** para gerenciar dependências e build do projeto

## Como Executar o Projeto

### Backend (Spring Boot)

1. Clone o repositório:
    ```bash
    git clone https://github.com/zeMatheusLira/websocket-chat-app.git
    ```
   
2. Acesse o diretório do projeto:
    ```bash
    cd test-websockets-chat
    ```

3. Compile o projeto com Maven:
    ```bash
    mvn clean install
    ```

4. Execute a aplicação Spring Boot:
    ```bash
    mvn spring-boot:run
    ```

5. O servidor será iniciado em `http://localhost:8080`.

### Frontend (HTML/CSS/JavaScript)

1. Após o backend estar rodando, abra o arquivo `index.html` localizado no diretório `src/main/resources/static/` em um navegador.

2. Insira um nome de usuário para se conectar ao chat.

3. Comece a enviar mensagens e interagir com outros usuários em tempo real.

## Estrutura do Projeto
```
test-websockets-chat/
├── src/
│   ├── main/
│   │   ├── java/
│   │   │   └── chat.testwebsockethat/            # Pacote principal do projeto
│   │   │       ├── chat/
│   │   │       │   ├── ChatController.java       # Controlador de WebSocket
│   │   │       │   ├── ChatMessage.java          # Modelo da mensagem de chat
│   │   │       │   ├── MessageType.java          # Enum para os tipos de mensagem (JOIN, CHAT, LEAVE)
│   │   │       ├── configs/
│   │   │       │   ├── WebSocketConfig.java         # Configuração do WebSocket
│   │   │       │   ├── WebSocketEventListener.java  # Listener de eventos WebSocket
│   └── resources/
│       ├── static/                              # Arquivos estáticos usados pelo frontend (HTML, CSS, JS)
│       │   ├── index.html                       # Interface principal do chat
│       │   ├── css/                             # Pasta de estilos CSS
│       │   │   └── main.css                     # Estilos do frontend
│       │   ├── js/                              # Pasta de scripts JavaScript
│       │   │   └── main.js                      # Lógica de frontend do WebSocket
├── pom.xml                                      # Arquivo de dependências Maven
├── README.md                                    # Documentação do projeto
```



### Arquivos Principais:

- **WebSocketConfig.java**: Configura o WebSocket e define os endpoints STOMP.
- **ChatController.java**: Controla as mensagens enviadas pelos usuários e gerencia a adição de novos usuários ao chat.
- **WebSocketEventListener.java**: Escuta eventos de desconexão e informa quando um usuário sai do chat.
- **index.html**: Frontend da aplicação, onde o usuário pode interagir com o chat.
- **main.js**: Contém a lógica de conexão WebSocket no lado do cliente, envio e recebimento de mensagens.

## Como Funciona

1. Quando o usuário acessa o **index.html**, ele insere um nome de usuário e se conecta ao WebSocket.
2. A aplicação envia e recebe mensagens usando o protocolo **STOMP**.
3. O backend gerencia a conexão e distribui as mensagens para todos os usuários conectados.
4. Sempre que um usuário entra ou sai do chat, uma mensagem de notificação é enviada para todos no canal público.


## Melhorias Futuras

- Adicionar suporte para salas de chat privadas.
- Implementar autenticação e autorização.
- Adicionar histórico de mensagens usando um banco de dados.
- Melhorar a interface do usuário com mais recursos interativos.


## Licença

Este projeto é licenciado sob os termos da licença MIT. Consulte o arquivo `LICENSE` para mais detalhes.
