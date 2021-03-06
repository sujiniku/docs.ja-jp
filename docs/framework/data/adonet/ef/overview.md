---
title: Entity Framework の概要
ms.date: 03/30/2017
ms.assetid: a2166b3d-d8ba-4a0a-8552-6ba1e3eaaee0
ms.openlocfilehash: 8b07fb9b80d5d0d13967c807198194b3a2228202
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32759895"
---
# <a name="entity-framework-overview"></a>Entity Framework の概要
[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] は、データ指向のソフトウェア アプリケーション開発をサポートする ADO.NET のテクノロジ セットです。 データ指向のアプリケーションの設計者と開発者はこれまで、2 つの大きく異なる目的を達成するために苦労してきました。 解決すべきビジネス上の問題のエンティティ、リレーションシップ、およびロジックをモデル化する一方で、データの格納と取得に使用するデータ エンジンに取り組む必要もあるからです。 データは複数のストレージ システムにまたがる場合があり、それぞれに独自のプロトコルが存在します。単一のストレージ システムを使用するアプリケーションであっても、ストレージ システムの要件と効率的で保守しやすいアプリケーション コードの記述要件のバランスを取る必要があります。  
  
 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] を使用することで、開発者は、顧客や顧客の住所など、ドメイン固有のオブジェクトおよびプロパティの形式でデータを扱うことができます。そのデータが格納されている、基になるデータベース テーブルや列を意識する必要はありません。 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] を使用すると、開発者はデータを操作するときに高い抽象化レベルで作業ができ、従来のアプリケーションよりコードの少ないデータ指向アプリケーションの作成と保守が可能になります。 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]のコンポーネントである、 [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)]、[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]アプリケーションを任意のコンピューターでも実行できます、[!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)]バージョン 3.5 SP1 以降がインストールされます。  
  
 このトピックの以降のセクションでは、[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] の詳細について説明します。  
  
