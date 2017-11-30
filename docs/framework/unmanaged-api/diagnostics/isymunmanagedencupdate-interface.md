---
title: "ISymUnmanagedENCUpdate インターフェイス"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedENCUpdate
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedENCUpdate
helpviewer_keywords: ISymUnmanagedENCUpdate interface [.NET Framework debugging]
ms.assetid: 63a9ef45-01a6-46da-b958-5c6dc2dc232c
topic_type: apiref
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 36ac53094751cb43ef122d439c7a784070c28182
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedencupdate-interface"></a><span data-ttu-id="dbade-102">ISymUnmanagedENCUpdate インターフェイス</span><span class="sxs-lookup"><span data-stu-id="dbade-102">ISymUnmanagedENCUpdate Interface</span></span>
<span data-ttu-id="dbade-103">関数は、エディット コンティニュ機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="dbade-103">Provides functions for the Edit and Continue feature.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="dbade-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="dbade-104">Methods</span></span>  
  
|<span data-ttu-id="dbade-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="dbade-105">Method</span></span>|<span data-ttu-id="dbade-106">説明</span><span class="sxs-lookup"><span data-stu-id="dbade-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="dbade-107">GetLocalVariableCount メソッド</span><span class="sxs-lookup"><span data-stu-id="dbade-107">GetLocalVariableCount Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-getlocalvariablecount-method.md)|<span data-ttu-id="dbade-108">ローカル変数の数を取得します。</span><span class="sxs-lookup"><span data-stu-id="dbade-108">Gets the number of local variables.</span></span>|  
|[<span data-ttu-id="dbade-109">GetLocalVariables メソッド</span><span class="sxs-lookup"><span data-stu-id="dbade-109">GetLocalVariables Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-getlocalvariables-method.md)|<span data-ttu-id="dbade-110">ローカル変数を取得します。</span><span class="sxs-lookup"><span data-stu-id="dbade-110">Gets the local variables.</span></span>|  
|[<span data-ttu-id="dbade-111">InitializeForEnc メソッド</span><span class="sxs-lookup"><span data-stu-id="dbade-111">InitializeForEnc Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-initializeforenc-method.md)|<span data-ttu-id="dbade-112">により、最初の呼び出しの前に計算するメソッドの境界を越えて、 [isymunmanagedencupdate::updatesymbolstore2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-updatesymbolstore2-method.md)メソッドです。</span><span class="sxs-lookup"><span data-stu-id="dbade-112">Allows method boundaries to be computed before the first call to the [ISymUnmanagedENCUpdate::UpdateSymbolStore2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-updatesymbolstore2-method.md) method.</span></span>|  
|[<span data-ttu-id="dbade-113">UpdateMethodLines メソッド</span><span class="sxs-lookup"><span data-stu-id="dbade-113">UpdateMethodLines Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-updatemethodlines-method.md)|<span data-ttu-id="dbade-114">再コンパイルされていないがある行が個別に移動されたメソッドの行情報を更新できるようにします。</span><span class="sxs-lookup"><span data-stu-id="dbade-114">Allows updating the line information for a method that has not been recompiled, but whose lines have moved independently.</span></span> <span data-ttu-id="dbade-115">各ステートメントのデルタが許可されます。</span><span class="sxs-lookup"><span data-stu-id="dbade-115">A delta for each statement is allowed.</span></span>|  
|[<span data-ttu-id="dbade-116">UpdateSymbolStore2 メソッド</span><span class="sxs-lookup"><span data-stu-id="dbade-116">UpdateSymbolStore2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-updatesymbolstore2-method.md)|<span data-ttu-id="dbade-117">により、コンパイラが行情報が要件を満たしていること、プログラム データベース (PDB) のストリームから変更されていない関数を省略できます。</span><span class="sxs-lookup"><span data-stu-id="dbade-117">Allows a compiler to omit functions that have not been modified from the program database (PDB) stream, provided that the line information meets the requirements.</span></span> <span data-ttu-id="dbade-118">PDB の行の古い情報と、関数のすべての行の 1 つのデルタは、正しい行情報を確認できます。</span><span class="sxs-lookup"><span data-stu-id="dbade-118">The correct line information can be determined with the old PDB line information and one delta for all lines in the function.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="dbade-119">要件</span><span class="sxs-lookup"><span data-stu-id="dbade-119">Requirements</span></span>  
 <span data-ttu-id="dbade-120">**ヘッダー:** CorSym.idl、CorSym.h</span><span class="sxs-lookup"><span data-stu-id="dbade-120">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dbade-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="dbade-121">See Also</span></span>  
 [<span data-ttu-id="dbade-122">シンボル ストア診断インターフェイスします。</span><span class="sxs-lookup"><span data-stu-id="dbade-122">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)