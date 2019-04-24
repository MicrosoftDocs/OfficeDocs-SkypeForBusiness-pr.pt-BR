---
title: tblEnumValue
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a33df20c-d19d-4f5c-b012-29dab8fb9200
description: a tabela tblEnumValue é uma tabela embutida em código que contém os valores de visibilidade e comportamento dos atributos que são usados na tabela Node.
ms.openlocfilehash: 579b2747ea753b8a701d11dd806178427cbb27b3
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212877"
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
