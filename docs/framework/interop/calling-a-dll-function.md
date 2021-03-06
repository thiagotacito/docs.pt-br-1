---
title: "Chamando uma função de DLL"
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
- unmanaged functions, calling
- unmanaged functions
- COM interop, platform invoke
- platform invoke, calling unmanaged functions
- interoperation with unmanaged code, platform invoke
- DLL functions
ms.assetid: 113646de-7ea0-4f0e-8df0-c46dab3e8733
caps.latest.revision: 12
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: b676599513b923ae46d6ec27d7506435d9cbfcd2
ms.contentlocale: pt-br
ms.lasthandoff: 08/21/2017

---
# <a name="calling-a-dll-function"></a>Chamando uma função de DLL
Embora a chamada a funções de DLL não gerenciadas seja quase idêntica à chamada de outro código gerenciado, há diferenças que podem fazer com que as funções de DLL pareçam confusas a princípio. Esta seção apresenta tópicos que descrevem alguns dos problemas incomuns relacionados a chamadas.  
  
 Estruturas retornadas de chamadas de invocação de plataforma devem ser tipos de dados que têm a mesma representação em um código gerenciado e não gerenciado. Esses tipos são chamados de *tipos blittable* porque não exigem conversão (consulte [Tipos blittable e não blittable](../../../docs/framework/interop/blittable-and-non-blittable-types.md)). Para chamar uma função que tem uma estrutura não blittable como seu tipo de retorno, é possível definir um tipo de auxiliar blittable do mesmo tamanho do tipo não blittable e converter os dados depois que a função é retornada.  
  
## <a name="in-this-section"></a>Nesta seção  
 [Passando estruturas](../../../docs/framework/interop/passing-structures.md)  
 Identifica os problemas de passar estruturas de dados com um layout predefinido.  
  
 [Funções de retorno de chamada](../../../docs/framework/interop/callback-functions.md)  
 Fornece informações básicas sobre as funções de retorno de chamada.  
  
 [Como implementar funções de retorno de chamada](../../../docs/framework/interop/how-to-implement-callback-functions.md)  
 Descreve como implementar funções de retorno de chamada em um código gerenciado.  
  
## <a name="related-sections"></a>Seções relacionadas  
 [Consumindo funções de DLL não gerenciadas](../../../docs/framework/interop/consuming-unmanaged-dll-functions.md)  
 Descreve como chamar funções de DLL não gerenciadas usando a invocação de plataforma.  
  
 [Marshaling de dados com a invocação de plataforma](../../../docs/framework/interop/marshaling-data-with-platform-invoke.md)  
 Descreve como declarar parâmetros de método e passar argumentos para funções exportadas por bibliotecas não gerenciadas.

