---
title: Tabela EdgeServers no Skype para Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aeda8c01-c88c-4f56-b3d0-bac475fae449
description: A tabela EdgeServers é uma tabela de suporte. Cada registro armazena informações sobre um servidor de borda que está envolvido em chamadas que têm registros no banco de dados.
ms.openlocfilehash: a55a72f9a98dda0295256803a7f9318116ecf969
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901049"
---
# <a name="edgeservers-table-in-skype-for-business-server-2015"></a>Tabela EdgeServers no Skype para Business Server 2015
 
A tabela EdgeServers é uma tabela de suporte. Cada registro armazena informações sobre um servidor de borda que está envolvido em chamadas que têm registros no banco de dados.
  
|**Coluna**|**Tipo de dados**|**Chave/índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**EdgeServerId** <br/> |int  <br/> |Primária  <br/> |Número exclusivo que identifica este servidor de borda.  <br/> |
|**EdgeServer** <br/> |nvarchar(256)  <br/> | <br/> |Nome do servidor de borda.  <br/> |
   

