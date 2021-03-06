

# [Microsserviços .NET: arquitetura para aplicativos .NET em contêineres](index.md)


## [Introdução aos contêineres e ao Docker](container-docker-introduction/index.md)


### [O que é o Docker?](container-docker-introduction/docker-defined.md)


### [Terminologia do Docker](container-docker-introduction/docker-terminology.md)


### [Registros, imagens e contêineres do Docker](container-docker-introduction/docker-containers-images-registries.md)


## [Escolhendo entre o .NET Core e o .NET Framework para contêineres do Docker](net-core-net-framework-containers/index.md)


### [Diretrizes gerais](net-core-net-framework-containers/general-guidance.md)


### [Quando escolher o .NET Core para os contêineres do Docker](net-core-net-framework-containers/net-core-container-scenarios.md)


### [Quando escolher o .NET Framework para os contêineres do Docker](net-core-net-framework-containers/net-framework-container-scenarios.md)


### [Tabela de decisões: estruturas .NET a serem usadas para o Docker](net-core-net-framework-containers/container-framework-choice-factors.md)


### [Para qual sistema operacional direcionar com os contêineres do .NET](net-core-net-framework-containers/net-container-os-targets.md)


### [Imagens oficiais do .NET Docker](net-core-net-framework-containers/official-net-docker-images.md)


## [Arquitetando aplicativos baseados em contêineres e em microsserviços](architect-microservice-container-applications/index.md)


### [Implantando aplicativos monolíticos em contêineres](architect-microservice-container-applications/containerize-monolithic-applications.md)


### [Estado e dados em aplicativos do Docker](architect-microservice-container-applications/docker-application-state-data.md)


### [Arquitetura orientada a serviço ](architect-microservice-container-applications/service-oriented-architecture.md)


### [Arquitetura de microsserviços](architect-microservice-container-applications/microservices-architecture.md)


### [Soberania de dados por microsserviço](architect-microservice-container-applications/data-sovereignty-per-microservice.md)


### [Arquitetura lógica versus arquitetura física](architect-microservice-container-applications/logical-versus-physical-architecture.md)


### [Desafios e soluções de gerenciamento de dados distribuídos](architect-microservice-container-applications/distributed-data-management.md)


### [Identificando os limites de modelo de domínio de cada microsserviço](architect-microservice-container-applications/identify-microservice-domain-model-boundaries.md)


### [Comunicação entre microsserviços](architect-microservice-container-applications/communication-between-microservices.md)


### [Comunicação assíncrona baseada em mensagens](architect-microservice-container-applications/asynchronous-message-based-communication.md)


### [Criando, evoluindo e fazendo o controle de versão de APIs e de contratos de microsserviços](architect-microservice-container-applications/maintain-microservice-apis.md)


### [Capacidade de endereçamento de microsserviços e o registro do serviço](architect-microservice-container-applications/microservices-addressability-service-registry.md)


### [Criando interface do usuário de composição baseada em microsserviços, incluindo forma e layout visuais da interface do usuário gerados por vários microsserviços](architect-microservice-container-applications/microservice-based-composite-ui-shape-layout.md)


### [Resiliência e a alta disponibilidade em microsserviços](architect-microservice-container-applications/resilient-high-availability-microservices.md)


### [Orquestrando microsserviços e aplicativos de vários contêineres para alta escalabilidade e disponibilidade](architect-microservice-container-applications/scalable-available-multi-container-microservice-applications.md)


### [Usando o Azure Service Fabric](architect-microservice-container-applications/using-azure-service-fabric.md)


## [Processo de desenvolvimento de aplicativos baseados no Docker](docker-application-development-process/index.md)


### [Fluxo de trabalho de desenvolvimento de aplicativos do Docker](docker-application-development-process/docker-app-development-workflow.md)


## [Implantando aplicativos Web .NET Core baseados em contêiner único em hosts do Linux ou do Windows Nano Server](net-core-single-containers-linux-windows-server-hosts/index.md)


## [Migrando aplicativos monolíticos herdados do .NET Framework para contêineres do Windows](containerize-net-framework-applications/index.md)


## [Projetando e desenvolvendo aplicativos .NET baseados em vários contêineres e em microsserviços](multi-container-microservice-net-applications/index.md)


### [Projetando um aplicativo orientado a microsserviço](multi-container-microservice-net-applications/microservice-application-design.md)


### [Criando um microsserviço CRUD simples controlado por dados](multi-container-microservice-net-applications/data-driven-crud-microservice.md)


### [Definindo o aplicativo de vários contêineres com o docker-compose.yml](multi-container-microservice-net-applications/multi-container-applications-docker-compose.md)


### [Usando um servidor de banco de dados em execução como contêiner](multi-container-microservice-net-applications/database-server-container.md)


### [Implementando comunicação baseada em evento entre microsserviços (eventos de integração)](multi-container-microservice-net-applications/integration-event-based-microservice-communications.md)


