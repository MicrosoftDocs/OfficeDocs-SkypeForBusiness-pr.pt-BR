---
title: tblEnumValue
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: a33df20c-d19d-4f5c-b012-29dab8fb9200
description: A tabela tblEnumValue é uma tabela embutida em código que contém os valores de Visibilidade e Comportamento dos atributos usados na tabela Nó.
ms.openlocfilehash: 0854b20316f0200e2521109880cad32862524c22
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58619697"
---
# <a name="tblenumvalue"></a>tblEnumValue
 
A tabela tblEnumValue é uma tabela embutida em código que contém os valores de Visibilidade e Comportamento dos atributos usados na tabela Nó.
  
**Columns**

|**Coluna**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|
|valueID  <br/> |smallint, não nulo  <br/> |ID do valor.  <br/> |
|attributeID  <br/> |smallint, não nulo  <br/> |ID do atributo.  <br/> |
|attributeValue  <br/> |nvarchar (256), não nulo  <br/> |Nome do valor.  <br/> |
   
**Teclas**

|**Coluna**|**Descrição**|
|:-----|:-----|
|valueID  <br/> |Chave primária.  <br/> |
|attributeID  <br/> |Chave estrangeira com pesquisa na tabela tblEnumAttribute.attributeID.  <br/> |
   
**Valores da tabela**

|**valueID**|**attributeID**|**attributeValue**|
|:-----|:-----|:-----|
|2  <br/> |1  <br/> |private  <br/> |
|3   <br/> |1  <br/> |scope  <br/> |
|4   <br/> |2  <br/> |normal  <br/> |
|5   <br/> |2  <br/> |auditório  <br/> |
|6   <br/> |1  <br/> |open  <br/> |
   
## <a name="see-also"></a>Confira também

[tblNode](tblnode.md)
