---
title: tblConfig
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7445e7db-c574-46fa-b964-8640d77047a8
description: tblConfig contém algumas configuração não suportada do servidor de Chat persistente, em uma linha.
ms.openlocfilehash: 9d28c0506b905975e2a72eeb83605fe4e32e7cfd
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30898934"
---
# <a name="tblconfig"></a>tblConfig
 
tblConfig contém algumas configuração não suportada do servidor de Chat persistente, em uma linha.
  
**Colunas**

|**Coluna**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|
|configLabel  <br/> |nvarchar (255), não nulo  <br/> |Contém "pool".  <br/> |
|configContent  <br/> |nvarchar (máx.)  <br/> |Conteúdo da configuração.  <br/> |
|configPoolID  <br/> |GUID, não nulo  <br/> |ID exclusiva da instância do banco de dados.  <br/> |
   
**Chave**

|**Coluna**|**Descrição**|
|:-----|:-----|
|configLabel  <br/> |Chave primária.  <br/> |
   

