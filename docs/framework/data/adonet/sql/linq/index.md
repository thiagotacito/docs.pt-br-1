---
title: LINQ to SQL
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 73d13345-eece-471a-af40-4cc7a2f11655
caps.latest.revision: 4
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 3c6410d06565c9dcb9696d0fcb4f3fc749a19c48
ms.contentlocale: pt-br
ms.lasthandoff: 09/05/2017

---
# <a name="linq-to-sql"></a>LINQ to SQL
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] é um componente do [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)] versão 3.5 que fornece uma infraestrutura de tempo de execução para gerenciar dados relacionais como objetos.  
  
> [!NOTE]
>  Os dados relacionais aparecem como uma coleção de tabelas bidimensionais (*relações* ou *arquivos simples*), em que as colunas comuns relacionam as tabelas entre si. Para usar o [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] efetivamente, você deve ter alguma familiaridade com os conceitos fundamentais de bancos de dados relacionais.  
  
 No [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], o modelo de dados de um banco de dados relacional é mapeado para um modelo de objeto expresso na linguagem de programação do desenvolvedor. Quando o aplicativo é executado, o [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] converte em SQL as consultas integradas à linguagem no modelo de objeto e as envia ao banco de dados para execução. Quando o banco de dados retorna os resultados, o [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] converte-os novamente em objetos com os quais você pode trabalhar em sua própria linguagem de programação.  
  
 Os desenvolvedores que usam o [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] normalmente usam o [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)], que fornece uma interface do usuário para implementar muitos dos recursos do [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].  
  
 A documentação incluída nessa versão do [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] descreve as técnicas, os processos e os blocos de construção básicos necessários para compilar aplicativos [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]. Você também pode pesquisar assuntos específicos na Biblioteca MSDN e participar do [Fórum da LINQ](http://go.microsoft.com/fwlink/?LinkId=76488), no qual poderá discutir tópicos mais complexos detalhadamente com especialistas. Por fim, o white paper [LINQ to SQL: .NET Language-Integrated Query for Relational Data](http://go.microsoft.com/fwlink/?LinkId=93205) (LINQ to SQL: consulta integrada à linguagem do .NET para dados relacionais) fornece informações detalhadas sobre a tecnologia [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], com exemplos de código C# e do [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)].  
  
## <a name="in-this-section"></a>Nesta seção  
 [Introdução](../../../../../../docs/framework/data/adonet/sql/linq/getting-started.md)  
 Fornece uma visão concentrada do [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] juntamente com informações sobre como começar a usar o [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].  
  
 [Guia de Programação](../../../../../../docs/framework/data/adonet/sql/linq/programming-guide.md)  
 Fornece etapas para operações de mapeamento, atualização, depuração e tarefas semelhantes.  
  
 [Referência](../../../../../../docs/framework/data/adonet/sql/linq/reference.md)  
 Especifica informações de referência sobre vários aspectos do [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]. Os tópicos incluem o mapeamento de tipos SQL-CLR, conversão padrão de operadores de consulta e muito mais.  
  
 [Amostras](../../../../../../docs/framework/data/adonet/sql/linq/samples.md)  
 Fornece links para exemplos de [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] e C#.  
  
## <a name="related-sections"></a>Seções relacionadas  
 [LINQ (Consulta Integrada à Linguagem)](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d)  
 Apresenta uma visão geral das tecnologias [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)].  
  
 [LINQ](../../../../../visual-basic/programming-guide/language-features/linq/index.md)  
 Descreve as tecnologias [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] para usuários de [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)].  
  
 [LINQ to ADO.NET](http://msdn.microsoft.com/en-us/be3297b9-1b54-4d4c-82a8-add0d79c2006)  
 Links para o portal do [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)].  
  
 [LINQ to SQL Walkthroughs](http://msdn.microsoft.com/en-us/308e66ac-f704-4e00-9b4e-7af0045a2374) (Passo a passo do LINQ to SQL)  
 Lista tutoriais disponíveis para o [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].  
  
 [Downloading Sample Databases](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md) (Baixando bancos de dados de amostra)  
 Descreve como baixar bancos de dados de exemplo usados na documentação.  
  
 [Visão geral da tecnologia LinqDataSource](http://msdn.microsoft.com/en-us/104cfc3f-7385-47d3-8a51-830dfa791136)  
 Descreve como o controle <xref:System.Web.UI.WebControls.LinqDataSource> expõe o [!INCLUDE[vbteclinqext](../../../../../../includes/vbteclinqext-md.md)] para desenvolvedores Web por meio da arquitetura de controle de fonte de dados [!INCLUDE[vstecasp](../../../../../../includes/vstecasp-md.md)].

