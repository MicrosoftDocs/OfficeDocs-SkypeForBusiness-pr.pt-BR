---
title: tblEnumAttribute
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 17f8b87e-36a6-4f6a-8630-7c76b61a7595
description: tblEnumAttribute é uma tabela embutida em código que inclui os atributos de Visibilidade e Comportamento usados na tabela Node.
ms.openlocfilehash: a2d2fa1eacac79784e20f137a037d672fa9eaa87
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60856438"
---
# <a name="tblenumattribute"></a>tblEnumAttribute
 
tblEnumAttribute é uma tabela embutida em código que inclui os atributos de Visibilidade e Comportamento usados na tabela Node.
  
**Columns**

|**Coluna**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|
|attributeID  <br/> |smallint, não nulo  <br/> |ID do atributo.  <br/> |
|attributeName  <br/> |nvarchar (256), não nulo  <br/> |Nome do atributo.  <br/> |
   
**Chave**

|**Coluna**|**Descrição**|
|:-----|:-----|
|attributeID  <br/> |Chave primária.  <br/> |
   
**Valores de Tablea**

|**attributeID**|**attributeName**|
|:-----|:-----|
|1  <br/> |Visibilidade.  <br/> |
|2  <br/> |Comportamento.  <br/> |
   
## <a name="see-also"></a>Confira também

[tblNode](tblnode.md)
