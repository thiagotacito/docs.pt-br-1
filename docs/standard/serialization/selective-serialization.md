---
title: "Serialização seletiva"
ms.date: 08/07/2017
ms.prod: .net
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- serialization, selective serialization
- binary serialization, selective serialization
ms.assetid: 39c56635-95d2-4afd-aff1-b022e7649bb3
caps.latest.revision: 6
author: Erikre
ms.author: erikre
manager: erikre
ms.translationtype: HT
ms.sourcegitcommit: 717bcb6f9f72a728d77e2847096ea558a9c50902
ms.openlocfilehash: 5cf437604f3072f3dec7b15897fcf5b6788289f0
ms.contentlocale: pt-br
ms.lasthandoff: 08/21/2017

---
# <a name="selective-serialization"></a>Serialização seletiva
Uma classe geralmente contém os campos que não devem ser serializados. Por exemplo, presuma que uma classe armazene uma ID de thread em uma variável de membro. Quando a classe é desserializada, o thread que armazenou a ID de quando a classe foi serializada pode não estar mais em execução; portanto, serializar esse valor não faz sentido. Você pode impedir que variáveis de membros sejam serializadas marcando-as com o atributo [NonSerialized](xref:System.NonSerializedAttribute) da maneira a seguir.  
  
```csharp  
[Serializable]  
public class MyObject   
{  
  public int n1;  
  [NonSerialized] public int n2;  
  public String str;  
}  
```

Se possível, crie um objeto que possa conter dados confidenciais de segurança não serializáveis. Se o objeto tiver que ser serializado, aplique o atributo `NonSerialized` em campos específicos que armazenam dados confidenciais. Se você não excluir esses campos da serialização, esteja ciente de que os dados que eles armazenam serão expostos em qualquer código que tenha permissão para serializar. Para obter mais informações sobre como escrever um código de serialização segura, consulte [Segurança e serialização](../../../docs/framework/misc/security-and-serialization.md).

[!INCLUDE [binary-serialization-warning](../../../includes/binary-serialization-warning.md)]
  
## <a name="see-also"></a>Consulte também  
 [Serialização Binária](binary-serialization.md)   
 [Serialização XML e SOAP](xml-and-soap-serialization.md)   
 [Segurança e serialização](../../../docs/framework/misc/security-and-serialization.md)
