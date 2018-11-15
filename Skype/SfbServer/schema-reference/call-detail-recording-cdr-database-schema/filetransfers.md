---
title: Exibir FileTransfers
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
ms.openlocfilehash: 97bc5f957192c8a2c6d888f81fce0891aa2b4f75
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/15/2018
ms.locfileid: "26531216"
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
   

