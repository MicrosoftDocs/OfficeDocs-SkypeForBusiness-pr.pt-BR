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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: a1d7187c-f851-4967-88ea-73922911ee7a
description: A tabela CallType é uma tabela estática que armazena a lista de possíveis tipos de chamadas.
ms.openlocfilehash: 294af58755e980200d75c899d6110322e2ff774d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815429"
---
# <a name="calltype-table-in-skype-for-business-server-2015"></a>Tabela CallType no Skype for Business Server 2015
 
A tabela CallType é uma tabela estática que armazena a lista de possíveis tipos de chamadas.
  
|**Coluna**|**Tipo de dados**|**Chave/índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**Callid** <br/> |int  <br/> |Primária  <br/> ||
|**CallType** <br/> |nvarchar  <br/> || Valores permitidos: <br/>  0--desconhecido <br/>  1-mensagens instantâneas <br/>  2 – compartilhamento de aplicativos <br/>  3--áudio <br/>  4-áudio e vídeo <br/>  Transferência de 5 arquivos <br/> |
   

