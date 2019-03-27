---
title: Exibir FileTransfers
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e52c3ad0-152e-4a18-af1c-1aff0d205151
description: O modo de exibição FileTransfer armazena informações sobre sessões de transferência de arquivo ponto a ponto. Este modo de exibição foi introduzido no Microsoft Lync Server 2013.
ms.openlocfilehash: a39e00becd772e74eb12de1a8ce5975e6626cffa
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30881462"
---
# <a name="filetransfers-view"></a>Exibir FileTransfers
 
O modo de exibição FileTransfer armazena informações sobre sessões de transferência de arquivo ponto a ponto. Este modo de exibição foi introduzido no Microsoft Lync Server 2013.
  
> [!NOTE]
> O modo de exibição do FileTransfers contém todas as colunas no [SessionDetails view](sessiondetails-0.md) além das colunas listadas abaixo.
  
|**Coluna**|**Tipo de dados**|**Detalhes**|
|:-----|:-----|:-----|
|**FileName** <br/> |nvarchar(256)  <br/> |Nome do arquivo transferido.  <br/> |
|**Cookie** <br/> |nvarchar (128)  <br/> |Usado para identificar cada mensagem de acompanhamento como sendo associado a este.  <br/> |
|**FileIdentity** <br/> |Identificador exclusivo  <br/> |Identificador exclusivo para distinguir entre transferências de arquivo envolvendo o mesmo nome de arquivo.  <br/> |
|**Aceitar** <br/> |bit  <br/> |Pode ser TRUE ou nulo. Se for TRUE, em seguida, rejeitar e Cancelar será NULL.  <br/> |
|**Rejeitar** <br/> |bit  <br/> |Pode ser TRUE ou nulo. Se for TRUE, em seguida, aceitar e Cancelar será NULL.  <br/> |
|**Cancelar** <br/> |bit  <br/> |Pode ser TRUE ou nulo. Se for TRUE, em seguida, aceitar e rejeitar será NULL.  <br/> |
   

