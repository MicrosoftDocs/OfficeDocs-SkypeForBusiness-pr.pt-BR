---
title: tblEnumAttribute
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 17f8b87e-36a6-4f6a-8630-7c76b61a7595
description: tblEnumAttribute é uma tabela embutida em código que contém os atributos de visibilidade e comportamento usados na tabela Node.
ms.openlocfilehash: b81e8ae09561220df381290eed212ef752820edd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929949"
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
   
## <a name="see-also"></a>Confira também

[tblNode](tblnode.md)
