---
title: '&lt;net.tcp&gt;'
ms.date: 03/30/2017
ms.assetid: 8bc2f2be-11c1-4bab-9018-1d21ae568d94
ms.openlocfilehash: 9e44ddcc3a3e983abe6e36d4b6095c5c4a67529f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="ltnettcpgt"></a>&lt;net.tcp&gt;
複数のプロセスが同じ TCP ポートを共有できる NET.TCP ポート共有サービスの構成設定を指定します。  
  
 \<system.serviceModel.activation>  
\<net.tcp>  
  
## <a name="syntax"></a>構文  
  
```xml  
<configuration>  
   <system.serviceModel.activation>  
       <net.tcp listenBacklog="Integer"  
          maxPendingAccepts="Integer"  
          maxPendingConnections="Integer"  
          receiveTimeout="TimeSpan"  
          teredoEnabled="Boolean">  
          <allowAccounts>  
             <!-- LocalSystem account -->   
             <add securityIdentifier="S-1-5-18"/>  
             <!-- LocalService account -->   
             <add securityIdentifier="S-1-5-19"/>  
             <!-- Administrators account -->   
             <add securityIdentifier="S-1-5-20"/>  
             <!-- Network Service account -->   
             <add securityIdentifier="S-1-5-32-544" />  
             <!-- IIS_IUSRS account (Vista only)-->   
             <add securityIdentifier="S-1-5-32-568"/>  
           </allowAccounts>  
       </net.tcp>  
   </system.serviceModel.activation>  
</configuration>  
```  
  
## <a name="type"></a>型  
 `Type`  
  
## <a name="attributes-and-elements"></a>属性および要素  
 以降のセクションでは、属性、子要素、および親要素について説明します。  
  
### <a name="attributes"></a>属性  
  
|属性|説明|  
|---------------|-----------------|  
|`listenBacklog`|共有接続から受け入れられます Windows Communication Foundation (WCF) サービスにまだディスパッチされていない最大の未処理の接続を指定する整数。 既定値は 10 です。|  
|`maxPendingAccepts`|整数は、共有サービスの待機エンドポイントで同時に受け入れる未処理のスレッドの最大数を示しています。 既定値は 2 です。|  
|`MaxPendingConnections`|アプリケーションによる受け入れをリスナーで待機できる最大接続数。 このクォータ値を超過すると、新規の受信接続は受け入れられるのを待機せずに切断されます。 メッセージ セキュリティのような接続機能では、クライアントは複数の接続を開くことがあります。 このクォータ値を設定する場合、サービス管理者はこのような追加の接続も考慮する必要があります。 既定値は 10 です。|  
|`receiveTimeout`|フレーム データを読み取り、基礎となる接続から接続ディスパッチを実行するタイムアウトを指定する `TimeSpan` です。 既定値は "00:00:10" です。|  
|`teredoEnabled`|WCF サービスに代わって TCP ポートでリッスンするように、ポート共有サービスが Microsoft Teredo サービスを使用しているかどうかを示すブール値。 既定値は、`false` です。|  
  
### <a name="child-elements"></a>子要素  
  
|要素|説明|  
|-------------|-----------------|  
|[\<allowAccounts>](../../../../../docs/framework/configure-apps/file-schema/wcf/allowaccounts.md)|含む構成要素のコレクション、`securityIdentifier`属性を WCF サービスをホストし、共有サービスへの接続アクセスが許可されるプロセスのユーザー アカウントを指定します。|  
  
### <a name="parent-elements"></a>親要素  
  
|要素|説明|  
|-------------|-----------------|  
|[\<system.serviceModel.activation >](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel-activation.md)|リスナー プロセス SMSvcHost.exe の設定が含まれています。|  
  
## <a name="remarks"></a>コメント  
 ポート共有の詳細については、次を参照してください。 [Net.TCP ポート共有](http://msdn.microsoft.com/library/f13692ee-a179-4439-ae72-50db9534eded)です。 ポート共有サービスを構成する方法を理解するには、次を参照してください。 [Net.TCP ポート共有サービスを構成する](http://msdn.microsoft.com/library/b6dd81fa-68b7-4e1b-868e-88e5901b7ea0)です。  
  
## <a name="see-also"></a>関連項目  
 <xref:System.ServiceModel.Activation.Configuration.NetTcpSection>  
 [Net.TCP ポート共有](http://msdn.microsoft.com/library/f13692ee-a179-4439-ae72-50db9534eded)  
 [Net.TCP ポート共有サービスを構成する](http://msdn.microsoft.com/library/b6dd81fa-68b7-4e1b-868e-88e5901b7ea0)
