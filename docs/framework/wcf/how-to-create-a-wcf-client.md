---
title: '方法 : Windows Communication Foundation クライアントを作成する'
ms.date: 03/30/2017
helpviewer_keywords:
- clients [WCF], running
- WCF clients [WCF], running
ms.assetid: a67884cc-1c4b-416b-8c96-5c954099f19f
ms.openlocfilehash: d2932293536f875d8986d8d49842cddc196ced0f
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
ms.locfileid: "33806274"
---
# <a name="how-to-create-a-windows-communication-foundation-client"></a>方法 : Windows Communication Foundation クライアントを作成する
これは、Windows Communication Foundation (WCF) アプリケーションを作成するために必要な 6 つのタスクのうちの 4 番目です。 タスクの 6 つのすべての概要については、次を参照してください。、[チュートリアル入門](../../../docs/framework/wcf/getting-started-tutorial.md)トピックです。  
  
 このトピックでは、WCF サービスからメタデータを取得しを使用して、サービスにアクセスできる、WCF プロキシを作成する方法について説明します。 このタスクを完了するには、Visual Studio に用意されている "サービス参照の追加" 機能を使用します。 このツールでは、サービスの MEX エンドポイントからメタデータを取得し、選択した言語 (既定では C#) でクライアント プロキシのマネージ ソース コード ファイルを生成します。 このツールでは、クライアント プロキシを作成する以外に、クライアントの構成ファイルの作成または更新も行います。この構成ファイルにより、クライアント アプリケーションはエンドポイントのいずれかにあるサービスに接続できるようになります。  
  
> [!NOTE]
>  使用することも、 [ServiceModel メタデータ ユーティリティ ツール (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)プロキシ クラスおよび Visual Studio 内でサービス参照の追加を使用する代わりに構成を生成するツールです。  
  
> [!WARNING]
>  クラス ライブラリ プロジェクトから WCF サービスを呼び出すときに[!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)]プロキシおよび関連構成ファイルを自動的に生成する、サービス参照の追加機能を使用することができます。  この構成ファイルはクラス ライブラリ プロジェクトで使用されません。 クラス ライブラリを呼び出す実行可能ファイルの app.config ファイルに、生成された構成ファイル内の設定を追加する必要があります。  
  
 クライアント アプリケーションは、生成されたプロキシ クラスを使用してサービスと通信します。 この手順で説明されて[する方法: クライアントを使用して](../../../docs/framework/wcf/how-to-use-a-wcf-client.md)です。  
  
### <a name="to-create-a-windows-communication-foundation-client"></a>Windows Communication Foundation クライアントを作成するには  
  
1.  はじめにソリューションを選択するを右クリックして新しいコンソール アプリケーション プロジェクトを作成する**追加**、**新しいプロジェクト**です。 **新しいプロジェクトの追加**ダイアログの の左側でダイアログ**Windows**  **c#** または**VB**です。 ダイアログの中央のセクションで選択**コンソール アプリケーション**です。 プロジェクトに `GettingStartedClient` という名前を付けます。  
  
2.  右クリック GettingStartedClient プロジェクトのターゲット フレームワークを .NET Framework 4.5 に設定**GettingStartedClient**ソリューション エクスプ ローラーを選択して**プロパティ**です。 ラベルの付いたボックスの一覧で**ターゲット フレームワーク**選択 **.NET Framework 4.5**です。 VB プロジェクトは少し異なり、GettingStartedClient プロジェクトのプロパティ ダイアログ ボックスのターゲット フレームワークを設定をクリックして、**コンパイル**、画面の左側にある タブでをクリックし、 **詳細設定コンパイル オプション**ダイアログ ボックスの左下隅にあるボタンをクリックします。 選択し、 **.NET Framework 4.5**というドロップダウン ボックスで**ターゲット フレームワーク**です。  
  
     ターゲット フレームワークを設定すると、ソリューションを再読み込みする Visual Studio 2011 キーを押して**OK**入力を求められたらです。  
  
3.  右クリックして System.ServiceModel への参照を GettingStartedClient プロジェクトに追加、**参照**クリックし、ソリューション エクスプ ローラーで GettingStartedClient プロジェクトの下のフォルダー**追加**参照。 **参照の追加**ダイアログの  **Framework**ダイアログ ボックスの左側にあります。 [アセンブリの検索] ボックスに「`System.ServiceModel`」と入力します。 ダイアログの中央のセクションで選択**System.ServiceModel**をクリックして、**追加**ボタンをクリックし、をクリックして、**閉じる**ボタンをクリックします。 クリックして、ソリューションを保存、**すべて保存**メイン メニューの下のボタンをクリックします。  
  
4.  次に、電卓サービスへのサービス参照を追加します。 これを実行する前に、GettingStartedHost コンソール アプリケーションを起動する必要があります。 ホストが実行されているソリューション エクスプ ローラーで GettingStartedClient プロジェクトの 参照 フォルダーを右クリックしてサービス参照の追加 ダイアログ ボックスの アドレス ボックスに次の URL でサービス参照の追加と種類を選択します HYPERLINK"。http://localhost:8000/ServiceModelSamples/Service" http://localhost:8000/ServiceModelSamples/Service  をクリックし、**移動**ボタンをクリックします。 "CalculatorService" が [サービス] ボックスに表示されたら、CalculatorService をダブルクリックして、そのサービスによって実装されているサービス コントラクトを展開して表示します。 同様をクリックして既定の名前空間のままにして、 **OK**ボタンをクリックします。  
  
     Visual Studio を使用してサービスへの参照を追加すると、ソリューション エクスプローラーで、新しい項目が GettingStartedClient プロジェクトの [サービス参照] フォルダーの下に表示されます。  使用する場合、 [ServiceModel メタデータ ユーティリティ ツール (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)ツールは、ソース コード ファイルおよび app.config ファイルが生成されます。  
  
     コマンド ライン ツールを使用することもできます。 [ServiceModel メタデータ ユーティリティ ツール (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)クライアント コードを作成する適切なスイッチです。 次の例では、サービスのコード ファイルと構成ファイルを生成しています。 最初の例では VB でプロキシを生成する方法を示し、2 番目の例では C# でプロキシを生成する方法を示しています。  
  
    ```  
    svcutil.exe /language:vb /out:generatedProxy.vb /config:app.config http://localhost:8000/ServiceModelSamples/service  
    ```  
  
    ```csharp  
    svcutil.exe /language:cs /out:generatedProxy.cs /config:app.config http://localhost:8000/ServiceModelSamples/service  
    ```  
  
 これで、クライアント アプリケーションで電卓サービスを呼び出すために使用されるプロキシが作成されました。 系列内の次のトピックに進んで:[する方法: クライアントを構成します。](../../../docs/framework/wcf/how-to-configure-a-basic-wcf-client.md)  
  
## <a name="see-also"></a>関連項目  
 [ServiceModel メタデータ ユーティリティ ツール (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)  
 [はじめに](../../../docs/framework/wcf/samples/getting-started-sample.md)  
 [自己ホスト](../../../docs/framework/wcf/samples/self-host.md)  
 [方法 : 構成ファイルを使用してサービスのメタデータを公開する](../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)  
 [方法 : Svcutil.exe を使用してメタデータ ドキュメントをダウンロードする](../../../docs/framework/wcf/feature-details/how-to-use-svcutil-exe-to-download-metadata-documents.md)
