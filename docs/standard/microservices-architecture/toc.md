

# [.NET マイクロサービス: コンテナー化された .NET アプリケーションのアーキテクチャ](index.md)


## [コンテナーと Docker の概要](container-docker-introduction/index.md)


### [Docker について](container-docker-introduction/docker-defined.md)


### [Docker に関する用語](container-docker-introduction/docker-terminology.md)


### [Docker のコンテナー、イメージ、およびレジストリ](container-docker-introduction/docker-containers-images-registries.md)


## [Docker コンテナー用 .NET Core と .NET Framework の選択](net-core-net-framework-containers/index.md)


### [一般的なガイダンス](net-core-net-framework-containers/general-guidance.md)


### [Docker コンテナー用 .Net Core を選択するタイミング](net-core-net-framework-containers/net-core-container-scenarios.md)


### [Docker コンテナー用 .NET Framework を選択するタイミング](net-core-net-framework-containers/net-framework-container-scenarios.md)


### [意思決定テーブル: Docker に使用する .NET Frameworks](net-core-net-framework-containers/container-framework-choice-factors.md)


### [.NET コンテナーで対象とする OS](net-core-net-framework-containers/net-container-os-targets.md)


### [公式の .NET Docker イメージ](net-core-net-framework-containers/official-net-docker-images.md)


## [コンテナーとマイクロサービス ベースのアプリケーションの設計](architect-microservice-container-applications/index.md)


### [モノリシック アプリケーションのコンテナー化](architect-microservice-container-applications/containerize-monolithic-applications.md)


### [Docker アプリケーションの状態とデータ](architect-microservice-container-applications/docker-application-state-data.md)


### [サービス指向アーキテクチャ](architect-microservice-container-applications/service-oriented-architecture.md)


### [マイクロサービス アーキテクチャ](architect-microservice-container-applications/microservices-architecture.md)


### [マイクロサービス単位のデータ管理](architect-microservice-container-applications/data-sovereignty-per-microservice.md)


### [論理アーキテクチャと物理アーキテクチャ](architect-microservice-container-applications/logical-versus-physical-architecture.md)


### [分散データ管理に関する課題とソリューション](architect-microservice-container-applications/distributed-data-management.md)


### [マイクロサービスごとにドメイン モデルの境界を識別する](architect-microservice-container-applications/identify-microservice-domain-model-boundaries.md)


### [マイクロサービス間の通信](architect-microservice-container-applications/communication-between-microservices.md)


### [非同期メッセージ ベースの通信](architect-microservice-container-applications/asynchronous-message-based-communication.md)


### [マイクロサービス API とコントラクトの作成、進化、バージョン管理](architect-microservice-container-applications/maintain-microservice-apis.md)


### [マイクロサービスのアドレス指定能力およびサービス レジストリ](architect-microservice-container-applications/microservices-addressability-service-registry.md)


### [複数のマイクロサービスによって生成されるレイアウトなど、マイクロサービスを基にしている複合 UI を作成する](architect-microservice-container-applications/microservice-based-composite-ui-shape-layout.md)


### [マイクロサービスの回復性と高可用性](architect-microservice-container-applications/resilient-high-availability-microservices.md)


### [高いスケーラビリティと可用性のためにマイクロサービスと複数のコンテナー アプリケーションを調整する](architect-microservice-container-applications/scalable-available-multi-container-microservice-applications.md)


### [Azure Service Fabric の使用](architect-microservice-container-applications/using-azure-service-fabric.md)


## [Docker ベースのアプリケーションの開発プロセス](docker-application-development-process/index.md)


### [Docker アプリの開発ワークフロー](docker-application-development-process/docker-app-development-workflow.md)


## [Linux または Windows Nano Server ホスト上で 1 つのコンテナー ベースの NET Core Web アプリケーションを展開する](net-core-single-containers-linux-windows-server-hosts/index.md)


## [レガシ モノリシック NET Framework アプリケーションを Windows コンテナーに移行する](containerize-net-framework-applications/index.md)


## [複数のコンテナーとマイクロサービス ベースの NET アプリケーションのデザインと開発](multi-container-microservice-net-applications/index.md)


### [マイクロサービス指向アプリケーションの設計](multi-container-microservice-net-applications/microservice-application-design.md)


### [単純なデータ ドリブン CRUD マイクロサービスの作成](multi-container-microservice-net-applications/data-driven-crud-microservice.md)


### [docker-compose.yml で複数のコンテナー アプリケーションを定義する](multi-container-microservice-net-applications/multi-container-applications-docker-compose.md)


### [コンテナーとして実行するデータベース サーバーの使用](multi-container-microservice-net-applications/database-server-container.md)


### [マイクロサービス (統合イベント) 間でイベント ベースの通信を実装する](multi-container-microservice-net-applications/integration-event-based-microservice-communications.md)


