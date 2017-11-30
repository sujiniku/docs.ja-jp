---
title: "ICorDebugManagedCallback::BreakpointSetError メソッド"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugManagedCallback.BreakpointSetError
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugManagedCallback::BreakpointSetError
helpviewer_keywords:
- BreakpointSetError method [.NET Framework debugging]
- ICorDebugManagedCallback::BreakpointSetError method [.NET Framework debugging]
ms.assetid: f2b773a4-c4d0-429c-9717-51d6e2ed86af
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 8d8d75261a0ac1211ec54252b698a2a1b17ccac2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugmanagedcallbackbreakpointseterror-method"></a><span data-ttu-id="3570d-102">ICorDebugManagedCallback::BreakpointSetError メソッド</span><span class="sxs-lookup"><span data-stu-id="3570d-102">ICorDebugManagedCallback::BreakpointSetError Method</span></span>
<span data-ttu-id="3570d-103">共通言語ランタイムが正確に関数がジャストでタイム (JIT) コンパイル前に設定されたブレークポイントをバインドできなかったことをデバッガーに通知します。</span><span class="sxs-lookup"><span data-stu-id="3570d-103">Notifies the debugger that the common language runtime was unable to accurately bind a breakpoint that was set before a function was just-in-time (JIT) compiled.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3570d-104">構文</span><span class="sxs-lookup"><span data-stu-id="3570d-104">Syntax</span></span>  
  
```  
HRESULT BreakpointSetError (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] ICorDebugBreakpoint *pBreakpoint,  
    [in] DWORD                dwError  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3570d-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3570d-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="3570d-106">[in]バインドされていないブレークポイントを含むアプリケーション ドメインを表す ICorDebugAppDomain オブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="3570d-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contains the unbound breakpoint.</span></span>  
  
 `pThread`  
 <span data-ttu-id="3570d-107">[in]バインドされていないブレークポイントを含む、スレッドを表す ICorDebugThread オブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="3570d-107">[in] A pointer to an ICorDebugThread object that represents the thread that contains the unbound breakpoint.</span></span>  
  
 `pBreakpoint`  
 <span data-ttu-id="3570d-108">[in]バインドされていないブレークポイントを表す ICorDebugBreakpoint オブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="3570d-108">[in] A pointer to an ICorDebugBreakpoint object that represents the unbound breakpoint.</span></span>  
  
 `dwError`  
 <span data-ttu-id="3570d-109">[in]エラーを示す整数。</span><span class="sxs-lookup"><span data-stu-id="3570d-109">[in] An integer that indicates the error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3570d-110">コメント</span><span class="sxs-lookup"><span data-stu-id="3570d-110">Remarks</span></span>  
 <span data-ttu-id="3570d-111">特定のブレークポイントに到達しません。</span><span class="sxs-lookup"><span data-stu-id="3570d-111">The given breakpoint will never be hit.</span></span> <span data-ttu-id="3570d-112">デバッガーは、非アクティブ化し、再バインドする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3570d-112">The debugger should deactivate and rebind it.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3570d-113">要件</span><span class="sxs-lookup"><span data-stu-id="3570d-113">Requirements</span></span>  
 <span data-ttu-id="3570d-114">**プラットフォーム:**を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。</span><span class="sxs-lookup"><span data-stu-id="3570d-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3570d-115">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3570d-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3570d-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3570d-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3570d-117">**.NET framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3570d-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3570d-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="3570d-118">See Also</span></span>  
 [<span data-ttu-id="3570d-119">ICorDebugManagedCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3570d-119">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)