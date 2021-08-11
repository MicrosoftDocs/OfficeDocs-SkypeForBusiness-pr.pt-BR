---
title: tblConfig
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
ms.assetid: 7445e7db-c574-46fa-b964-8640d77047a8
description: tblConfig contém algumas configurações sem suporte do Servidor de Chat Persistente, em uma linha.
ms.openlocfilehash: 0e9cc0a0c4686432032591aa0c380b303fc5251a56a6c983a1e10b009e0eb28a
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54278349"
---
# <a name="tblconfig"></a>tblConfig
 
tblConfig contém algumas configurações sem suporte do Servidor de Chat Persistente, em uma linha.
  
**Columns**

|**Coluna**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|
|configLabel  <br/> |nvarchar (255), não nulo  <br/> |Contém "pool."  <br/> |
|configContent  <br/> |nvarchar (máx.)  <br/> |Conteúdo de configuração.  <br/> |
|configPoolID  <br/> |GUID, não nulo  <br/> |ID exclusivo da instância de banco de dados.  <br/> |
   
**Chave**

|**Coluna**|**Descrição**|
|:-----|:-----|
|configLabel  <br/> |Chave primária.  <br/> |
   

