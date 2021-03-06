---
title: '&lt;byteStreamMessageEncoding&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bbadd8dd-60a2-4007-b959-89373a8a7d60
caps.latest.revision: 4
author: Erikre
ms.author: erikre
manager: erikre
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: c0eaafec80dbd7aa9b32c89a2d73a0fc444fb0bf
ms.contentlocale: pt-br
ms.lasthandoff: 09/25/2017

---
# <a name="ltbytestreammessageencodinggt"></a>&lt;byteStreamMessageEncoding&gt;
Especifica a codificação de mensagens como um fluxo de bytes, com a opção para especificar a codificação de caracteres.  
  
 \<System. ServiceModel >  
\<associações >  
\<customBinding >  
\<associação >  
\<binaryMessageEncoding >  
  
## <a name="syntax"></a>Sintaxe  
  
```xml  
<byteStreamMessageEncoding/>  
```  
  
## <a name="attributes-and-elements"></a>Atributos e elementos  
 As seções a seguir descrevem atributos, elementos filho e elementos pai.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descrição|  
|---------------|-----------------|  
|messageVersion|Especifica a versão SOAP das mensagens enviadas usando a associação. Essa propriedade só pode ser definida para o valor da versão de mensagem <xref:System.ServiceModel.Channels.MessageVersion.None%2A>. O codificador de mensagens do fluxo de bytes não dá suporte a outras versões de mensagem.<br /><br /> Esse atributo é do tipo <xref:System.ServiceModel.Channels.MessageVersion>.|  
  
### <a name="child-elements"></a>Elementos filho  
  
|Elemento|Descrição|  
|-------------|-----------------|  
|[\<readerQuotas >](http://msdn.microsoft.com/library/3e5e42ff-cef8-478f-bf14-034449239bfd)|Define as restrições na complexidade de mensagens SOAP que podem ser processadas por pontos de extremidade configurados com essa associação. Esse elemento é do tipo <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.|  
  
### <a name="parent-elements"></a>Elementos pai  
  
|Elemento|Descrição|  
|-------------|-----------------|  
|[\<associação >](../../../../../docs/framework/misc/binding.md)|Define todos os recursos de associação da associação personalizada.|  
  
## <a name="see-also"></a>Consulte também  
 <xref:System.ServiceModel.Configuration.ByteStreamMessageEncodingElement>   
 <xref:System.ServiceModel.Channels.CustomBinding>   
 <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>   
 <xref:System.ServiceModel.Channels.ByteStreamMessageEncodingBindingElement>   
 [Codificação de mensagens](../../../../../docs/framework/configure-apps/file-schema/wcf/message-encoding.md)   
 [Escolhendo um codificador de mensagem](../../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)   
 [Associações](../../../../../docs/framework/wcf/bindings.md)   
 [Estendendo associações](../../../../../docs/framework/wcf/extending/extending-bindings.md)   
 [Associações personalizadas](../../../../../docs/framework/wcf/extending/custom-bindings.md)   
 [\<customBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)

