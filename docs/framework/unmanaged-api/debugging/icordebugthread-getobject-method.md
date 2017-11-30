---
title: "ICorDebugThread::GetObject メソッド"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugThread.GetObject
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugThread::GetObject
helpviewer_keywords:
- GetObject method, ICorDebugThread interface [.NET Framework debugging]
- ICorDebugThread::GetObject method [.NET Framework debugging]
ms.assetid: 1590febe-96c2-4046-97db-d81d81d67e01
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 94e6d69ff2a873f387da0e93bcd859d53103d4b5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugthreadgetobject-method"></a><span data-ttu-id="c00b7-102">ICorDebugThread::GetObject メソッド</span><span class="sxs-lookup"><span data-stu-id="c00b7-102">ICorDebugThread::GetObject Method</span></span>
<span data-ttu-id="c00b7-103">共通言語ランタイム (CLR) のスレッドにインターフェイス ポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="c00b7-103">Gets an interface pointer to the common language runtime (CLR) thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c00b7-104">構文</span><span class="sxs-lookup"><span data-stu-id="c00b7-104">Syntax</span></span>  
  
```  
HRESULT GetObject (  
    [out] ICorDebugValue   **ppObject  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c00b7-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c00b7-105">Parameters</span></span>  
 `ppObject`  
 <span data-ttu-id="c00b7-106">[out]CLR スレッドを表す ICorDebugValue インターフェイス オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="c00b7-106">[out] A pointer to the address of an ICorDebugValue interface object that represents the CLR thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c00b7-107">要件</span><span class="sxs-lookup"><span data-stu-id="c00b7-107">Requirements</span></span>  
 <span data-ttu-id="c00b7-108">**プラットフォーム:**を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。</span><span class="sxs-lookup"><span data-stu-id="c00b7-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c00b7-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c00b7-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c00b7-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c00b7-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c00b7-111">**.NET framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c00b7-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c00b7-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="c00b7-112">See Also</span></span>  
 <xref:System.Threading.Thread>