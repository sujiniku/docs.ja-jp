---
title: ジェネリック コレクションに対するインターフェイスでの分散の使用 (C#)
ms.date: 07/20/2015
ms.assetid: a44f0708-10fa-4c76-82cd-daa6e6b31e8e
ms.openlocfilehash: 7f1c44ecc831a7eb35541a432bc776c512bd10a3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33340464"
---
# <a name="using-variance-in-interfaces-for-generic-collections-c"></a>ジェネリック コレクションに対するインターフェイスでの分散の使用 (C#)
共変のインターフェイスのメソッドでは、そのインターフェイスで指定された型よりも強い派生型を返すことができます。 反変のインターフェイスのメソッドでは、そのインターフェイスで指定された型よりも弱い派生型のパラメーターを受け取ることができます。  
  
 .NET Framework 4 では、既存のいくつかのインターフェイスが共変および反変になります。 その中には、<xref:System.Collections.Generic.IEnumerable%601> や <xref:System.IComparable%601> があります。 これにより、派生型のコレクションに対して、基本型のジェネリック コレクションを操作するメソッドを再利用できます。  
  
 .NET Framework のバリアント インターフェイスの一覧については、「[Variance in Generic Interfaces (C#)](../../../../csharp/programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md)」 (ジェネリック インターフェイスの分散 (C#)) を参照してください。  
  
## <a name="converting-generic-collections"></a>ジェネリック コレクションの変換  
 次の例は、<xref:System.Collections.Generic.IEnumerable%601> インターフェイスにおける共変性のサポートの利点を示しています。 `PrintFullName` メソッドは、パラメーターとして `IEnumerable<Person>` 型のコレクションを受け取ります。 ただし、`Employee` は `Person` を継承しているため、`IEnumerable<Employee>` 型のコレクションで再利用できます。  
  
```csharp  
// Simple hierarchy of classes.  
public class Person  
{  
    public string FirstName { get; set; }  
    public string LastName { get; set; }  
}  
  
public class Employee : Person { }  
  
class Program  
{  
    // The method has a parameter of the IEnumerable<Person> type.  
    public static void PrintFullName(IEnumerable<Person> persons)  
    {  
        foreach (Person person in persons)  
        {  
            Console.WriteLine("Name: {0} {1}",  
            person.FirstName, person.LastName);  
        }  
    }  
  
    public static void Test()  
    {  
        IEnumerable<Employee> employees = new List<Employee>();  
  
        // You can pass IEnumerable<Employee>,   
        // although the method expects IEnumerable<Person>.  
  
        PrintFullName(employees);  
  
    }  
}  
```  
  
## <a name="comparing-generic-collections"></a>ジェネリック コレクションの比較  
 次の例は、<xref:System.Collections.Generic.IComparer%601> インターフェイスにおける反変性のサポートの利点を示しています。 `PersonComparer` クラスは、`IComparer<Person>` インターフェイスを実装します。 ただし、`Employee` は `Person` を継承しているため、`Employee` 型の一連のオブジェクトを比較するためにこのクラスを再利用できます。  
  
```csharp  
// Simple hierarchy of classes.  
public class Person  
{  
    public string FirstName { get; set; }  
    public string LastName { get; set; }  
}  
  
public class Employee : Person { }  
  
// The custom comparer for the Person type  
// with standard implementations of Equals()  
// and GetHashCode() methods.  
class PersonComparer : IEqualityComparer<Person>  
{  
    public bool Equals(Person x, Person y)  
    {              
        if (Object.ReferenceEquals(x, y)) return true;  
        if (Object.ReferenceEquals(x, null) ||  
            Object.ReferenceEquals(y, null))  
            return false;              
        return x.FirstName == y.FirstName && x.LastName == y.LastName;  
    }  
    public int GetHashCode(Person person)  
    {  
        if (Object.ReferenceEquals(person, null)) return 0;  
        int hashFirstName = person.FirstName == null  
            ? 0 : person.FirstName.GetHashCode();  
        int hashLastName = person.LastName.GetHashCode();  
        return hashFirstName ^ hashLastName;  
    }  
}  
  
class Program  
{  
  
    public static void Test()  
    {  
        List<Employee> employees = new List<Employee> {  
               new Employee() {FirstName = "Michael", LastName = "Alexander"},  
               new Employee() {FirstName = "Jeff", LastName = "Price"}  
            };  
  
        // You can pass PersonComparer,   
        // which implements IEqualityComparer<Person>,  
        // although the method expects IEqualityComparer<Employee>.  
  
        IEnumerable<Employee> noduplicates =  
            employees.Distinct<Employee>(new PersonComparer());  
  
        foreach (var employee in noduplicates)  
            Console.WriteLine(employee.FirstName + " " + employee.LastName);  
    }  
}  
```  
  
## <a name="see-also"></a>参照  
 [ジェネリック インターフェイスの分散 (C#)](../../../../csharp/programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md)
