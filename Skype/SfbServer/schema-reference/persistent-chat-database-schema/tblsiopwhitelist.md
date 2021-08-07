---
title: tblSiopWhiteList
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
ms.assetid: 05fc1df4-32eb-4d46-9d1c-e0b607091142
description: A tabela SiopWhiteList é a lista de suplementos registrados que podem ser associados aos nós.
ms.openlocfilehash: 3f1ad0461bc227970d4a2a0864dbc6318ef0af32d854402180321bab74aa91e5
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54305373"
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
   