-   [モデルの活用](#LifeToModels)  
  
-   [データへのオブジェクトのマッピング](#MappingObjectsToData)  
  
-   [アクセスして、エンティティ データの変更](#AccessingData)  
  
-   [データ プロバイダー](#DataProviders)  
  
-   [Entity Data Model ツール](#Tools)  
  
-   [さらに学習します。](#LearnMore)  
  
<a name="LifeToModels"></a>   
## <a name="giving-life-to-models"></a>モデルの活用  
 アプリケーションやサービスを構築するとき、従来からの一般的な設計アプローチは、アプリケーションまたはサービスをドメイン モデル、論理モデル、および物理モデルの 3 つの部分に分割する方法です。 ドメイン モデルでは、モデル化の対象となるシステムに存在するエンティティとリレーションシップを定義します。 リレーショナル データベースの論理モデルでは、外部キー制約を用いながらエンティティおよびリレーションシップをテーブルとして正規化します。 物理モデルでは、パーティション分割やインデックス化などのストレージ情報を指定することで、特定のデータ エンジンの機能に対応します。  
  
 物理モデルは、パフォーマンスを向上させるためにデータベース管理者が調整しますが、アプリケーション コードを記述するプログラマは、主に SQL クエリを記述したりストアド プロシージャを呼び出したりすることによって論理モデルを扱うことに専念します。 ドメイン モデルは通常、アプリケーションの要件を収集して伝達するためのツールとして使用されます。プロジェクトの初期段階でのみ表示および検討され、その後ほとんど使用されないのが一般的です。 概念モデルの作成を省略し、実際にリレーショナル データベースのテーブル、列、およびキーを指定することから開始する開発チームも多く存在します。  
  
 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]により開発者は、ドメイン モデルのクエリのエンティティとリレーションシップをモデルにライフ (と呼ばれる、*概念*中のモデル、 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]) に依存しながら、[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]ものを変換するにはデータ ソース固有のコマンドを操作します。 これにより、特定のデータ ソースへの依存関係をアプリケーションにハードコーディングしなくても済みます。  
  
 Code First を使用すると、概念モデルはコードのストレージ モデルにマッピングされます。 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] では、オブジェクトの種類と定義する追加の構成に基づいて概念モデルを推論できます。 マッピング メタデータは、ドメインの種類を定義した方法とコードで指定する追加の構成情報の組み合わせに基づいて実行時に生成されます。 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] は、メタデータに基づいて必要に応じてデータベースを生成します。 詳細については、次を参照してください。[マッピングの概念モデルの作成と](http://go.microsoft.com/fwlink/?LinkID=235382)です。  
  
 Entity Data Model ツールでの作業時には、概念モデル、ストレージ モデル、およびこの 2 者間のマッピングは、XML ベースのスキーマで表され、名前の拡張子が同じファイルで定義されます。  
  
-   概念モデルは概念スキーマ定義言語 (CSDL) で定義されます。 CSDL は、[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]の実装、 [Entity Data Model](../../../../../docs/framework/data/adonet/entity-data-model.md)です。 ファイル拡張子は .csdl です。  
  
-   ストア スキーマ定義言語ファイル (SSDL) はストレージ モデル (論理モデルとも呼ばれる) を定義します。 ファイル拡張子は .ssdl です。  
  
-   マッピング仕様言語ファイル (MSL) はストレージ モデルと概念モデルの間のマッピングを定義します。 ファイル拡張子は .msl です。  
  
 ストレージ モデルとマッピングは、概念モデル、データ クラス、またはアプリケーション コードを変更することなく、必要に応じて変更できます。 ストレージ モデルはプロバイダー固有なので、データ ソースの違いを意識することなく一貫した概念モデルを扱うことができます。  
  
 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]使用方法、これらのモデルおよびマッピングを作成するファイルの読み取り、更新、およびデータ ソースの同等の操作を概念モデルのエンティティとリレーションシップに対する操作を削除します。 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]でも、データ ソース内のストアド プロシージャを概念モデルのエンティティのマッピングをサポートしています。 詳細については、次を参照してください。 [CSDL、SSDL、MSL 仕様](../../../../../docs/framework/data/adonet/ef/language-reference/csdl-ssdl-and-msl-specifications.md)です。  
  
<a name="MappingObjectsToData"></a>   
## <a name="mapping-objects-to-data"></a>データへのオブジェクトのマッピング  
 オブジェクト指向プログラミングには、データ ストレージ システムと対話するという難題があります。 クラスの編成はリレーショナル データベース テーブルの編成に似ている場合がありますが、完全に一致するわけではありません。 正規化された複数のテーブルと単一のクラスが対応する場合も多く、クラス間のリレーションシップとテーブル間のリレーションシップとで表現方法が異なる場合もあります。 たとえば、販売注文の顧客を表すために、`Order` クラスは `Customer` クラスのインスタンスへの参照が含まれているプロパティを使用する一方で、データベースの `Order` テーブル行には `Customer` テーブルの主キー値に対応する値がある外部キー列 (または列セット) が含まれている場合があります。 `Customer` クラスには `Orders` クラスのインスタンスのコレクションが含まれている `Order` という名前のプロパティがありますが、データベースの `Customer` テーブルに同等の列がない場合などです。 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] は、この方法でリレーションシップを表すか、データベースで表されるリレーションシップに似せるかの柔軟性を開発者に与えます。  
  
 既存のソリューションでは、"インピーダンスのミスマッチ" とよく呼ばれるこの差異を、オブジェクト指向のクラスやプロパティをリレーショナル テーブルやリレーショナル列にマップするだけで埋めようとしてきました。 この従来の方法ではなく、[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]リレーショナル テーブル、列、および論理モデルの外部キー制約を概念モデルのエンティティとリレーションシップにマップします。 これにより、さらに柔軟にオブジェクトを定義して論理モデルを最適化することが可能になります。 [!INCLUDE[adonet_edm](../../../../../includes/adonet-edm-md.md)] ツールでは、概念モデルに基づく拡張可能なデータ クラスが生成されます。 このクラスは、開発者が追加するメンバーで拡張できる部分クラスです。 既定では、特定の概念モデルに対して生成されるクラスは、エンティティをオブジェクトとして具体化したり変更を追跡したり保存したりするサービスを提供する基本クラスから派生します。 開発者はこのようなクラスを使用して、エンティティとリレーションシップを、アソシエーションによって関連付けられたオブジェクトとして操作できます。 また、開発者は、概念モデルに生成されるクラスをカスタマイズすることもできます。 詳細については、次を参照してください。[オブジェクトの操作](../../../../../docs/framework/data/adonet/ef/working-with-objects.md)です。  
  
<a name="AccessingData"></a>   
## <a name="accessing-and-changing-entity-data"></a>エンティティ データに対するアクセスと変更  
 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] は単なるオブジェクト リレーショナル マッピング ソリューションではなく、基本的には、概念モデルのエンティティとリレーションシップとして表されるデータにアプリケーションからアクセスして変更できるようにするためのものです。 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] はモデル ファイルとマッピング ファイルの情報を使用して、概念モデルで表されるエンティティ型に対するオブジェクト クエリをデータ ソース固有のクエリに変換します。 クエリの結果がオブジェクトに具体化する、[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]を管理します。 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]を概念モデルを照会し、オブジェクトを返す、次の方法を提供します。  
  
-   [!INCLUDE[linq_entities](../../../../../includes/linq-entities-md.md)]。 概念モデルで定義されているエンティティ型を照会するためには、統合言語クエリ (LINQ) のサポートを提供します。 詳細については、次を参照してください。 [LINQ to Entities](../../../../../docs/framework/data/adonet/ef/language-reference/linq-to-entities.md)です。  
  
