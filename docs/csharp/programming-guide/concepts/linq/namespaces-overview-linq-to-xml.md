---
title: "Visão geral sobre namespaces (LINQ to XML)"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 16283322-8238-4918-ab11-802ac6748eb7
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: dfa9e65bcf5a3c0e37bb1a44caab889468c5c236
ms.contentlocale: pt-br
ms.lasthandoff: 07/28/2017

---
# <a name="namespaces-overview-linq-to-xml"></a>Visão geral sobre namespaces (LINQ to XML)
Este tópico apresenta namespaces, a classe <xref:System.Xml.Linq.XName> e a classe <xref:System.Xml.Linq.XNamespace>.  
  
## <a name="xml-names"></a>Nomes XML  
 Os nomes XML são geralmente uma fonte de complexidade na programação XML. Um nome de XML consiste em um namespace XML (também chamado um URI de um namespace XML) e um nome local. Um namespace XML é semelhante a um namespace em um programa baseadas em [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]. Permite que você determine exclusivamente os nomes de elementos e atributos. Isso ajuda a evitar conflitos de nome entre várias partes de um documento XML. Quando você declarar um namespace de XML, poderá selecionar um nome local que somente deve ser exclusivo dentro desse namespace.  
  
 Outro aspecto de nomes XML são os *prefixos de namespace* de XML. Os prefixos XML causam a maioria da complexidade de nomes XML. Esses prefixos permite que você crie um atalho para um namespace XML, que faz o documento XML mais concisas e legível. No entanto, os prefixos XML depende do seu contexto para ter significado, que adiciona a complexidade. Por exemplo, o prefixo `aw` XML pode ser associado com a um namespace XML de uma parte de uma árvore XML, e com um outro namespace XML em uma parte diferente da árvore XML.  
  
 Uma das vantagens de usar [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] com C# é que você não precisa usar prefixos XML. Quando o [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] carrega ou analisa um documento XML, cada prefixo XML é resolvido para o namespace de XML correspondente. Após isso, quando você trabalha com um documento que usar namespaces, você acessa quase sempre namespaces com o URI de namespace, e não com o prefixo de namespace. Quando os desenvolvedores trabalham com nomes XML em [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] sempre trabalham com um nome XML totalmente qualificado (isto é, um namespace de XML e um nome local). No entanto, quando necessário, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] permite que você trabalhe com controle e prefixos de namespace.  
  
 Em [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], a classe que representa nomes XML é <xref:System.Xml.Linq.XName>. Os nomes XML aparecem com frequência em toda a API [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] e, em qualquer lugar em que um nome XML for necessário, você encontrará um parâmetro <xref:System.Xml.Linq.XName>. No entanto, raramente você trabalha diretamente com um <xref:System.Xml.Linq.XName>. <xref:System.Xml.Linq.XName> contém uma conversão implícita de cadeia de caracteres.  
  
 Para obter mais informações, consulte <xref:System.Xml.Linq.XNamespace> e <xref:System.Xml.Linq.XName>.  
  
## <a name="see-also"></a>Consulte também  
 [Trabalhando com namespaces XML (C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md)

