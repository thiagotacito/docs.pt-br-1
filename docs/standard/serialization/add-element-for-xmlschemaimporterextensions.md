---
title: Elemento &lt;add&gt; de &lt;xmlSchemaImporterExtensions&gt;
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- XML serialization, configuration
- <add> element for <xmlSchemaImporterExtensions> element
ms.assetid: c828a558-094b-441e-9065-790b87315fa0
caps.latest.revision: 3
author: Erikre
ms.author: erikre
manager: erikre
ms.translationtype: HT
ms.sourcegitcommit: 717bcb6f9f72a728d77e2847096ea558a9c50902
ms.openlocfilehash: 859e348359ed35e971baff8611fa4f676808f5a7
ms.contentlocale: pt-br
ms.lasthandoff: 08/21/2017

---
# <a name="ltaddgt-element-for-ltxmlschemaimporterextensionsgt"></a>Elemento &lt;add&gt; de &lt;xmlSchemaImporterExtensions&gt;
Adiciona tipos usados pelo <xref:System.Xml.Serialization.XmlSchemaImporter> para mapeamento de tipos XSD para tipos do .NET Framework. Para obter mais informações sobre arquivos de configuração, consulte [Esquema de arquivos de configuração](../../../docs/framework/configure-apps/file-schema/index.md).  
  
 \<configuration>  
\<system.xml.serialization>  
\<XmlSchemaImporterExtensions>  
\<add>  
  
## <a name="syntax"></a>Sintaxe  
  
```xml  
<add name = "typeName" type="fully qualified type [,Version=version number] [,Culture=culture] [,PublicKeyToken= token]"/>  
```  
  
## <a name="attributes-and-elements"></a>Atributos e elementos  
 As seções a seguir descrevem atributos, elementos filho e elementos pai.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descrição|  
|---------------|-----------------|  
|**name**|Um nome simples que é usado para localizar a instância.|  
|**type**|Necessário. Especifica a classe de extensão de esquema para adicionar. O valor de atributo **type** deve ser uma linha e incluir o nome do tipo totalmente qualificado. Quando o assembly é colocado no GAC (cache de assembly global), ele também deve incluir a versão, cultura e token de chave pública do assembly assinado.|  
  
### <a name="child-elements"></a>Elementos filho  
 nenhuma.  
  
### <a name="parent-elements"></a>Elementos pai  
  
|Elemento|Descrição|  
|-------------|-----------------|  
|\<xmlSchemaImporterExtensions>|Contém tipos que são usados pela <xref:System.Xml.Serialization.XmlSchemaImporter>.|  
  
## <a name="example"></a>Exemplo  
 O exemplo de código a seguir adiciona um tipo de extensão que o XmlSchemaImporter pode usar ao mapear tipos.  
  
```xml  
<configuration>  
  <system.xml.serialization>  
    <xmlSchemaImporterExtensions>  
       <add name="contoso" type="System.Web.Mobile.MobileCapabilities,   
       System.Web.Mobile, Version=2.0.0.0, Culture=neutral,   
       PublicKeyToken=b03f5f7f11d50a3a" />   
    </xmlSchemaImporterExtensions>  
  </system.xml.serialization>  
</configuration>  
```  
  
## <a name="see-also"></a>Consulte também  
 <xref:System.Xml.Serialization.XmlSchemaImporter>   
 Elemento [\<system.xml.serialization>](../../../docs/standard/serialization/system-xml-serialization-element.md)   
 Elemento [\<schemaImporterExtensions>](../../../docs/standard/serialization/schemaimporterextensions-element.md)

