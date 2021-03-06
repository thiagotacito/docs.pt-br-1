---
title: "Classes static e membros de classes static (Guia de Programação em C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- C# language, static members
- static members [C#]
- static classes [C#]
- C# language, static classes
- static class members [C#]
ms.assetid: 235614b5-1371-4dbd-9abd-b406a8b0298b
caps.latest.revision: 49
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 63f46f9ae35b3c699744f7bf61cad3b08b796509
ms.contentlocale: pt-br
ms.lasthandoff: 07/28/2017

---
# <a name="static-classes-and-static-class-members-c-programming-guide"></a>Classes static e membros de classes static (Guia de Programação em C#)
Uma classe [static](../../../csharp/language-reference/keywords/static.md) é basicamente o mesmo que uma classe não estática, mas há uma diferença: uma classe estática não pode ser instanciada. Em outras palavras, você não pode usar a palavra-chave [new](../../../csharp/language-reference/keywords/new.md) para criar uma variável do tipo de classe. Como não há nenhuma variável de instância, você acessa os membros de uma classe estática usando o próprio nome de classe. Por exemplo, se você tiver uma classe estática denominada `UtilityClass` que tem um método público chamado `MethodA`, chame o método, conforme mostrado no exemplo a seguir:  
  
```csharp  
UtilityClass.MethodA();  
```  
  
 Uma classe estática pode ser usada como um contêiner conveniente para conjuntos de métodos que operam apenas em parâmetros de entrada e não precisam obter ou definir campos de instância internos. Por exemplo, na biblioteca de classes .NET Framework, a classe estática <xref:System.Math?displayProperty=fullName> contém métodos que executam operações matemáticas, sem a necessidade de armazenar ou recuperar dados que são exclusivos de uma determinada instância da classe <xref:System.Math>. Ou seja, você aplica os membros da classe especificando o nome de classe e o nome do método, conforme mostrado no exemplo a seguir.  
  
```csharp  
double dub = -3.14;  
Console.WriteLine(Math.Abs(dub));  
Console.WriteLine(Math.Floor(dub));  
Console.WriteLine(Math.Round(Math.Abs(dub)));  
  
// Output:  
// 3.14  
// -4  
// 3  
```  
  
 Como é o caso com todos os tipos de classe, as informações de tipo de uma classe estática são carregadas pelo CLR (Common Language Runtime) [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] quando o programa que faz referência à classe é carregado. O programa não pode especificar exatamente quando a classe é carregada. No entanto, é garantido que ela será carregada e terá seus campos inicializados e seu construtor estático chamado antes que a classe seja referenciada pela primeira vez em seu programa. Um construtor estático é chamado apenas uma vez e uma classe estática permanece na memória pelo tempo de vida do domínio do aplicativo em que seu programa reside.  
  
> [!NOTE]
>  Para criar uma classe não estática que permite que apenas uma instância de si mesma seja criada, consulte [Implementando singleton no C#](http://go.microsoft.com/fwlink/?LinkID=100567).  
  
 A lista a seguir fornece os principais recursos de uma classe estática:  
  
-   Contém apenas membros estáticos.  
  
-   Não pode ser instanciada.  
  
-   É lacrada.  
  
-   Não pode conter [Construtores de instância](../../../csharp/programming-guide/classes-and-structs/instance-constructors.md).  
  
 Criar uma classe estática é, portanto, basicamente o mesmo que criar uma classe que contém apenas membros estáticos e um construtor particular. Um construtor particular impede que a classe seja instanciada. A vantagem de usar uma classe estática é que o compilador pode verificar se nenhum membro de instância foi adicionado acidentalmente. O compilador garantirá que as instâncias dessa classe não possam ser criadas.  
  
 Classes estáticas são lacradas e, portanto, não podem ser herdadas. Elas não podem herdar de qualquer classe, exceto por <xref:System.Object>. Classes estáticas não podem conter um construtor de instância. No entanto, elas podem conter um construtor estático. Classes não estáticas também devem definir um construtor estático se a classe contiver membros estáticos que exigem inicialização não trivial. Para obter mais informações, consulte [Construtores estáticos](../../../csharp/programming-guide/classes-and-structs/static-constructors.md).  
  
## <a name="example"></a>Exemplo  
 Temos aqui um exemplo de uma classe estática que contém dois métodos que convertem a temperatura de Celsius em Fahrenheit e de Fahrenheit em Celsius:  
  
 [!code-cs[csProgGuideObjects#31](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/static-classes-and-static-class-members_1.cs)]  
  
## <a name="static-members"></a>Membros Estáticos  
 Uma classe não estática pode conter métodos, campos, propriedades ou eventos estáticos. O membro estático pode ser chamado em uma classe, mesmo quando nenhuma instância da classe foi criada. O membro estático sempre é acessado pelo nome de classe, não pelo nome da instância. Existe apenas uma cópia de um membro estático, independentemente de quantas instâncias da classe forem criadas. Propriedades e métodos estáticos não podem acessar eventos e campos não estáticos no tipo que os contêm e não podem acessar uma variável de instância de nenhum objeto, a menos que ele seja passado explicitamente em um parâmetro de método.  
  
 É mais comum declarar uma classe não estática com alguns membros estáticos do que declarar uma classe inteira como estática. Dois usos comuns dos campos estáticos são manter uma contagem do número de objetos que foram instanciados ou armazenar um valor que deve ser compartilhado entre todas as instâncias.  
  
 Métodos estáticos podem ser sobrecarregados, mas não substituídos, porque pertencem à classe e não a qualquer instância da classe.  
  
 Embora um campo não possa ser declarado como `static const`, um campo [const](../../../csharp/language-reference/keywords/const.md) é essencialmente estático em seu comportamento. Ele pertence ao tipo e não a instâncias do tipo. Portanto, campos constantes podem ser acessados usando a mesma notação `ClassName.MemberName` usada para campos estáticos. Nenhuma instância de objeto é necessária.  
  
 O C# não dá suporte a variáveis locais estáticas (variáveis que são declaradas no escopo do método).  
  
 Você declara membros de classe estática usando a palavra-chave `static` antes do tipo de retorno do membro, conforme mostrado no exemplo a seguir:  
  
 [!code-cs[csProgGuideObjects#29](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/static-classes-and-static-class-members_2.cs)]  
  
 Membros estáticos são inicializados antes que o membro estático seja acessado pela primeira vez e antes que o construtor estático, se houver, seja chamado. Para acessar um membro de classe estática, use o nome da classe em vez de um nome de variável para especificar o local do membro, conforme mostrado no exemplo a seguir:  
  
 [!code-cs[csProgGuideObjects#30](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/static-classes-and-static-class-members_3.cs)]  
  
 Se sua classe contiver campos estáticos, forneça um construtor estático que os inicializa quando a classe é carregada.  
  
 Uma chamada para um método estático gera uma instrução de chamada em MSIL (Microsoft Intermediate Language), enquanto uma chamada para um método de instância gera uma instrução `callvirt`, que também verifica se há referências de objeto nulas. No entanto, na maioria das vezes, a diferença de desempenho entre os dois não é significativa.  
  
## <a name="c-language-specification"></a>Especificação da Linguagem C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Consulte também  
 [Guia de Programação em C#](../../../csharp/programming-guide/index.md)   
 [static](../../../csharp/language-reference/keywords/static.md)   
 [Classes](../../../csharp/programming-guide/classes-and-structs/classes.md)   
 [class](../../../csharp/language-reference/keywords/class.md)   
 [Construtores estáticos](../../../csharp/programming-guide/classes-and-structs/static-constructors.md)   
 [Construtores de instância](../../../csharp/programming-guide/classes-and-structs/instance-constructors.md)

