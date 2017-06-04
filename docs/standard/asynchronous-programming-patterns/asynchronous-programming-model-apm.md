---
title: "Asynchronous Programming Model (APM) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "ending asynchronous operations"
  - "starting asynchronous operations"
  - "beginning asynchronous operations"
  - "asynchronous programming, ending operations"
  - "asynchronous programming"
  - "stopping asynchronous operations"
  - "asynchronous programming, beginning operations"
ms.assetid: c9b3501e-6bc6-40f9-8efd-4b6d9e39ccf0
caps.latest.revision: 13
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 13
---
# Asynchronous Programming Model (APM)
<xref:System.IAsyncResult> デザイン パターンを使用する非同期操作は **Begin** *OperationName* と **End** *OperationName* という名前の、各 *OperationName* 非同期操作を開始および終了する 2 種類のメソッドとして実装されます。 たとえば、<xref:System.IO.FileStream> クラスは、<xref:System.IO.FileStream.BeginRead%2A> および <xref:System.IO.FileStream.EndRead%2A> メソッドを提供して、非同期的にファイルからバイトを読み取ります。 これらのメソッドは非同期バージョンの <xref:System.IO.FileStream.Read%2A> メソッドを実装します。  
  
> [!NOTE]
>  .NET Framework 4 以降では、タスク並列ライブラリによって非同期\/並列プログラミングの新しいモデルが提供されます。 詳細については、「[Task Parallel Library \(TPL\)](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md)」および「[Task\-based Asynchronous Pattern \(TAP\)](../../../docs/standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md)」を参照してください。  
  
 **Begin** *OperationName* を呼び出した後、アプリケーションは別のスレッドで非同期操作が行われている間も、スレッドの呼び出しに関する命令の実行を続行できます。**Begin** *OperationName* の呼び出しごとに、アプリケーションでは **End** *OperationName* も呼び出して、操作の結果を取得する必要があります。  
  
## 非同期操作の開始  
 **Begin** *OperationName* メソッドは非同期操作 *OperationName* を開始し、<xref:System.IAsyncResult> インターフェイスを実装するオブジェクトを返します。<xref:System.IAsyncResult> オブジェクトは非同期操作に関する情報を格納します。 非同期操作に関する情報を次の表に示します。  
  
|メンバー|説明|  
|----------|--------|  
|<xref:System.IAsyncResult.AsyncState%2A>|非同期操作についての情報を格納するオプションのアプリケーション固有オブジェクト。|  
|<xref:System.IAsyncResult.AsyncWaitHandle%2A>|<xref:System.Threading.WaitHandle>。非同期操作が完了するまでアプリケーションの実行をブロックするために使用できます。|  
|<xref:System.IAsyncResult.CompletedSynchronously%2A>|非同期操作が別の <xref:System.Threading.ThreadPool> スレッドで完了する代わりに、**Begin** *OperationName* の呼び出しに使用されたスレッドで完了したかどうかを示す値。|  
|<xref:System.IAsyncResult.IsCompleted%2A>|非同期操作が完了したかどうかを示す値。|  
  
 **Begin** *OperationName* メソッドは、同期バージョンのメソッドのシグネチャで宣言された、値渡しまたは参照渡しのパラメーターを受け取ります。 どの out パラメーターも、**Begin** *OperationName* メソッド シグネチャの一部ではありません。**Begin** *OperationName* メソッド シグネチャには、2 種類の追加のパラメーターが含まれます。 1 つ目のパラメーターは、非同期操作が完了したときに呼び出されるメソッドを参照する <xref:System.AsyncCallback> デリゲートを定義します。 操作完了時にメソッドを呼び出さない場合、呼び出し元は `null` \(Visual Basic では `Nothing`\) を指定できます。 2 つ目の追加のパラメーターは、ユーザー定義オブジェクトです。 このオブジェクトは、アプリケーション固有の状態情報を、非同期操作が完了したときに呼び出されるメソッドに渡すために使用できます。**Begin** *OperationName* メソッドが、ファイルから読み取ったバイトを格納するバイト配列など操作固有の追加のパラメーターを受け取る場合は、<xref:System.AsyncCallback> とアプリケーション状態オブジェクトが **Begin** *OperationName* メソッド シグネチャの最後のパラメーターになります。  
  
 **Begin** *OperationName* は、瞬時にコントロールを呼び出し元スレッドに返します。**Begin** *OperationName* メソッドが例外をスローする場合は、非同期操作が開始される前に例外がスローされます。**Begin** *OperationName* メソッドが例外をスローする場合、コールバック メソッドは呼び出されません。  
  
