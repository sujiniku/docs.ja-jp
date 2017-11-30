---
title: "ICorDebugILCode2 インターフェイス"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugILCode2
api_location: mscordbi.dll
api_type: COM
ms.assetid: f9dc2afd-df8a-464d-bdbf-5af0a1d4bf85
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2fd6b7b6b097010a307abbc260cda7c4b73e0f00
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugilcode2-interface"></a><span data-ttu-id="9ccd5-102">ICorDebugILCode2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9ccd5-102">ICorDebugILCode2 Interface</span></span>
<span data-ttu-id="9ccd5-103">[.NET Framework 4.5.2 以降のバージョンでのみでサポート]</span><span class="sxs-lookup"><span data-stu-id="9ccd5-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="9ccd5-104">論理的に拡張し、 [ICorDebugILCode](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md)に元のメソッド IL オフセットを関数のローカル変数シグネチャに対するトークンを返すし、プロファイラーのインストルメント化された中間言語 (IL) にマップするメソッドを提供するインターフェイスオフセットします。</span><span class="sxs-lookup"><span data-stu-id="9ccd5-104">Logically extends the [ICorDebugILCode](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md) interface to provide methods that return the token for a function's local variable signature, and that map a profiler's instrumented intermediate language (IL) offsets to original method IL offsets.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9ccd5-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="9ccd5-105">Methods</span></span>  
  
|<span data-ttu-id="9ccd5-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="9ccd5-106">Method</span></span>|<span data-ttu-id="9ccd5-107">説明</span><span class="sxs-lookup"><span data-stu-id="9ccd5-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9ccd5-108">GetInstrumentedILMap メソッド</span><span class="sxs-lookup"><span data-stu-id="9ccd5-108">GetInstrumentedILMap Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode2-getinstrumentedilmap-method.md)|<span data-ttu-id="9ccd5-109">プロファイラーのインストルメント化された IL オフセットから、このインスタンスに対する元のメソッドの IL オフセットへのマップを返します。</span><span class="sxs-lookup"><span data-stu-id="9ccd5-109">Returns a map from profiler instrumented IL offsets to original method IL offsets for this instance.</span></span>|  
|[<span data-ttu-id="9ccd5-110">GetLocalVarSigToken メソッド</span><span class="sxs-lookup"><span data-stu-id="9ccd5-110">GetLocalVarSigToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode2-getlocalvarsigtoken-method.md)|<span data-ttu-id="9ccd5-111">このインスタンスで示される関数について、ローカル変数のシグネチャのメタデータ トークンを取得します。</span><span class="sxs-lookup"><span data-stu-id="9ccd5-111">Gets the metadata token for the local variable signature for the function that is represented by this instance.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9ccd5-112">要件</span><span class="sxs-lookup"><span data-stu-id="9ccd5-112">Requirements</span></span>  
 <span data-ttu-id="9ccd5-113">**プラットフォーム:**を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。</span><span class="sxs-lookup"><span data-stu-id="9ccd5-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9ccd5-114">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9ccd5-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9ccd5-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9ccd5-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9ccd5-116">**.NET framework のバージョン:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9ccd5-116">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ccd5-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="9ccd5-117">See Also</span></span>  
 [<span data-ttu-id="9ccd5-118">ICorDebugILCode インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9ccd5-118">ICorDebugILCode Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md)  
 [<span data-ttu-id="9ccd5-119">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="9ccd5-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="9ccd5-120">デバッグ</span><span class="sxs-lookup"><span data-stu-id="9ccd5-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)