### [開発環境またはテスト環境の RabbitMQ でイベント バスを実装する](multi-container-microservice-net-applications/rabbitmq-event-bus-development-test-environment.md)


### [イベントのサブスクライブ](multi-container-microservice-net-applications/subscribe-events.md)


### [ASP.NET Core サービスと Web アプリのテスト](multi-container-microservice-net-applications/test-aspnet-core-services-web-apps.md)


## [マイクロサービスで DDD と CQRS パターンを使ってビジネスの複雑さに取り組む](microservice-ddd-cqrs-patterns/index.md)


### [マイクロサービスに簡略化された CQRS と DDD パターンを適用する](microservice-ddd-cqrs-patterns/apply-simplified-microservice-cqrs-ddd-patterns.md)


### [eShopOnContainers の DDD マイクロサービスに CQRS および CQS のアプローチを適用する](microservice-ddd-cqrs-patterns/eshoponcontainers-cqrs-ddd-microservice.md)


### [CQRS マイクロサービスに読み取り/クエリを実装する](microservice-ddd-cqrs-patterns/cqrs-microservice-reads.md)


### [DDD 指向マイクロサービスの設計](microservice-ddd-cqrs-patterns/ddd-oriented-microservice.md)


### [マイクロサービス ドメイン モデルの設計](microservice-ddd-cqrs-patterns/microservice-domain-model.md)


### [.NET Core でマイクロサービス ドメイン モデルを実装する](microservice-ddd-cqrs-patterns/net-core-microservice-domain-model.md)


### [Seedwork (再利用可能な基本クラスとドメイン モデルのインターフェイス)](microservice-ddd-cqrs-patterns/seedwork-domain-model-base-classes-interfaces.md)


### [値オブジェクトの実装](microservice-ddd-cqrs-patterns/implement-value-objects.md)


### [列挙型ではなく列挙型クラスを使用する](microservice-ddd-cqrs-patterns/enumeration-classes-over-enum-types.md)


### [ドメイン モデル レイヤーでの検証の設計](microservice-ddd-cqrs-patterns/domain-model-layer-validations.md)


### [クライアント側の検証 (プレゼンテーション層での検証)](microservice-ddd-cqrs-patterns/client-side-validation.md)


### [ドメイン イベント: 設計と実装](microservice-ddd-cqrs-patterns/domain-events-design-implementation.md)


### [インフラストラクチャの永続レイヤーの設計](microservice-ddd-cqrs-patterns/infrastructure-persistence-layer-design.md)


### [Entity Framework Core でインフラストラクチャの永続レイヤーを実装する](microservice-ddd-cqrs-patterns/infrastructure-persistence-layer-implemenation-entity-framework-core.md)


### [永続インフラストラクチャとして NoSQL データベースを使用する](microservice-ddd-cqrs-patterns/nosql-database-persistence-infrastructure.md)


### [マイクロサービス アプリケーション レイヤーと Web API の設計](microservice-ddd-cqrs-patterns/microservice-application-layer-web-api-design.md)


### [Web API を使用したマイクロサービス アプリケーション レイヤーの実装](microservice-ddd-cqrs-patterns/microservice-application-layer-implementation-web-api.md)


## [回復性の高いアプリケーションの実装](implement-resilient-applications/index.md)


### [部分的なエラーの処理](implement-resilient-applications/handle-partial-failure.md)


### [部分的なエラーを処理するための戦略](implement-resilient-applications/partial-failure-strategies.md)


### [指数のバックオフを含む再試行を実装する](implement-resilient-applications/implement-retries-exponential-backoff.md)


### [回復力の高い Entity Framework Core SQL 接続の実装](implement-resilient-applications/implement-resilient-entity-framework-core-sql-connections.md)


### [指数のバックオフを含むカスタムの HTTP 呼び出しの再試行を実装する](implement-resilient-applications/implement-custom-http-call-retries-exponential-backoff.md)


### [Polly で指数のバックオフを含む HTTP 呼び出しの再試行を実装する](implement-resilient-applications/implement-http-call-retries-exponential-backoff-polly.md)


### [直流高速度遮断器パターンの実装](implement-resilient-applications/implement-circuit-breaker-pattern.md)


### [稼働状況の監視](implement-resilient-applications/monitor-app-health.md)


## [NET マイクロサービスおよび Web アプリケーションをセキュリティで保護する](secure-net-microservices-web-applications/index.md)


### [.NET マイクロサービスと Web アプリケーションでの承認について](secure-net-microservices-web-applications/authorization-net-microservices-web-applications.md)


### [開発時にアプリケーションの機密情報を安全に格納する](secure-net-microservices-web-applications/developer-app-secrets-storage.md)


### [実稼働時に機密情報を保護するために Azure Key Vault を使用する](secure-net-microservices-web-applications/azure-key-vault-protects-secrets.md)


## [重要な習得事項](key-takeaways.md)