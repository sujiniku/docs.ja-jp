---
title: Regasm.exe (アセンブリ登録ツール)
ms.date: 03/30/2017
helpviewer_keywords:
- Assembly Registration tool
- assemblies [.NET Framework], registering
- Regasm.exe
- registering assemblies
ms.assetid: e190e342-36ef-4651-a0b4-0e8c2c0281cb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 11ccdb4c75af2b37595d9be977f2ab881ebe1184
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33408747"
---
# <a name="regasmexe-assembly-registration-tool"></a>Regasm.exe (アセンブリ登録ツール)
アセンブリ登録ツールは、1 つのアセンブリに含まれるメタデータを読み込み、必要なエントリをレジストリに追加します。これにより、COM クライアントによって .NET Framework クラスが自動的に作成されます。 クラスが登録されると、どの COM クライアントでも、そのクラスを COM クラスであるかのように使用できます。 クラスの登録は、アセンブリのインストール時に 1 回だけ行われます。 実際に登録されるまでは、アセンブリに含まれるクラスのインスタンスを COM から作成することはできません。  
  
 このツールを実行するには、開発者コマンド プロンプト (または、Windows 7 の Visual Studio コマンド プロンプト) を使用します。 詳細については、「[Visual Studio 用開発者コマンド プロンプト](../../../docs/framework/tools/developer-command-prompt-for-vs.md)」を参照してください。  
  
 コマンド プロンプトに次のように入力します。  
  
## <a name="syntax"></a>構文  
  
```  
regasm assemblyFile [options]  
```  
  
#### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|*assemblyFile*|COM に登録するアセンブリ。|  
  
|オプション|説明|  
|------------|-----------------|  
|**/codebase**|レジストリに Codebase エントリを作成します。 Codebase エントリは、グローバル アセンブリ キャッシュにインストールされないアセンブリのファイル パスを指定します。 登録しようとしているアセンブリを、後でグローバル アセンブリ キャッシュにインストールする場合は、このオプションを指定する必要はありません。 **/codebase** オプションと共に指定する *assemblyFile* 引数は、[厳密な名前付きのアセンブリ](../../../docs/framework/app-domains/strong-named-assemblies.md)である必要があります。|  
|**/registered**|このツールが既に登録されているタイプ ライブラリだけを参照するように指定します。|  
|**/asmpath:directory**|アセンブリ参照を含むディレクトリを指定します。 **/regfile** オプションと共に使用する必要があります。|  
|**/nologo**|Microsoft 著作権情報を表示しません。|  
|**/regfile** [**:** *regFile*]|アセンブリについて指定した .reg ファイルを生成します。このファイルには必要なレジストリ エントリが含まれます。 このオプションを指定してもレジストリは変更されません。 このオプションは **/u** または **/tlb** オプションとは併用できません。|  
|**/silent** または **/s**|成功メッセージを表示しません。|  
|**/tlb** [**:** *typeLibFile*]|指定したアセンブリからタイプ ライブラリを生成します。このアセンブリには、アセンブリ内で定義されたアクセス可能な型の定義が含まれます。|  
|**/unregister** または **/u**|*assemblyFile* 内で見つかった、作成可能なクラスの登録を取り消します。 このオプションを省略すると、アセンブリ内の作成可能なクラスが Regasm.exe で登録されます。|  
|**/verbose**|詳細出力モードを指定します。**/tlb** オプションと共に指定した場合、タイプ ライブラリを生成する必要のある参照先アセンブリの一覧が表示されます。|  
|**/?** または **/help**|このツールのコマンド構文とオプションを表示します。|  
  
> [!NOTE]
>  Regasm.exe のコマンド行オプションでは大文字と小文字が区別されません。 オプションの一部を指定するだけで一意に識別できます。 たとえば、**/n** は **/nologo** と等価であり、**/t:** *outfile.tlb* は **/tlb:** *outfile.tlb* と等価です。  
  