### [Implementando um barramento de eventos com o RabbitMQ para o ambiente de desenvolvimento ou de teste](multi-container-microservice-net-applications/rabbitmq-event-bus-development-test-environment.md)


### [Assinando eventos](multi-container-microservice-net-applications/subscribe-events.md)


### [Testando os aplicativos Web e os serviços do ASP.NET Core](multi-container-microservice-net-applications/test-aspnet-core-services-web-apps.md)


## [Lidando com a complexidade dos negócios em um microsserviço com padrões DDD e CQRS](microservice-ddd-cqrs-patterns/index.md)


### [Aplicando padrões CQRS e DDD simplificados em um microsserviço](microservice-ddd-cqrs-patterns/apply-simplified-microservice-cqrs-ddd-patterns.md)


### [Aplicando abordagens CQRS e CQS em um microsserviço DDD em eShopOnContainers](microservice-ddd-cqrs-patterns/eshoponcontainers-cqrs-ddd-microservice.md)


### [Implementando leituras/consultas em um microsserviço CQRS](microservice-ddd-cqrs-patterns/cqrs-microservice-reads.md)


### [Projetando um microsserviço orientado a DDD](microservice-ddd-cqrs-patterns/ddd-oriented-microservice.md)


### [Projetando um modelo de domínio de microsserviço](microservice-ddd-cqrs-patterns/microservice-domain-model.md)


### [Implementando um modelo de domínio de microsserviço com o .NET Core](microservice-ddd-cqrs-patterns/net-core-microservice-domain-model.md)


### [Seedwork (classes e interfaces base reutilizáveis para seu modelo de domínio)](microservice-ddd-cqrs-patterns/seedwork-domain-model-base-classes-interfaces.md)


### [Implementando objetos de valor](microservice-ddd-cqrs-patterns/implement-value-objects.md)


### [Usando classes Enumeration em vez de tipos enum](microservice-ddd-cqrs-patterns/enumeration-classes-over-enum-types.md)


### [Projetando validações na camada de modelo de domínio](microservice-ddd-cqrs-patterns/domain-model-layer-validations.md)


### [Validação do lado do cliente (validação nas camadas de apresentação)](microservice-ddd-cqrs-patterns/client-side-validation.md)


### [Eventos de domínio: design e implementação](microservice-ddd-cqrs-patterns/domain-events-design-implementation.md)


### [Projetando a camada de persistência da infraestrutura](microservice-ddd-cqrs-patterns/infrastructure-persistence-layer-design.md)


### [Implementando a camada de persistência de infraestrutura com o Entity Framework Core](microservice-ddd-cqrs-patterns/infrastructure-persistence-layer-implemenation-entity-framework-core.md)


### [Usando bancos de dados NoSQL como infraestrutura de persistência](microservice-ddd-cqrs-patterns/nosql-database-persistence-infrastructure.md)


### [Projetando a camada de aplicativos de microsserviço e a API Web](microservice-ddd-cqrs-patterns/microservice-application-layer-web-api-design.md)


### [Implementando a camada de aplicativos de microsserviço usando a API Web](microservice-ddd-cqrs-patterns/microservice-application-layer-implementation-web-api.md)


## [Implementando aplicativos resilientes](implement-resilient-applications/index.md)


### [Tratando de falha parcial](implement-resilient-applications/handle-partial-failure.md)


### [Estratégias para tratar de falhas parciais](implement-resilient-applications/partial-failure-strategies.md)


### [Implementação de novas tentativas com retirada exponencial](implement-resilient-applications/implement-retries-exponential-backoff.md)


### [Implementando conexões SQL do Entity Framework Core](implement-resilient-applications/implement-resilient-entity-framework-core-sql-connections.md)


### [Implementando de novas tentativas de chamadas HTTP personalizadas com retirada exponencial](implement-resilient-applications/implement-custom-http-call-retries-exponential-backoff.md)


### [Implementando novas tentativas de chamadas HTTP com retirada exponencial com a Polly](implement-resilient-applications/implement-http-call-retries-exponential-backoff-polly.md)


### [Implementando o padrão de disjuntor](implement-resilient-applications/implement-circuit-breaker-pattern.md)


### [Monitoramento de integridade](implement-resilient-applications/monitor-app-health.md)


## [Protegendo aplicativos Web e microsserviços .NET](secure-net-microservices-web-applications/index.md)


### [Sobre a autorização em aplicativos Web e em microsserviços .NET](secure-net-microservices-web-applications/authorization-net-microservices-web-applications.md)


### [Armazenando segredos de aplicativo com segurança durante o desenvolvimento](secure-net-microservices-web-applications/developer-app-secrets-storage.md)


### [Usando o Azure Key Vault para proteger segredos no momento da produção](secure-net-microservices-web-applications/azure-key-vault-protects-secrets.md)


## [Principais aspectos a serem lembrados](key-takeaways.md)
