---
title: '方法: 待機ハンドルがあるキャンセル要求を待機する'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cancellation, waiting with wait handles
ms.assetid: 6e2aa49b-fc84-4bcf-962b-17db98b7edcb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6543c2e5ea953887e699ee6f9ca3b70e08e5ae85
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33583917"
---
# <a name="how-to-listen-for-cancellation-requests-that-have-wait-handles"></a>方法: 待機ハンドルがあるキャンセル要求を待機する
イベントがシグナル状態になるのを待機している間にメソッドがブロックされた場合、取り消しトークンの値を確認して、適切なタイミングで応答することはできません。 最初の例は、統合取り消しフレームワークをネイティブにサポートしない <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType> などのイベントの処理時にこの問題を解決する方法を示しています。 2 番目の例は、統合取り消しをサポートする、<xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType> を使用するより効率的な方法を示しています。  
  
> [!NOTE]
>  [マイ コードのみ] が有効になっている場合、Visual Studio では、例外をスローする行で処理が中断され、"ユーザー コードで処理されない例外" に関するエラー メッセージが表示されることがあります。 このエラーは問題にはなりません。 F5 キーを押して、処理が中断された箇所から続行し、以下の例に示す例外処理動作を確認できます。 Visual Studio による処理が最初のエラーで中断しないようにするには、**[ツール] メニューの [オプション]、[デバッグ] 、[全般]** の順にクリックし、[マイ コードのみ] チェック ボックスをオフにします。  
  
## <a name="example"></a>例  
 次の例では <xref:System.Threading.ManualResetEvent> を使用して、統合取り消しをサポートしない待機ハンドルのブロックを解除する方法を示します。  
  
 [!code-csharp[Cancellation#9](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/cancellationex9.cs#9)]
 [!code-vb[Cancellation#9](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/cancellationex9.vb#9)]  
  
## <a name="example"></a>例  
 次の例では <xref:System.Threading.ManualResetEventSlim> を使用して、統合取り消しをサポートするコーディネーション プリミティブのブロックを解除する方法を示します。 <xref:System.Threading.Semaphore>`Slim` や <xref:System.Threading.CountdownEvent> などの他の軽量なコーディネーション プリミティブでも同じ方法を使用することができます。  
  
 [!code-csharp[Cancellation#10](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/cancellationex10.cs#10)]
 [!code-vb[Cancellation#10](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/cancellationex10.vb#10)]  
  
## <a name="see-also"></a>参照  
 [マネージ スレッドのキャンセル](../../../docs/standard/threading/cancellation-in-managed-threads.md)