## <a name="remarks"></a>コメント  
 **/regfile** オプションを使用すると、直接にレジストリを変更しなくても、レジストリ エントリを含む .reg ファイルを生成できます。 コンピューターのレジストリを更新するには、レジストリ エディター ツール (Regedit.exe) を使用して .reg ファイルをインポートします。 .reg ファイルには、ユーザー定義の登録機能で行われるレジストリの更新についての情報は含まれません。  **/regfile** オプションは、マネージ クラスのレジストリ エントリだけを生成します。  このオプションは、`TypeLibID` と `InterfaceID` のエントリは生成しません。  
  
 **/tlb** オプションを指定すると、アセンブリ内で見つかった型を記述するタイプ ライブラリが Regasm.exe で生成および登録されます。 生成されたタイプ ライブラリは、現在の作業ディレクトリ、または出力ファイル用に指定されたディレクトリ内に格納されます。 他のアセンブリを参照するアセンブリについてタイプ ライブラリを生成すると、一度に複数のタイプ ライブラリが生成されることがあります。 タイプ ライブラリを使用して、[!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)] などの開発用ツールに対して型情報を提供できます。 登録するアセンブリがタイプ ライブラリ インポーター ([Tlbimp.exe](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md)) で生成されたアセンブリである場合には、**/tlb** オプションを使用しないでください。 タイプ ライブラリからインポートされたアセンブリからは、タイプ ライブラリをエクスポートできません。 **/tlb** オプションを使用した場合の効果は、タイプ ライブラリ エクスポーター ([Tlbexp.exe](../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md)) と Regasm.exe を使用した場合と同じです。ただし、Tlbexp.exe では、生成されたタイプ ライブラリが登録されません。  **/tlb** オプションを使用してタイプ ライブラリを登録する場合、**/tlb** オプションと **/unregister** オプションを使用してタイプ ライブラリの登録を解除できます。 この 2 つのオプションを使用すると、タイプ ライブラリとインターフェイス エントリの登録を解除でき、これによって、レジストリをかなり整理できます。  
  
 COM で使用するためにアセンブリを登録すると、Regasm.exe は、ローカル コンピューターのレジストリにエントリを追加します。 より具体的には、バージョンに依存するレジストリ キーを作成して、同じアセンブリの複数のバージョンが同じコンピューターで side-by-side 実行できるようにします。 アセンブリが初めて登録される場合は、そのアセンブリの最上位キーが 1 つ作成され、特定のバージョンに対する一意なサブキーが作成されます。 アセンブリの新しいバージョンを登録するたびに、Regasm.exe は、新しいバージョンに対するサブキーを作成します。  
  
 たとえば、COM で使用するために、マネージ コンポーネント myComp.dll のバージョン 1.0.0.0 を登録しているとします。 その後、myComp.dll バージョン 2.0.0.0 を登録します。 コンピューター上のすべての COM クライアント アプリケーションは myComp.dll バージョン 2.0.0.0 を使用しているため、myComponent.dll バージョン 1.0.0.0 を登録解除することにしました。 このレジストリ スキームでは、myComp.dll バージョン 1.0.0.0 のサブキーだけが削除されるため、バージョン 1.0.0.0 を登録解除できます。  
  
 Regasm.exe を使用してアセンブリを登録した後で、そのアセンブリを[グローバル アセンブリ キャッシュ](../../../docs/framework/app-domains/gac.md)内に登録すると、どの COM クライアントからもアクティブにできます。 アセンブリをアクティブにするアプリケーションが 1 つだけの場合は、そのアプリケーションのディレクトリ内にアセンブリを格納できます。  
  
## <a name="examples"></a>使用例  
 `myTest.dll` に含まれるすべてのパブリック クラスを登録するコマンドを次に示します。  
  
```  
regasm myTest.dll  
```  
  
 ファイル `myTest.reg` を生成するコマンドを次に示します。このファイルには、必要なレジストリ エントリがすべて含まれます。 このコマンドを実行してもレジストリは更新されません。  
  
```  
regasm myTest.dll /regfile:myTest.reg  
```  
  
 `myTest.dll` に含まれるすべてのパブリック クラスを登録し、タイプ ライブラリ `myTest.tlb` を生成および登録するコマンドを次に示します。このタイプ ライブラリには、`myTest.dll` で定義されたすべてのパブリック型の定義が含まれます。  
  
```  
regasm myTest.dll /tlb:myTest.tlb  
```  
  
## <a name="see-also"></a>参照  
 [ツール](../../../docs/framework/tools/index.md)  
 [Tlbexp.exe (タイプ ライブラリ エクスポーター)](../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md)  
 [Tlbimp.exe (タイプ ライブラリ インポーター)](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md)  
 [COM へのアセンブリの登録](../../../docs/framework/interop/registering-assemblies-with-com.md)  
 [Visual Studio 用開発者コマンド プロンプト](../../../docs/framework/tools/developer-command-prompt-for-vs.md)
