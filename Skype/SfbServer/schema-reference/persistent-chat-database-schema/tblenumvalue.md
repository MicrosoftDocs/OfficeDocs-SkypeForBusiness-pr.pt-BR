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
localization_priority: Normal
ms.assetid: a33df20c-d19d-4f5c-b012-29dab8fb9200
description: A tabela tblEnumValue é uma tabela embutida em código que contém os valores de Visibilidade e Comportamento dos atributos usados na tabela Nó.
ms.openlocfilehash: a13bfbe79d1eb118f0727f390816a26d35a508d0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816021"
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
|2   <br/> |1   <br/> |private  <br/> |
|3   <br/> |1   <br/> |escopo  <br/> |
|4   <br/> |2   <br/> |normal  <br/> |
|5   <br/> |2   <br/> |auditório  <br/> |
|6   <br/> |1   <br/> |abrir  <br/> |
   
## <a name="see-also"></a>Confira também

[tblNode](tblnode.md)
