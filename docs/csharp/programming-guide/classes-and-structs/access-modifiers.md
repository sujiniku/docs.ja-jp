---
title: アクセス修飾子 (C# プログラミング ガイド)
ms.date: 07/20/2015
helpviewer_keywords:
- C# Language, access modifiers
- access modifiers [C#], about
ms.assetid: 6e81ee82-224f-4a12-9baf-a0dca2656c5b
ms.openlocfilehash: ec275d4782fee047b16fd114c4d22ceb03eecb11
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33314110"
---
# <a name="access-modifiers-c-programming-guide"></a>アクセス修飾子 (C# プログラミング ガイド)
すべての型とそのメンバーには、アクセシビリティ レベルがあります。同じアセンブリ (または他のアセンブリ) にある他のコードからそれらの型やそのメンバーを利用できるかどうかは、アクセシビリティ レベルによって制御されます。 型またはメンバーにはその宣言時に、以下のアクセス修飾子を使ってアクセシビリティを指定できます。  
  
 [public](../../../csharp/language-reference/keywords/public.md)  
 この型またはメンバーには、同じアセンブリ内の他のコードや、そのアセンブリを参照する別のアセンブリ内の任意のコードからアクセスできます。 
  
 [private](../../../csharp/language-reference/keywords/private.md)  
 この型またはメンバーには、同じクラス内または同じ構造体内のコードからのみアクセスできます。  
  
 [protected](../../../csharp/language-reference/keywords/protected.md)  
 この型またはメンバーには、同じクラス内のコードか、そのクラスから派生したクラス内のコードからのみアクセスできます。  
 [internal](../../../csharp/language-reference/keywords/internal.md)  
 この型またはメンバーには、同じアセンブリ内の任意のコードからアクセスできますが、別のアセンブリからはアクセスできません。  
  
 [protected internal](../../../csharp/language-reference/keywords/protected-internal.md) この型またはメンバーには、それが宣言されているアセンブリ内の任意のコードからアクセスできるほか、別のアセンブリの派生クラス内からアクセスすることができます。 

 [private protected](../../../csharp/language-reference/keywords/private-protected.md) この型またはメンバーには、同じクラスのコードか、そのクラスから派生した型のコードによって、その宣言アセンブリ内でのみ、アクセスできます。
  
 次の例は、型とメンバーにアクセス修飾子を指定する方法を示しています。  
  
 [!code-csharp[csProgGuideObjects#72](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/access-modifiers_1.cs)]  
  
 コンテキストに関係なくすべての型またはすべてのメンバーにどのようなアクセス修飾子でも使用できるというわけではありません。型のメンバーのアクセシビリティが、それを含んでいる型のアクセシビリティによって制約を受ける場合もあります。 以降のセクションでは、アクセシビリティについてさらに詳しく取り上げます。  
  
## <a name="class-and-struct-accessibility"></a>クラスと構造体のアクセシビリティ  
 名前空間に直接宣言されている (つまり、他のクラスや構造体の入れ子にされていない) クラスと構造体には、public または internal を指定することができます。 アクセス修飾子が指定されなかった場合は、既定で internal が適用されます。  
  
 構造体のメンバー (入れ子にされているクラスや構造体も含む) は public、internal、private のいずれかとして宣言することができます。 クラスのメンバー (入れ子にされているクラスや構造体も含む) は public、protected internal、protected、internal、private protected、private のいずれかとして宣言することができます。 クラスのメンバーと構造体のメンバー (入れ子にされているクラスや構造体も含む) には、既定で private のアクセス レベルが指定されます。 入れ子にされた型のうち、private が指定されているものには、それを含んでいる型の外部からはアクセスできません。  
  
 派生クラスに、その基本型を超えるアクセシビリティを割り当てることはできません。 つまり、internal クラス `A` から派生したクラス `B` を public にすることはできません。 仮にそれが許容されるならば、`A` が public になると考えられます。`A` のすべての protected メンバーと internal メンバーに派生クラスからアクセスできることになるからです。  
  
 InternalsVisibleToAttribute を使うと、internal 型へのアクセスを他の特定のアセンブリに許可することができます。 詳細については、[Friend アセンブリ](http://msdn.microsoft.com/library/df0c70ea-2c2a-4bdc-9526-df951ad2d055)に関するページを参照してください。  
  
## <a name="class-and-struct-member-accessibility"></a>クラスと構造体のメンバーのアクセシビリティ  
 クラスのメンバー (入れ子にされているクラスや構造体も含む) は、6 種類あるアクセス修飾子をどれでも使って宣言できます。 構造体のメンバーを protected として宣言することはできません。構造体は継承をサポートしていないためです。  
  
 通常、メンバーのアクセシビリティが、それを含んでいる型のアクセシビリティを超えることはありません。 ただし、internal クラスの public メンバーには、そのアセンブリの外部からアクセスできる場合もあります。そのメンバーがインターフェイスのメソッドを実装している場合や public な基本クラスに定義されている仮想メソッドをオーバーライドしている場合がそれに該当します。  
  
 フィールド、プロパティ、イベントのいずれかに該当するメンバーの型には、メンバー自体と同じかそれ以上のアクセシビリティが必要です。 同様に、メソッド、インデクサー、デリゲートのいずれかに該当するメンバーの戻り値の型とパラメーターの型には、メンバー自体と同じかそれ以上のアクセシビリティが必要です。 たとえば、クラス `C` を返すメソッド `M` を public にするためには、`C` も public である必要があります。 同様に、`A` が private として宣言されている場合、`A` 型のプロパティを protected にすることはできません。  
  
 ユーザー定義の演算子は、必ず public として宣言する必要があります。 詳細については、「[operator (C# Reference) (operator (C# リファレンス))](../../../csharp/language-reference/keywords/operator.md)」を参照してください。  
  
 アクセシビリティ修飾子をファイナライザーに割り当てることはできません。  
  
 クラスまたは構造体のメンバーにアクセス レベルを設定するには、該当するキーワードをメンバーの宣言に追加します。その例を次に示します。  
  
 [!code-csharp[csProgGuideObjects#73](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/access-modifiers_2.cs)]  
  
> [!NOTE]
>  protected internal のアクセシビリティ レベルは、"protected AND internal" ではなく "protected OR internal" という意味になります。 つまり、protected internal のメンバーには、同じアセンブリ内の任意のクラス (派生クラスも含む) からアクセスすることができます。 同じアセンブリ内の派生クラスのみにアクセシビリティを限定するには、クラス自体は internal として宣言し、そのメンバーを protected として宣言します。 また、C# 7.2 以降、外側のクラスを internal にしなくても、private protected アクセス修飾子を利用して同じ結果を得ることができます。  
  
## <a name="other-types"></a>その他の型  
 名前空間内に直接宣言されたインターフェイスは、public または internal として宣言できます。クラスや構造体と同様、インターフェイスの既定のアクセス レベルは internal になります。 インターフェイスのメンバーは常に public です。他の型がクラスや構造体にアクセスできるようにすることがインターフェイスの目的であるためです。 インターフェイスのメンバーにアクセス修飾子を適用することはできません。  
  
 列挙型のメンバーは常に public となり、アクセス修飾子を適用することはできません。  
  
 デリゲートの振る舞いは、クラスおよび構造体と似ています。 既定では、名前空間内に直接宣言されているときには internal アクセスが、入れ子にされているときは private アクセスが適用されます。  
  
## <a name="c-language-specification"></a>C# 言語仕様  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>参照  
 [C# プログラミング ガイド](../../../csharp/programming-guide/index.md)  
 [クラスと構造体](../../../csharp/programming-guide/classes-and-structs/index.md)  
 [インターフェイス](../../../csharp/programming-guide/interfaces/index.md)  
 [private](../../../csharp/language-reference/keywords/private.md)  
 [public](../../../csharp/language-reference/keywords/public.md)  
 [internal](../../../csharp/language-reference/keywords/internal.md)  
 [protected](../../../csharp/language-reference/keywords/protected.md)  
 [protected internal](../../../csharp/language-reference/keywords/protected-internal.md)  
 [private protected](../../../csharp/language-reference/keywords/private-protected.md)  
 [class](../../../csharp/language-reference/keywords/class.md)  
 [struct](../../../csharp/language-reference/keywords/struct.md)  
 [interface](../../../csharp/language-reference/keywords/interface.md)
