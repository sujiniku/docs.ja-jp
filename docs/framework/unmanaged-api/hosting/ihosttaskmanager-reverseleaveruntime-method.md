---
title: "IHostTaskManager::ReverseLeaveRuntime メソッド"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostTaskManager.ReverseLeaveRuntime
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostTaskManager::ReverseLeaveRuntime
helpviewer_keywords:
- IHostTaskManager::ReverseLeaveRuntime method [.NET Framework hosting]
- ReverseLeaveRuntime method [.NET Framework hosting]
ms.assetid: 4837d398-16a1-4e32-902c-022cd1aad3ca
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: db8a9114cd15a4e7d42e8f99941d4bcbb9faa842
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2017
---
# <a name="ihosttaskmanagerreverseleaveruntime-method"></a><span data-ttu-id="ce460-102">IHostTaskManager::ReverseLeaveRuntime メソッド</span><span class="sxs-lookup"><span data-stu-id="ce460-102">IHostTaskManager::ReverseLeaveRuntime Method</span></span>
<span data-ttu-id="ce460-103">コントロールが共通言語ランタイム (CLR) のままであり、さらに、マネージ コードから呼び出されたアンマネージ関数を入力することをホストに通知します。</span><span class="sxs-lookup"><span data-stu-id="ce460-103">Notifies the host that control is leaving the common language runtime (CLR) and entering an unmanaged function that was, in turn, called from managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce460-104">構文</span><span class="sxs-lookup"><span data-stu-id="ce460-104">Syntax</span></span>  
  
```  
HRESULT ReverseLeaveRuntime ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="ce460-105">戻り値</span><span class="sxs-lookup"><span data-stu-id="ce460-105">Return Value</span></span>  
  
|<span data-ttu-id="ce460-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ce460-106">HRESULT</span></span>|<span data-ttu-id="ce460-107">説明</span><span class="sxs-lookup"><span data-stu-id="ce460-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ce460-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="ce460-108">S_OK</span></span>|<span data-ttu-id="ce460-109">`ReverseLeaveRuntime`正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="ce460-109">`ReverseLeaveRuntime` returned successfully.</span></span>|  
|<span data-ttu-id="ce460-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ce460-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ce460-111">CLR が、プロセスに読み込まれていませんまたは CLR は、状態をマネージ コードを実行またはできないの呼び出しは正常に処理します。</span><span class="sxs-lookup"><span data-stu-id="ce460-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ce460-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ce460-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ce460-113">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="ce460-113">The call timed out.</span></span>|  
|<span data-ttu-id="ce460-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ce460-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ce460-115">呼び出し元は、ロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="ce460-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ce460-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ce460-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ce460-117">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="ce460-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ce460-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ce460-118">E_FAIL</span></span>|<span data-ttu-id="ce460-119">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="ce460-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ce460-120">メソッドには、E_FAIL が返される、ときに、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="ce460-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ce460-121">メソッドのホストに以降の呼び出しでは、HOST_E_CLRNOTAVAILABLE を返します。</span><span class="sxs-lookup"><span data-stu-id="ce460-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="ce460-122">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="ce460-122">E_OUTOFMEMORY</span></span>|<span data-ttu-id="ce460-123">十分なメモリが要求されたリソースの割り当てを完了します。</span><span class="sxs-lookup"><span data-stu-id="ce460-123">Not enough memory is available to complete the requested resource allocation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ce460-124">コメント</span><span class="sxs-lookup"><span data-stu-id="ce460-124">Remarks</span></span>  
 <span data-ttu-id="ce460-125">CLR 呼び出し`ReverseLeaveRuntime`プラットフォームを通じてマネージ コードから呼び出された、さらに、アンマネージ関数に制御を呼び出し、現在実行中のタスクを返すことをホストに通知します。</span><span class="sxs-lookup"><span data-stu-id="ce460-125">The CLR calls `ReverseLeaveRuntime` to inform the host that the currently executing task is returning control to an unmanaged function that was, in turn, called from managed code through platform invoke.</span></span> <span data-ttu-id="ce460-126">各呼び出し`ReverseLeaveRuntime`に対応する呼び出しと一致する[ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md)です。</span><span class="sxs-lookup"><span data-stu-id="ce460-126">Each call to `ReverseLeaveRuntime` matches a corresponding call to [ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ce460-127">要件</span><span class="sxs-lookup"><span data-stu-id="ce460-127">Requirements</span></span>  
 <span data-ttu-id="ce460-128">**プラットフォーム:**を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。</span><span class="sxs-lookup"><span data-stu-id="ce460-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ce460-129">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ce460-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ce460-130">**ライブラリ:** MSCorEE.dll にリソースとして含まれています。</span><span class="sxs-lookup"><span data-stu-id="ce460-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ce460-131">**.NET framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ce460-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce460-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="ce460-132">See Also</span></span>  
 [<span data-ttu-id="ce460-133">CallNeedsHostHook メソッド</span><span class="sxs-lookup"><span data-stu-id="ce460-133">CallNeedsHostHook Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-callneedshosthook-method.md)  
 [<span data-ttu-id="ce460-134">EnterRuntime メソッド</span><span class="sxs-lookup"><span data-stu-id="ce460-134">EnterRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md)  
 [<span data-ttu-id="ce460-135">ICLRTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ce460-135">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="ce460-136">ICLRTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ce460-136">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="ce460-137">IHostTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ce460-137">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="ce460-138">IHostTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ce460-138">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [<span data-ttu-id="ce460-139">LeaveRuntime メソッド</span><span class="sxs-lookup"><span data-stu-id="ce460-139">LeaveRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md)  
 [<span data-ttu-id="ce460-140">詳しく見てプラットフォーム呼び出し</span><span class="sxs-lookup"><span data-stu-id="ce460-140">A Closer Look at Platform Invoke</span></span>](http://msdn.microsoft.com/en-us/ba9dd55b-2eaa-45cd-8afd-75cb8d64d243)