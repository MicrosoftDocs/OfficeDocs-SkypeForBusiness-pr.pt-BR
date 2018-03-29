---
title: tblEnumAttribute
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 17f8b87e-36a6-4f6a-8630-7c76b61a7595
description: tblEnumAttribute é uma tabela embutida em código que contém os atributos de visibilidade e comportamento usados na tabela Node.
ms.openlocfilehash: 24208b56aba586af500a2f659a2d5cbf1a47234d
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="tblenumattribute"></a>tblEnumAttribute
 
tblEnumAttribute é uma tabela embutida em código que contém os atributos de visibilidade e comportamento usados na tabela Node.
  
**Colunas**

|**Coluna**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|
|attributeID  <br/> |smallint, não nulo  <br/> |ID do atributo.  <br/> |
|attributeName  <br/> |nvarchar (256), não nulo  <br/> |Nome do atributo.  <br/> |
   
**Chave**

|**Coluna**|**Descrição**|
|:-----|:-----|
|attributeID  <br/> |Chave primária.  <br/> |
   
**Valores da tabela**

|**attributeID**|**attributeName**|
|:-----|:-----|
|1  <br/> |Visibilidade.  <br/> |
|2  <br/> |Comportamento.  <br/> |
   
## <a name="see-also"></a>Consulte também

#### 

[tblNode](tblnode.md)

