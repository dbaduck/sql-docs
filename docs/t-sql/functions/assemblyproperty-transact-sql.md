---
title: "ASSEMBLYPROPERTY (Transact-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "07/24/2017"
ms.prod: "sql-non-specified"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "database-engine"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "ASSEMBLYPROPERTY_TSQL"
  - "ASSEMBLYPROPERTY"
dev_langs: 
  - "TSQL"
helpviewer_keywords: 
  - "ASSEMBLYPROPERTY statement"
  - "assemblies [CLR integration], properties"
ms.assetid: cf03d1b1-724c-48bf-a8df-3fe2586b150a
caps.latest.revision: 40
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
---
# ASSEMBLYPROPERTY (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx_md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

Returns information about a property of an assembly.
  
![Topic link icon](../../database-engine/configure-windows/media/topic-link.gif "Topic link icon") [Transact-SQL Syntax Conventions](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)
  
## Syntax  
  
```sql
ASSEMBLYPROPERTY('assembly_name', 'property_name')  
```  
  
## Arguments  
*assembly_name*  
Is the name of the assembly.
  
*property_name*  
Is the name of a property about which to retrieve information. *property_name* can be one of the following values.
  
|Value|Description|  
|---|---|
|**CultureInfo**|Locale of the assembly.|  
|**PublicKey**|Public key or public key token of the assembly.|  
|**MvID**|Complete, compiler-generated version identification number of the assembly.|  
|**VersionMajor**|Major component (first part) of the four-part version identification number of the assembly.|  
|**VersionMinor**|Minor component (second part) of the four-part version identification number of the assembly.|  
|**VersionBuild**|Build component (third part) of the four-part version identification number of the assembly.|  
|**VersionRevision**|Revision component (fourth part) of the four-part version identification number of the assembly.|  
|**SimpleName**|Simple name of the assembly.|  
|**Architecture**|Processor architecture of the assembly.|  
|**CLRName**|Canonical string that encodes the simple name, version number, culture, public key, and architecture of the assembly. This value uniquely identifies the assembly on the common language runtime (CLR) side.|  
  
## Return type
**sql_variant**
  
## Examples  
The following example assumes a `HelloWorld` assembly is registered in the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database. For more information, see [Hello World Sample](http://msdn.microsoft.com/library/fed6c358-f5ee-4d4c-9ad6-089778383ba7).
  
```sql
USE AdventureWorks2012;  
GO  
SELECT ASSEMBLYPROPERTY ('HelloWorld' , 'PublicKey');  
```  
  
## See also
[CREATE ASSEMBLY &#40;Transact-SQL&#41;](../../t-sql/statements/create-assembly-transact-sql.md)  
[DROP ASSEMBLY &#40;Transact-SQL&#41;](../../t-sql/statements/drop-assembly-transact-sql.md)
  
  