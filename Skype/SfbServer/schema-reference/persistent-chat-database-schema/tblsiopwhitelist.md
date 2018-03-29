---
title: tabela Siopwhitelist
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 05fc1df4-32eb-4d46-9d1c-e0b607091142
description: a tabela Siopwhitelist é a lista de suplementos registrados que podem ser associados a nós.
ms.openlocfilehash: 0653ec7f4a663479f7b7d4787eee4dc0a1045aac
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="tblsiopwhitelist"></a>tabela Siopwhitelist
 
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
   