-   [!INCLUDE[esql](../../../../../includes/esql-md.md)]。 概念モデルのエンティティと直接連動して、サポートする SQL のストレージに依存しない言語[!INCLUDE[adonet_edm](../../../../../includes/adonet-edm-md.md)]概念です。 [!INCLUDE[esql](../../../../../includes/esql-md.md)] オブジェクトのクエリと EntityClient プロバイダーを使用して実行されるクエリの両方に使用されます。 詳細については、次を参照してください。 [Entity SQL の概要](../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)です。  
  
 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] には、EntityClient データ プロバイダーが含まれています。 このプロバイダーは接続を管理し、エンティティ クエリをデータ ソース固有のクエリに変換し、[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] がエンティティ データをオブジェクトに具体化するために使用するデータ リーダーを返します。 オブジェクトの具体化する必要がない場合、EntityClient プロバイダーこともできます、標準のような[!INCLUDE[vstecado](../../../../../includes/vstecado-md.md)]データ プロバイダーを実行するアプリケーションを有効にして[!INCLUDE[esql](../../../../../includes/esql-md.md)]クエリを実行し、返される読み取り専用データ リーダーを使用します。 詳細については、次を参照してください。 [Entity Framework の EntityClient プロバイダー](../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md)です。  
  
 次の図は、データにアクセスするための [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] アーキテクチャを示しています。  
  
 ![Entity Framework のアーキテクチャ ダイアグラム](../../../../../docs/framework/data/adonet/ef/media/wd-efarchdiagram.gif "wd_EFArchDiagram")  
  
 [!INCLUDE[adonet_edm](../../../../../includes/adonet-edm-md.md)] ツールは、概念モデルのエンティティ コンテナーを表す `System.Data.Objects.ObjectContext` または `System.Data.Entity.DbContext` から派生したクラスを生成できます。 このオブジェクト コンテキストは、変更の追跡や ID、同時実行、およびリレーションシップの管理などの機能を提供します。 また、このクラスは、データ ソースに挿入、更新、および削除を書き込む `SaveChanges` メソッドも公開します。 このような変更は、クエリと同様に、システムによって自動的に生成されるコマンドで行うことも、特定のストアド プロシージャを使用するように指定することもできます。  
  
<a name="DataProviders"></a>   
## <a name="data-providers"></a>データ プロバイダー  
 `EntityClient` プロバイダーは、概念エンティティおよびリレーションシップに従ってデータにアクセスし、[!INCLUDE[vstecado](../../../../../includes/vstecado-md.md)] プロバイダー モデルを拡張します。 [!INCLUDE[esql](../../../../../includes/esql-md.md)] を使用するクエリを実行します。 [!INCLUDE[esql](../../../../../includes/esql-md.md)] は、`EntityClient` がデータベースと通信する基盤となるクエリ言語を提供します。 詳細については、次を参照してください。 [Entity Framework の EntityClient プロバイダー](../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md)です。  
  
 更新された [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] の SqlClient Data Provider は、正規コマンド ツリーをサポートしています。 詳細については、次を参照してください。 [Entity Framework 用 SqlClient](../../../../../docs/framework/data/adonet/ef/sqlclient-for-the-entity-framework.md)です。  
  
<a name="Tools"></a>   
## <a name="entity-data-model-tools"></a>Entity Data Model ツール  
 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] ランタイムに加えて、[!INCLUDE[vs_current_long](../../../../../includes/vs-current-long-md.md)] にはマッピング ツールとモデリング ツールが含まれています。 詳細については、次を参照してください。[モデリングとマッピング](../../../../../docs/framework/data/adonet/ef/modeling-and-mapping.md)です。  
  
<a name="LearnMore"></a>   
## <a name="learning-more"></a>詳細情報  
 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] の詳細については、次のトピックを参照してください。  
  
 [はじめに](../../../../../docs/framework/data/adonet/ef/getting-started.md)  
 取得する方法に関する情報を提供し、使用して迅速に実行されている、[クイック スタート](http://msdn.microsoft.com/library/0bc534be-789f-4819-b9f6-76e51d961675)、単純なを作成する方法を示す[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]アプリケーションです。  
  
 [Entity Framework の用語](../../../../../docs/framework/data/adonet/ef/terminology.md)  
 Entity Data Model と [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] で使用されている用語や [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] のドキュメントで使用されている用語を多数定義しています。  
  
 [Entity Framework のリソース](../../../../../docs/framework/data/adonet/ef/resources.md)  
 概念に関するトピックへのリンクや [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] アプリケーションの構築に関する外部トピックおよびリソースへのリンクを示します。  
  
## <a name="see-also"></a>関連項目  
 [ADO.NET Entity Framework](../../../../../docs/framework/data/adonet/ef/index.md)
