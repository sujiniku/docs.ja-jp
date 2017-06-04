---
title: "UI Automation Support for the MenuBar Control Type | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-bcl"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "UI Automation, Menu Bar control type"
  - "control types, Menu Bar"
  - "Menu Bar control type"
ms.assetid: c1202b21-c1f0-4560-853c-7b99bd73ad97
caps.latest.revision: 22
author: "Xansky"
ms.author: "mhopkins"
manager: "markl"
caps.handback.revision: 22
---
# UI Automation Support for the MenuBar Control Type
> [!NOTE]
>  このドキュメントは、[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 名前空間で定義されているマネージ <xref:System.Windows.Automation> クラスを使用する .NET Framework 開発者を対象としています。[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] の最新情報については、「[Windows Automation API: UI オートメーション](http://go.microsoft.com/fwlink/?LinkID=156746)」を参照してください。  
  
 このトピックでは、<xref:System.Windows.Automation.ControlType.MenuBar> コントロール型の [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] サポートについて説明します。[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] でのコントロール型とは、コントロールが <xref:System.Windows.Automation.AutomationElement.ControlTypeProperty> プロパティを使用するために満たす必要がある一連の条件のことです。 条件には、[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] ツリー構造、[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] プロパティの値、およびコントロール パターンに関する特定のガイドラインが含まれます。  
  
 MenuBar コントロール型を実装するコントロールの例には、メニュー バー コントロールがあります。 メニュー バーは、ユーザーがアプリケーションに含まれるコマンドおよびオプションをアクティブにするための手段を提供します。  
  
 以降のセクションで、MenuBar コントロール型に必要な [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] ツリー構造、プロパティ、コントロール パターン、およびイベントを定義します。[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 要件は、[!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)]、[!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)]、または [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)] のいずれの場合も、すべてのリスト コントロールに適用されます。  
  
<a name="Required_UI_Automation_Tree_Structure"></a>   
## 必須の UI オートメーション ツリー構造  
 次の表に、コントロール ビューと、メニュー バー コントロールに関連する [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] ツリーのコンテンツ ビューを示し、それぞれのビューに含めることができる内容について説明します。[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] ツリーの詳細については、「[UI Automation Tree Overview](../../../docs/framework/ui-automation/ui-automation-tree-overview.md)」を参照してください。  
  
|コントロール ビュー|コンテンツ ビュー|  
|----------------|---------------|  
|メニュー バー<br /><br /> -   MenuItem \(1 個以上\)<br />-   その他のコントロール \(0 個以上\)|メニュー バー<br /><br /> -   MenuItem \(1 個以上\)<br />-   その他のコントロール \(0 個以上\)|  
  
 メニュー バー コントロールの構造には、エディット コントロールやコンボ ボックスなどの他のコントロールを含めることができます。 これらの追加コントロールは、コントロール ビューおよびコンテンツ ビューに含まれる、上記に一覧した「その他のコントロール」に対応します。  
  
<a name="Required_UI_Automation_Properties"></a>   
## 必須の UI オートメーション プロパティ  
 次の表に、メニュー バー コントロールに特に関連する値または定義を持つ [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] プロパティを示します。[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] プロパティの詳細については、「[UI Automation Properties for Clients](../../../docs/framework/ui-automation/ui-automation-properties-for-clients.md)」を参照してください。  
  
