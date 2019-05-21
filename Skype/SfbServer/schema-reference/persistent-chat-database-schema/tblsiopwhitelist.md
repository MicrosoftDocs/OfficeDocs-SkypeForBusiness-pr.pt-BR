---
title: tblSiopWhiteList
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 05fc1df4-32eb-4d46-9d1c-e0b607091142
description: tblSiopWhiteList é a lista de suplementos registrados que podem ser associados a nós.
ms.openlocfilehash: 3277ec3a2d4fe11000b2eda60fa2327547c77d2b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295171"
---
# <a name="tblsiopwhitelist"></a>tblSiopWhiteList
 
tblSiopWhiteList é a lista de suplementos registrados que podem ser associados a nós.
  
**Colunas**

|**Coluna**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|
|siopID  <br/> |GUID, não nulo  <br/> |GUID do suplemento.  <br/> |
|siopName  <br/> |nvarchar (50), NOT NULL  <br/> |Display-nome do suplemento.  <br/> |
|siopUrl  <br/> |nvarchar (255), NOT NULL  <br/> |URL do suplemento.  <br/> |
   
**Chave**

|**Coluna**|**Descrição**|
|:-----|:-----|
|siopID  <br/> |Chave primária.  <br/> |
   

