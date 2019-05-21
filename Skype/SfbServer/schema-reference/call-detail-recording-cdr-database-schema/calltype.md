---
title: Tabela CallType no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a1d7187c-f851-4967-88ea-73922911ee7a
description: A tabela CallType é uma tabela estática que armazena a lista de possíveis tipos de chamadas.
ms.openlocfilehash: 992e5682aedf7a0b9063960992197970146c8cfc
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296557"
---
# <a name="calltype-table-in-skype-for-business-server-2015"></a>Tabela CallType no Skype for Business Server 2015
 
A tabela CallType é uma tabela estática que armazena a lista de possíveis tipos de chamadas.
  
|**Coluna**|**Tipo de dados**|**Chave/índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**Callid** <br/> |int  <br/> |Primária  <br/> ||
|**CallType** <br/> |nvarchar  <br/> || Valores permitidos: <br/>  0--desconhecido <br/>  1-mensagens instantâneas <br/>  2 – compartilhamento de aplicativos <br/>  3--áudio <br/>  4-áudio e vídeo <br/>  Transferência de 5 arquivos <br/> |
   