|[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] プロパティ|値|ノート|  
|---------------------------------------------------------------------------------|-------|---------|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty>|「ノート」を参照。|このプロパティで公開する値には、メニュー バー コントロールに含まれるすべてのコントロールを含める必要があります。|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.NameProperty>|「ノート」を参照。|アプリケーションに複数のメニュー バーがある場合を除き、メニュー バー コントロールに名前は必要ありません。 アプリケーションに複数のメニュー バーがある場合、このプロパティを使用して、「書式設定」や「アウトライン」といった識別名を公開する必要があります|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LabeledByProperty>|`Null`|メニュー バー コントロールには例外なく、ラベルはありません。|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ControlTypeProperty>|メニュー バー|この値は、すべての UI フレームワークで同じです。|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LocalizedControlTypeProperty>|「メニュー バー」|MenuBar コントロール型に対応する、ローカライズされた文字列。|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsContentElementProperty>|True|メニュー バー コントロールは、常に [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] ツリーのコンテンツ ビューに組み込まれます。|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsControlElementProperty>|True|メニュー バー コントロールは、常に [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] ツリーのコントロール ビューに組み込まれます。|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsOffscreenProperty>|「ノート」を参照。|このプロパティの値は、コントロールを画面に表示できるかどうかによって異なります。|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.OrientationProperty>|状況に依存|このプロパティは、メニュー バー コントロールが水平または垂直のいずれかであるかを公開します。|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsKeyboardFocusableProperty>|True|メニュー バー コントロールに含まれるコントロールはキーボード フォーカスを受け取ることができるため、メニュー バー コントロールはキーボード フォーカスを受け取ることができます。|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.HelpTextProperty>|「ノート」を参照。|メニュー バー コントロールにヘルプ テキストが必要になるシナリオはありません。|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AcceleratorKeyProperty>|`Null`|メニュー バーでアクセラレータ キーを使用することは決してありません。|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AccessKeyProperty>|「ALT」|ALT キーを押すと常に、アプリケーション内のメニュー バーにフォーカスが移動します。|  
  
<a name="Required_UI_Automation_Control_Patterns"></a>   
## 必須の UI オートメーション コントロール パターン  
 次の表に、メニュー バー コントロールでサポートされなければならない [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] コントロール パターンを示します。 コントロール パターンの詳細については、「[UI Automation Control Patterns Overview](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)」を参照してください。  
  
|コントロール パターン|Support|ノート|  
|-----------------|-------------|---------|  
|<xref:System.Windows.Automation.Provider.IExpandCollapseProvider>|状況に依存|コントロールを展開または折りたたむことができる場合は、<xref:System.Windows.Automation.Provider.IExpandCollapseProvider> を実装します。|  
|<xref:System.Windows.Automation.Provider.IDockProvider>|状況に依存|コントロールを画面のさまざまな部分にドッキングできる場合は、<xref:System.Windows.Automation.Provider.IDockProvider> を実装します。|  
|<xref:System.Windows.Automation.Provider.ITransformProvider>|状況に依存|コントロールのサイズ変更、回転、移動が可能な場合は、<xref:System.Windows.Automation.Provider.ITransformProvider> を実装する必要があります。|  
  
<a name="Required_UI_Automation_Events"></a>   
## 必須の UI オートメーション イベント  
 次の表に、すべてのメニュー バー コントロールでサポートされなければならない [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] イベントを示します。 イベントの詳細については、「[UI Automation Events Overview](../../../docs/framework/ui-automation/ui-automation-events-overview.md)」を参照してください。  
  
|[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] イベント|サポート\/値|ノート|  
|--------------------------------------------------------------------------------|-------------|---------|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty> プロパティ変更イベント。|必須|なし|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsOffscreenProperty> プロパティ変更イベント。|必須|なし|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsEnabledProperty> プロパティ変更イベント。|必須|なし|  
|<xref:System.Windows.Automation.ExpandCollapsePatternIdentifiers.ExpandCollapseStateProperty> プロパティ変更イベント。|状況に依存|なし|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationFocusChangedEvent>|必要|なし|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.StructureChangedEvent>|必要|なし|  
  
## 参照  
 <xref:System.Windows.Automation.ControlType.MenuBar>   
 [UI Automation Control Types Overview](../../../docs/framework/ui-automation/ui-automation-control-types-overview.md)   
 [UI Automation Overview](../../../docs/framework/ui-automation/ui-automation-overview.md)