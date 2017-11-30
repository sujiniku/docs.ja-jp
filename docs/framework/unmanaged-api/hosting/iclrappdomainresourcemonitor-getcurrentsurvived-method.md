---
title: "ICLRAppDomainResourceMonitor::GetCurrentSurvived メソッド"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRAppDomainResourceMonitor.GetCurrentSurvived
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRAppDomainResourceMonitor::GetCurrentSurvived
helpviewer_keywords:
- ICLRAppDomainResourceMonitor::GetCurrentSurvived method [.NET Framework hosting]
- GetCurrentSurvived method [.NET Framework hosting]
ms.assetid: 392e9009-40ef-40e3-ad4d-7ce93a989e78
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b9fe624c83be5dcf762f1c6036f8e4264f0e45c5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2017
---
# <a name="iclrappdomainresourcemonitorgetcurrentsurvived-method"></a><span data-ttu-id="72ff6-102">ICLRAppDomainResourceMonitor::GetCurrentSurvived メソッド</span><span class="sxs-lookup"><span data-stu-id="72ff6-102">ICLRAppDomainResourceMonitor::GetCurrentSurvived Method</span></span>
<span data-ttu-id="72ff6-103">最後のフル ブロッキング ガベージ コレクションで残ったをして、現在のアプリケーション ドメインによって参照されているバイト数を取得します。</span><span class="sxs-lookup"><span data-stu-id="72ff6-103">Gets the number of bytes that survived the last full, blocking garbage collection and that are referenced by the current application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72ff6-104">構文</span><span class="sxs-lookup"><span data-stu-id="72ff6-104">Syntax</span></span>  
  
