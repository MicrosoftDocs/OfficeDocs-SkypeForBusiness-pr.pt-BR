---
title: Tabela CallType Skype para Business Server 2015
ms.reviewer: ''
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
ms.openlocfilehash: 29e5ed85de5917092ad00cd0e1aa60fec1a31b22
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213358"
---
# <a name="calltype-table-in-skype-for-business-server-2015"></a>Tabela CallType Skype para Business Server 2015
 
A tabela CallType é uma tabela estática que armazena a lista de possíveis tipos de chamada.
  
|**Coluna**|**Tipo de dados**|**Chave/índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**CallTypeId** <br/> |int  <br/> |Primária  <br/> ||
|**CallType** <br/> |nvarchar  <br/> || Valores permitidos: <br/>  0--desconhecido <br/>  1 - instant Messaging <br/>  2-- Compartilhamento de aplicativos <br/>  3-- áudio <br/>  4 - áudio e vídeo <br/>  5 - arquivo transferência <br/> |
   

