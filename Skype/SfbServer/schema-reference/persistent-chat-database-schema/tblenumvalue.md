---
title: tblEnumValue
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a33df20c-d19d-4f5c-b012-29dab8fb9200
description: a tabela tblEnumValue é uma tabela embutida em código que contém os valores de visibilidade e comportamento dos atributos que são usados na tabela Node.
ms.openlocfilehash: 00ee5a7a7538fa620e438ead5e986f859ef25a6c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929865"
---
# <a name="tblenumvalue"></a>tblEnumValue
 
a tabela tblEnumValue é uma tabela embutida em código que contém os valores de visibilidade e comportamento dos atributos que são usados na tabela Node.
  
**Colunas**

|**Coluna**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|
|valueID  <br/> |smallint, não nulo  <br/> |ID do valor.  <br/> |
|attributeID  <br/> |smallint, não nulo  <br/> |ID do atributo.  <br/> |
|valor de atributo  <br/> |nvarchar (256), não nulo  <br/> |Nome do valor.  <br/> |
   
**Chaves**

|**Coluna**|**Descrição**|
|:-----|:-----|
|valueID  <br/> |Chave primária.  <br/> |
|attributeID  <br/> |Chave estrangeira com pesquisa na tabela Tblenumattribute.  <br/> |
   
**Valores da tabela**

|**valueID**|**attributeID**|**valor de atributo**|
|:-----|:-----|:-----|
|2  <br/> |1  <br/> |private  <br/> |
|3  <br/> |1  <br/> |escopo  <br/> |
|4  <br/> |2  <br/> |normal  <br/> |
|5  <br/> |2  <br/> |auditório  <br/> |
|6  <br/> |1  <br/> |Abrir  <br/> |
   
## <a name="see-also"></a>Confira também

[tblNode](tblnode.md)
