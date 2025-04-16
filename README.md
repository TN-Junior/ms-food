
# ms-food

Projeto desenvolvido com arquitetura de microserviços utilizando **Spring Boot**, com foco em modularização, escalabilidade e boas práticas de separação de responsabilidades. Cada microserviço representa uma funcionalidade isolada do sistema.

---

## Estrutura de Módulos

```
ms-food/
├── gateway/         # API Gateway (Spring Cloud Gateway)
├── pagamentos/      # Microserviço de pagamentos
├── pedidos/         # Microserviço de pedidos
├── server/          # Serviço de descoberta (Eureka Server)
└── .idea/, .mvn/, etc.  # Arquivos de configuração e metadados
```

---

## Tecnologias Utilizadas

- Java 17
- Spring Boot
- Spring Cloud Gateway
- Spring Data JPA
- Spring Web
- Eureka Server (Service Discovery)
- Flyway (migração de banco de dados)
- Maven

---

## Descrição dos Microserviços

### 1. Gateway
- Atua como API Gateway, redirecionando requisições para os serviços internos.
- Utiliza Spring Cloud Gateway.
- Arquivo principal: `GatewayApplication.java`

### 2. Pagamentos
- Responsável pelo gerenciamento de pagamentos de pedidos.
- Camadas: Controller, Service, Repository, Model, DTO.
- Usa JPA e Flyway para persistência e versionamento de banco.

### 3. Pedidos
- Gerencia os pedidos realizados.
- Camadas: Controller, Service, Repository, Model, DTO.
- Também utiliza Flyway para versionamento de banco.

### 4. Server
- Serviço de descoberta com Eureka Server.
- Permite que os outros serviços se registrem e se comuniquem dinamicamente.

---

## Como Rodar Localmente

1. Clone o projeto:
```bash
git clone https://github.com/TN-Junior/ms-food.git
cd ms-food
```

2. Suba o Eureka Server:
```bash
cd server
./mvnw spring-boot:run
```

3. Em seguida, execute os demais microserviços (`gateway`, `pagamentos`, `pedidos`) em terminais separados.

---

## Próximos Passos

- Implementar autenticação com Spring Security
- Incluir testes de integração
- Dockerizar os serviços
- Criar documentação com Swagger/OpenAPI

---

## Autor

Desenvolvido por Tary Junior – contribuindo com sistemas distribuídos e arquitetura em microserviços.

---

© 2025 - Projeto ms-food