```  
HRESULT STDMETHODCALLTYPE GetCurrentSurvived(  
             [in]  DWORD dwAppDomainId,  
             [out] ULONGLONG *pAppDomainBytesSurvived,  
             [out] ULONGLONG *pTotalBytesSurvived);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="72ff6-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="72ff6-105">Parameters</span></span>  
 `dwAppDomainId`  
 <span data-ttu-id="72ff6-106">[in]要求されたアプリケーション ドメインの ID。</span><span class="sxs-lookup"><span data-stu-id="72ff6-106">[in] The ID of the requested application domain.</span></span>  
  
 `pAppDomainBytesSurvived`  
 <span data-ttu-id="72ff6-107">[out]このアプリケーション ドメインによって保持されている最後のガベージ コレクションの後に残ったバイト数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="72ff6-107">[out] A pointer to the number of bytes that survived after the last garbage collection that are held by this application domain.</span></span> <span data-ttu-id="72ff6-108">完全なコレクションの後にこの番号は正確で完全です。</span><span class="sxs-lookup"><span data-stu-id="72ff6-108">After a full collection, this number is accurate and complete.</span></span> <span data-ttu-id="72ff6-109">短期コレクションの後に、この番号は完全な可能性のあるではありません。</span><span class="sxs-lookup"><span data-stu-id="72ff6-109">After an ephemeral collection, this number is potentially incomplete.</span></span> <span data-ttu-id="72ff6-110">このパラメーターは、`null` に設定できます。</span><span class="sxs-lookup"><span data-stu-id="72ff6-110">This parameter can be `null`.</span></span>  
  
 `pRuntimeBytesSurvived`  
 <span data-ttu-id="72ff6-111">[out]最後のガベージ コレクションの後に残ったバイトの総数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="72ff6-111">[out] A pointer to the total number of bytes that survived from the last garbage collection.</span></span> <span data-ttu-id="72ff6-112">完全なコレクションの後に、この数は、マネージ ヒープ内に保持されているバイト数を表します。</span><span class="sxs-lookup"><span data-stu-id="72ff6-112">After a full collection, this number represents the number of the bytes that are held in managed heaps.</span></span> <span data-ttu-id="72ff6-113">短期コレクションの後は、この数は短期のジェネレーションにライブで保持されているバイト数を表します。</span><span class="sxs-lookup"><span data-stu-id="72ff6-113">After an ephemeral collection, this number represents the number of bytes that are held live in ephemeral generations.</span></span> <span data-ttu-id="72ff6-114">このパラメーターは、`null` に設定できます。</span><span class="sxs-lookup"><span data-stu-id="72ff6-114">This parameter can be `null`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="72ff6-115">戻り値</span><span class="sxs-lookup"><span data-stu-id="72ff6-115">Return Value</span></span>  
 <span data-ttu-id="72ff6-116">このメソッドは、次の特定の HRESULT と、メソッドの失敗を示す HRESULT エラーも返します。</span><span class="sxs-lookup"><span data-stu-id="72ff6-116">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="72ff6-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="72ff6-117">HRESULT</span></span>|<span data-ttu-id="72ff6-118">説明</span><span class="sxs-lookup"><span data-stu-id="72ff6-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="72ff6-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="72ff6-119">S_OK</span></span>|<span data-ttu-id="72ff6-120">メソッドは正常に完了しました。</span><span class="sxs-lookup"><span data-stu-id="72ff6-120">The method completed successfully.</span></span>|  
|<span data-ttu-id="72ff6-121">COR_E_APPDOMAINUNLOADED</span><span class="sxs-lookup"><span data-stu-id="72ff6-121">COR_E_APPDOMAINUNLOADED</span></span>|<span data-ttu-id="72ff6-122">アプリケーション ドメインがアンロードされたか、存在しません。</span><span class="sxs-lookup"><span data-stu-id="72ff6-122">The application domain has been unloaded or does not exist.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="72ff6-123">コメント</span><span class="sxs-lookup"><span data-stu-id="72ff6-123">Remarks</span></span>  
 <span data-ttu-id="72ff6-124">統計がフル ブロッキング ガベージ コレクション後にのみ更新されます。つまり、すべてのジェネレーションが含まれていると、コレクションの中に、アプリケーションが停止するコレクションが発生します。</span><span class="sxs-lookup"><span data-stu-id="72ff6-124">Statistics are updated only after a full, blocking garbage collection; that is, a collection that includes all generations and that stops the application while collection occurs.</span></span> <span data-ttu-id="72ff6-125">たとえば、<xref:System.GC.Collect?displayProperty=nameWithType>メソッドのオーバー ロードがフル ブロッキング コレクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="72ff6-125">For example, the <xref:System.GC.Collect?displayProperty=nameWithType> method overload performs a full, blocking collection.</span></span> <span data-ttu-id="72ff6-126">同時実行ガベージ コレクションは、バック グラウンドで行われ、アプリケーションをブロックしません。</span><span class="sxs-lookup"><span data-stu-id="72ff6-126">Concurrent garbage collection occurs in the background and does not block the application.</span></span>  
  
 <span data-ttu-id="72ff6-127">`GetCurrentSurvived`メソッドは、アンマネージ相当するマネージ<xref:System.AppDomain.MonitoringSurvivedMemorySize%2A?displayProperty=nameWithType>プロパティです。</span><span class="sxs-lookup"><span data-stu-id="72ff6-127">The `GetCurrentSurvived` method is the unmanaged equivalent of the managed <xref:System.AppDomain.MonitoringSurvivedMemorySize%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="72ff6-128">要件</span><span class="sxs-lookup"><span data-stu-id="72ff6-128">Requirements</span></span>  
 <span data-ttu-id="72ff6-129">**プラットフォーム:**を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。</span><span class="sxs-lookup"><span data-stu-id="72ff6-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="72ff6-130">**ヘッダー:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="72ff6-130">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="72ff6-131">**ライブラリ:** MSCorEE.dll にリソースとして含まれています。</span><span class="sxs-lookup"><span data-stu-id="72ff6-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="72ff6-132">**.NET framework のバージョン:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="72ff6-132">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72ff6-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="72ff6-133">See Also</span></span>  
 [<span data-ttu-id="72ff6-134">ICLRAppDomainResourceMonitor インターフェイス</span><span class="sxs-lookup"><span data-stu-id="72ff6-134">ICLRAppDomainResourceMonitor Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md)  
 [<span data-ttu-id="72ff6-135">アプリケーション ドメインのリソース監視</span><span class="sxs-lookup"><span data-stu-id="72ff6-135">Application Domain Resource Monitoring</span></span>](../../../../docs/standard/garbage-collection/app-domain-resource-monitoring.md)  
 [<span data-ttu-id="72ff6-136">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="72ff6-136">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="72ff6-137">ホスティング</span><span class="sxs-lookup"><span data-stu-id="72ff6-137">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)