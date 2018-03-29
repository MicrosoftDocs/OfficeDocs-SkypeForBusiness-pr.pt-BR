---
title: Tabela CallType Skype para Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a1d7187c-f851-4967-88ea-73922911ee7a
description: A tabela CallType é uma tabela estática que armazena a lista de possíveis tipos de chamada.
ms.openlocfilehash: e2353176a69db9eada137525561541d26caa7a8e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="calltype-table-in-skype-for-business-server-2015"></a>Tabela CallType Skype para Business Server 2015
 
A tabela CallType é uma tabela estática que armazena a lista de possíveis tipos de chamada.
  
|**Coluna**|**Tipo de dados**|**Índice de chaves /**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**CallTypeId** <br/> |int  <br/> |Primária  <br/> ||
|**CallType** <br/> |nvarchar  <br/> || Valores permitidos: <br/>  0--desconhecido <br/>  1 - instant Messaging <br/>  2-- Compartilhamento de aplicativos <br/>  3-- áudio <br/>  4 - áudio e vídeo <br/>  5 - arquivo transferência <br/> |
   