## 非同期操作の終了  
 **End** *OperationName* メソッドは、非同期操作の *OperationName* を終了します。**End** *OperationName* メソッドの戻り値は、このメソッドの対応する同期操作によって返される型と同じ型であり、非同期操作に固有です。 たとえば、<xref:System.IO.FileStream.EndRead%2A> メソッドは <xref:System.IO.FileStream> から読み取ったバイト数を返し、<xref:System.Net.Dns.EndGetHostByName%2A> メソッドはホスト コンピューターに関する情報を含む <xref:System.Net.IPHostEntry> オブジェクトを返します。**End** *OperationName* メソッドは、メソッドの同期バージョンのシグネチャで宣言された out パラメーターや ref パラメーターをすべて受け取ります。**End** *OperationName* メソッドには、同期メソッドからのパラメーターに加えて <xref:System.IAsyncResult> パラメーターが含まれています。 呼び出し元は、対応する呼び出しから返されたインスタンスを **Begin** *OperationName* に渡す必要があります。  
  
 **End** *OperationName* が呼び出されるときに <xref:System.IAsyncResult> オブジェクトによって表される非同期操作が完了していない場合、**End** *OperationName* は非同期操作が完了するまで、呼び出し元スレッドをブロックします。 非同期操作によってスローされた例外は、**End** *OperationName* メソッドからスローされます。 同じ <xref:System.IAsyncResult> を使用して **End** *OperationName* メソッドを複数回呼び出す場合の効果は定義されません。 同様に、関連する Begin メソッドによって返されたのではない <xref:System.IAsyncResult> を使用した **End** *OperationName* メソッドの呼び出しも定義されません。  
  
> [!NOTE]
>  どちらの未定義シナリオの場合でも、実装者は <xref:System.InvalidOperationException> のスローを検討する必要があります。  
  
> [!NOTE]
>  このデザイン パターンの実装者は <xref:System.IAsyncResult.IsCompleted%2A> を true に設定し、非同期コールバック メソッドを呼び出して \(指定されている場合\)、<xref:System.IAsyncResult.AsyncWaitHandle%2A> をシグナリングすることで、非同期操作の完了を呼び出し元に通知する必要があります。  
  
 アプリケーション開発者には、非同期操作の結果にアクセスするための、デザイン上の選択肢がいくつかあります。 どの選択が適切になるかは、アプリケーションが操作の完了前に実行できる命令を持っているかどうかによって変わります。 非同期操作の結果を受け取るまで、アプリケーションが別の作業を実行できない場合は、結果が使用可能になるまで、そのアプリケーションをブロックする必要があります。 非同期操作が完了するまでブロックするには、次に示す方法の 1 つを使用します。  
  
-   アプリケーションのメイン スレッドから **End** *OperationName* を呼び出し、操作が完了するまでアプリケーションの実行をブロックします。 この手法の例については、「[Blocking Application Execution by Ending an Async Operation](../../../docs/standard/asynchronous-programming-patterns/blocking-application-execution-by-ending-an-async-operation.md)」を参照してください。  
  
-   <xref:System.IAsyncResult.AsyncWaitHandle%2A> を使用して、1 つ以上の操作が完了するまでアプリケーションの実行をブロックします。 この手法の例については、「[Blocking Application Execution Using an AsyncWaitHandle](../../../docs/standard/asynchronous-programming-patterns/blocking-application-execution-using-an-asyncwaithandle.md)」を参照してください。  
  
 非同期操作が完了するまでアプリケーションをブロックする必要がない場合は、次のいずれかの方法を使用します。  
  
-   <xref:System.IAsyncResult.IsCompleted%2A> プロパティを定期的に確認し、操作が完了したときに **End** *OperationName* を呼び出して、操作完了ステータスをポーリングします。 この手法の例については、「[Polling for the Status of an Asynchronous Operation](../../../docs/standard/asynchronous-programming-patterns/polling-for-the-status-of-an-asynchronous-operation.md)」を参照してください。  
  
-   <xref:System.AsyncCallback> デリゲートを使用して、操作が完了したときに呼び出されるメソッドを指定します。 この手法の例については、「[Using an AsyncCallback Delegate to End an Asynchronous Operation](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md)」を参照してください。  
  
## 参照  
 [Event\-based Asynchronous Pattern \(EAP\)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)   
 [Calling Synchronous Methods Asynchronously](../../../docs/standard/asynchronous-programming-patterns/calling-synchronous-methods-asynchronously.md)   
 [Using an AsyncCallback Delegate and State Object](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-and-state-object.md)