---
title: SOA アプリケーション
description: Microsoft プラットフォームとツールでコンテナー化された Docker アプリケーションのライフサイクル
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: 37313c4eb437b6b7a362456a7d1ee3b3aecb6020
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33569426"
---
# <a name="soa-applications"></a>SOA アプリケーション

SOA 過剰使用されている用語、別の人に非常に多くのさまざまなものを意図したもの。 少なくともと共通の基盤、SOA、またはサービスの向き、平均する構造体 (最も一般的な HTTP サービス) としてさまざまな種類で分類可能な複数のサービスに分解することによって、アプリケーションのアーキテクチャなどのサブシステムが、または、層とそれ以外の場合にします。

今日では、依存関係をすべて、コンテナー イメージに含まれているために、展開に関連する問題を解決する Docker コンテナーとしてそれらのサービスを展開できます。 ただし、Soa のスケール アウトする必要がある場合がありますの課題に基づいて 1 つのインスタンスを展開する場合は。 これは、Docker のクラスタ リング ソフトウェアまたは orchestrator が支援する場所です。 見ていきますこれで、次のセクションで詳しくお microservices アプローチを調べる場合です。

1 日の終わりには、コンテナーのクラスタ リング ソリューションは、両方の従来の SOA アーキテクチャまたは各マイクロ サービスがそのデータ モデルを所有するより高度な microservices アーキテクチャ用に便利です。 および、複数のデータベースでは、ご協力に感謝するもできるスケール アウト SOA サービスによって共有される単一のデータベースの操作ではなく、データ層です。 ただし、データの分割についての説明は、アーキテクチャと設計についてのみです。


>[!div class="step-by-step"]
[前] (state-and-data-in-docker-applications.md) [次へ] (調整-高-スケーラビリティ-availability.md)
