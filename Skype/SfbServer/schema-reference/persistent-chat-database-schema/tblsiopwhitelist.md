---
title: tblSiopWhiteList
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 05fc1df4-32eb-4d46-9d1c-e0b607091142
description: a tabela Siopwhitelist é a lista de suplementos registrados que podem ser associados a nós.
ms.openlocfilehash: f3389f3d4a956e00180303c09bd3eb264d786b9b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33924770"
---
# <a name="tblsiopwhitelist"></a>tblSiopWhiteList
 
a tabela Siopwhitelist é a lista de suplementos registrados que podem ser associados a nós.
  
**Colunas**

|**Coluna**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|
|siopID  <br/> |GUID, não nulo  <br/> |GUID do suplemento.  <br/> |
|siopName  <br/> |nvarchar (50), não nulo  <br/> |Nome de exibição do add-in.  <br/> |
|siopUrl  <br/> |nvarchar (255), não nulo  <br/> |URL do add-in.  <br/> |
   
**Chave**

|**Coluna**|**Descrição**|
|:-----|:-----|
|siopID  <br/> |Chave primária.  <br/> |
   

