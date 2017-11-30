---
title: "IHostIoCompletionManager::CloseIoCompletionPort メソッド"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostIoCompletionManager.CloseIoCompletionPort
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostIoCompletionManager::CloseIoCompletionPort
helpviewer_keywords:
- IHostIoCompletionManager::CloseIoCompletionPort method [.NET Framework hosting]
- CloseIoCompletionPort method [.NET Framework hosting]
ms.assetid: e86ad7be-3758-498a-a972-5522d69dfbb3
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 066d51c821cf86522ffaca4c15db360ce96ed773
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2017
---
# <a name="ihostiocompletionmanagercloseiocompletionport-method"></a><span data-ttu-id="48f3f-102">IHostIoCompletionManager::CloseIoCompletionPort メソッド</span><span class="sxs-lookup"><span data-stu-id="48f3f-102">IHostIoCompletionManager::CloseIoCompletionPort Method</span></span>
<span data-ttu-id="48f3f-103">ホストが事前に呼び出したを通じて開かれたポートを閉じることを要求[CreateIoCompletionPort](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-createiocompletionport-method.md)です。</span><span class="sxs-lookup"><span data-stu-id="48f3f-103">Requests that the host close a port that was opened through an earlier call to [CreateIoCompletionPort](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-createiocompletionport-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48f3f-104">構文</span><span class="sxs-lookup"><span data-stu-id="48f3f-104">Syntax</span></span>  
  
```  
HRESULT CloseIoCompletionPort (  
    [in] HANDLE hPort  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="48f3f-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="48f3f-105">Parameters</span></span>  
 `hPort`  
 <span data-ttu-id="48f3f-106">[in]ポートを閉じるのハンドル。</span><span class="sxs-lookup"><span data-stu-id="48f3f-106">[in] The handle of the port to close.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="48f3f-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="48f3f-107">Return Value</span></span>  
  
|<span data-ttu-id="48f3f-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="48f3f-108">HRESULT</span></span>|<span data-ttu-id="48f3f-109">説明</span><span class="sxs-lookup"><span data-stu-id="48f3f-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="48f3f-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="48f3f-110">S_OK</span></span>|<span data-ttu-id="48f3f-111">`CloseIoCompletionPort`正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="48f3f-111">`CloseIoCompletionPort` returned successfully.</span></span>|  
|<span data-ttu-id="48f3f-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="48f3f-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="48f3f-113">共通言語ランタイム (CLR) が、プロセスに読み込まれていませんまたは CLR は、状態をマネージ コードを実行またはできないの呼び出しは正常に処理します。</span><span class="sxs-lookup"><span data-stu-id="48f3f-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="48f3f-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="48f3f-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="48f3f-115">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="48f3f-115">The call timed out.</span></span>|  
|<span data-ttu-id="48f3f-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="48f3f-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="48f3f-117">呼び出し元は、ロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="48f3f-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="48f3f-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="48f3f-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="48f3f-119">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="48f3f-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="48f3f-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="48f3f-120">E_FAIL</span></span>|<span data-ttu-id="48f3f-121">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="48f3f-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="48f3f-122">メソッドには、E_FAIL が返される、ときに、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="48f3f-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="48f3f-123">メソッドのホストに以降の呼び出しでは、HOST_E_CLRNOTAVAILABLE を返します。</span><span class="sxs-lookup"><span data-stu-id="48f3f-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="48f3f-124">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="48f3f-124">E_INVALIDARG</span></span>|<span data-ttu-id="48f3f-125">無効なポート ハンドルが渡されました。</span><span class="sxs-lookup"><span data-stu-id="48f3f-125">An invalid port handle was passed.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="48f3f-126">コメント</span><span class="sxs-lookup"><span data-stu-id="48f3f-126">Remarks</span></span>  
 <span data-ttu-id="48f3f-127">`hPort`以前の呼び出しによって作成されたポートへのハンドルをする必要があります`CreateIoCompletionPort`です。</span><span class="sxs-lookup"><span data-stu-id="48f3f-127">`hPort` must be a handle to a port that was created by an earlier call to `CreateIoCompletionPort`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="48f3f-128">要件</span><span class="sxs-lookup"><span data-stu-id="48f3f-128">Requirements</span></span>  
 <span data-ttu-id="48f3f-129">**プラットフォーム:**を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。</span><span class="sxs-lookup"><span data-stu-id="48f3f-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="48f3f-130">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="48f3f-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="48f3f-131">**ライブラリ:** MSCorEE.dll にリソースとして含まれています。</span><span class="sxs-lookup"><span data-stu-id="48f3f-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="48f3f-132">**.NET framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="48f3f-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48f3f-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="48f3f-133">See Also</span></span>  
 [<span data-ttu-id="48f3f-134">ICLRIoCompletionManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="48f3f-134">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)  
 [<span data-ttu-id="48f3f-135">IHostIoCompletionManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="48f3f-135">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)