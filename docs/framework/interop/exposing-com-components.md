---
title: Expondo componentes do COM para o .NET Framework
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- exposing COM components to .NET Framework
- interoperation with unmanaged code, exposing COM components
- COM interop, exposing COM components
ms.assetid: e78b14f1-e487-43cd-9c6d-1a07483f1730
caps.latest.revision: 11
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: c0fcf7bec289d64b1faceef00b01278fa45caab0
ms.contentlocale: pt-br
ms.lasthandoff: 08/21/2017

---
# <a name="exposing-com-components-to-the-net-framework"></a>Expondo componentes do COM para o .NET Framework
Esta seção resume o processo necessário para expor um componente COM existente ao código gerenciado. Para obter detalhes sobre como escrever servidores COM que são totalmente integrados ao .NET Framework, consulte [Considerações sobre design para interoperação](http://msdn.microsoft.com/en-us/b59637f6-fe35-40d6-ae72-901e7a707689).  
  
 Os componentes COM existentes são recursos valiosos no código gerenciado, como aplicativos de negócios de camada intermediária ou como uma funcionalidade isolada. Um componente ideal tem um assembly de interoperabilidade primário e está em conformidade total com os padrões de programação impostos pelo COM.  
  
#### <a name="to-expose-com-components-to-the-net-framework"></a>Para expor componentes COM ao .NET Framework  
  
1.  [Importe uma biblioteca de tipos como um assembly](../../../docs/framework/interop/importing-a-type-library-as-an-assembly.md).  
  
     O Common Language Runtime exige metadados para todos os tipos, incluindo tipos COM. Há várias maneiras de obter um assembly que contém tipos COM importados como metadados.  
  
2.  [Crie tipos COM em um código gerenciado](http://msdn.microsoft.com/en-us/1a95a8ca-c8b8-4464-90b0-5ee1a1135b66).  
  
     É possível inspecionar tipos COM, ativar instâncias e invocar métodos no objeto COM da mesma maneira que você faria com qualquer tipo gerenciado.  
  
3.  [Compile um projeto de interoperabilidade](../../../docs/framework/interop/compiling-an-interop-project.md).  
  
     O [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] fornece compiladores para várias linguagens em conformidade com CLS (Common Language Specification), incluindo [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)], C# e C++.  
  
4.  [Implante um aplicativo de interoperabilidade](../../../docs/framework/interop/deploying-an-interop-application.md).  
  
     Os aplicativos de interoperabilidade são mais bem implantados como assemblies assinados [de nome forte](../../../docs/framework/app-domains/strong-named-assemblies.md) no cache de assembly global.  
  
## <a name="see-also"></a>Consulte também  
 [Interoperação com código não gerenciado](../../../docs/framework/interop/index.md)   
 [Considerações sobre design para interoperação](http://msdn.microsoft.com/en-us/b59637f6-fe35-40d6-ae72-901e7a707689)   
 [Amostra de interoperabilidade COM: cliente .NET e servidor COM](../../../docs/framework/interop/com-interop-sample-net-client-and-com-server.md)   
 [Independência de linguagem e componentes independentes de linguagem](../../../docs/standard/language-independence-and-language-independent-components.md)   
 [Gacutil.exe (Ferramenta Cache de Assembly Global)](../../../docs/framework/tools/gacutil-exe-gac-tool.md)

