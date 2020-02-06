---
title: tblEnumValue
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: a33df20c-d19d-4f5c-b012-29dab8fb9200
description: tblEnumValue é uma tabela codificada que contém os valores de visibilidade e comportamento dos atributos usados na tabela de nós.
ms.openlocfilehash: accb9cb4801984bd4b3839cd44e5b7feb8d06baa
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814599"
---
# <a name="tblenumvalue"></a>tblEnumValue
 
tblEnumValue é uma tabela codificada que contém os valores de visibilidade e comportamento dos atributos usados na tabela de nós.
  
**Colunas**

|**Coluna**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|
|valueid  <br/> |smallint, não nulo  <br/> |ID do valor.  <br/> |
|attributeID  <br/> |smallint, não nulo  <br/> |ID do atributo.  <br/> |
|atributovalue  <br/> |nvarchar (256), NOT NULL  <br/> |Nome do valor.  <br/> |
   
**As**

|**Coluna**|**Descrição**|
|:-----|:-----|
|valueid  <br/> |Chave primária.  <br/> |
|attributeID  <br/> |Chave estrangeira com pesquisa na tabela tblEnumAttribute. attributeID.  <br/> |
   
**Valores da tabela**

|**valueid**|**attributeID**|**atributovalue**|
|:-----|:-----|:-----|
|2  <br/> |1  <br/> |private  <br/> |
|3  <br/> |1  <br/> |com  <br/> |
|4  <br/> |2  <br/> |Normalmente  <br/> |
|5  <br/> |2  <br/> |auditorium  <br/> |
|6  <br/> |1  <br/> |abriu  <br/> |
   
## <a name="see-also"></a>Confira também

[tblNode](tblnode.md)
