---
title: tblSiopWhiteList
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 05fc1df4-32eb-4d46-9d1c-e0b607091142
description: A tabela SiopWhiteList é a lista de suplementos registrados que podem ser associados aos nós.
ms.openlocfilehash: 7a84170ccf79e3cb84c876a1bc1828c4eabf4e78
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60743097"
---
# <a name="tblsiopwhitelist"></a>tblSiopWhiteList
 
A tabela SiopWhiteList é a lista de suplementos registrados que podem ser associados aos nós.
  
**Columns**

|**Coluna**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|
|siopID  <br/> |GUID, não nulo  <br/> |GUID do suplemento.  <br/> |
|siopName  <br/> |nvarchar (50), não nulo  <br/> |Nome de exibição do suplemento.  <br/> |
|siopUrl  <br/> |nvarchar (255), não nulo  <br/> |URL do suplemento.  <br/> |
   
**Chave**

|**Coluna**|**Descrição**|
|:-----|:-----|
|siopID  <br/> |Chave primária.  <br/> |
   

