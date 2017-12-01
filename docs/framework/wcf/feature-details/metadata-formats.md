---
title: Formatos de metadados
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: baad1e68-28fc-4a6a-8a43-75e47e7fa871
caps.latest.revision: "12"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: d250b57282d24780dcdd1e045f18d7528bd86a90
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="metadata-formats"></a>Formatos de metadados
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]oferece suporte os formatos de metadados na tabela a seguir.  
  
## <a name="metadata-specifications-and-usage"></a>Especificações de metadados e de uso  
  
|Protocolo|Especificação e uso|  
|--------------|-----------------------------|  
|WSDL 1.1|[Web Services Description Language (WSDL) 1.1](http://go.microsoft.com/fwlink/?LinkId=94859)<br /><br /> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]usa o WSDL Web Services Description Language () para descrever serviços.|  
|esquema XML|[Esquema XML parte 2: Edição de segundo de tipos de dados](http://go.microsoft.com/fwlink/?LinkId=94861) e [esquema XML parte 1: estruturas segunda edição](http://go.microsoft.com/fwlink/?LinkId=94862)<br /><br /> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]usa o esquema XML para descrever tipos de dados usados em mensagens.|  
|Política de WS|[Política de serviços Web 1.2 - Framework (WS-Policy)](http://go.microsoft.com/fwlink/?LinkId=94864)<br /><br /> [Política de serviços Web 1.5 - estrutura](http://go.microsoft.com/fwlink/?LinkId=94865)<br /><br /> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]usa o WS-Policy 1.2 ou 1,5 especificações com declarações específicas de domínio para descrever os recursos e requisitos de serviço.|  
|Anexos de política WS|[Política de serviços Web 1.2 - anexo (mecanismo WS-PolicyAttachment)](http://go.microsoft.com/fwlink/?LinkId=94866)<br /><br /> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]implementa o WS-Policy anexos para anexar a expressões de política em vários escopos em WSDL.|  
|Troca de metadados de WS|[Troca de metadados de serviços da Web (WS-MetadataExchange) versão 1.1](http://go.microsoft.com/fwlink/?LinkId=94868)<br /><br /> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]implementa o WS-MetadataExchange para recuperar o esquema XML, WSDL e WS-Policy.|  
|WS endereçamento de associação para WSDL|[Associação de WSDL 1.0 - endereçamento de serviços Web](http://go.microsoft.com/fwlink/?LinkId=94869)<br /><br /> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]implementa o WS-Addressing associação WSDL anexar informações de endereçamento em WSDL.|  
  
## <a name="see-also"></a>Consulte também  
 [Protocolos com suporte por associações de interoperabilidade fornecidas pelo sistema de serviços Web](../../../../docs/framework/wcf/feature-details/web-services-protocols-supported-by-system-provided-interoperability-bindings.md)  
 [WSDL e política](../../../../docs/framework/wcf/feature-details/wsdl-and-policy.md)