---
title: Exibir FileTransfers
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e52c3ad0-152e-4a18-af1c-1aff0d205151
description: O modo de exibição FileTransfer armazena informações sobre sessões de transferência de arquivo ponto a ponto. Este modo de exibição foi introduzido no Microsoft Lync Server 2013.
ms.openlocfilehash: aa238d11a88b8259427619271171adcf6f1c3e42
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901184"
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
   

