---
title: FileName で指定されたファイルは、正しい XML ファイルではありません
ms.date: 07/20/2015
ms.assetid: c4c30bf3-e0ad-4bc8-89e0-2c3e49e9793b
ms.openlocfilehash: 3aecb0c2c87539717656a29f5b48f94fce3c8453
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33639189"
---
# <a name="file-specified-in-filename-is-not-a-valid-xml-file"></a>FileName で指定されたファイルは、正しい XML ファイルではありません
指定したファイル名は、正しい XML ファイルではありません。 XML ドキュメントの許可されている構造体とコンテンツを指定する場合、ドキュメント型定義 (DTD)、Microsoft XML-Data Reduced (XDR) スキーマ、または XML スキーマ定義言語 (XSD) スキーマを使用できます。 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]で XML 文法を指定する場合は、XSD スキーマをお勧めします。  
  
> [!NOTE]
>  Visual Studio の以前のバージョンにある **XML デザイナー** とは、型指定されたデータセットおよび XML スキーマのデザイナーのことです。 **XML デザイナー** は、XML スキーマ ファイルの作成と編集に今も使用できます。 ただし、 [!INCLUDE[vs_current_long](~/includes/vs-current-long-md.md)]では、型指定されたデータセットの作成と編集用のデザイナーは、 **データセット デザイナー**です。 詳細については、次を参照してください。[の作成と型指定されたデータセットの編集](/visualstudio/data-tools/creating-and-editing-typed-datasets)です。  
  
## <a name="to-correct-this-error"></a>このエラーを解決するには  
  
-   正しいファイル名を指定していることを確認します。  
  
-   確認する必要のある XML ファイルを **XML デザイナー**に読み込んで、指定したファイルに正しい XML が含まれていることを確認します。 **[XML]** メニューで、 **[XML の整合性チェック]** をクリックします。 エラーは **[タスク一覧]** に表示されます。  
  
-   XML ファイルに関連付けられた XML スキーマがある場合は、定義された構造体にその要素が出現し、個々の要素のコンテンツがスキーマで指定された宣言されたデータ型に準拠していることを確認します。  
  
## <a name="see-also"></a>関連項目  
 <xref:System.Xml>  
 [方法: ファイル パスを解析する](../../visual-basic/developing-apps/programming/drives-directories-files/how-to-parse-file-paths.md)
