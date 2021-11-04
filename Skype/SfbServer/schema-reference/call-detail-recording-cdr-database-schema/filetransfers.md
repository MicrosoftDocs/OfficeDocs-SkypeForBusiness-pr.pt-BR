---
title: Exibição FileTransfers
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: e52c3ad0-152e-4a18-af1c-1aff0d205151
description: O exibição FileTransfer armazena informações sobre sessões de transferência de arquivos ponto a ponto. Essa exibição foi introduzida no Microsoft Lync Server 2013.
ms.openlocfilehash: 11e46edf67c6ba9d1597f296ffd8ecf551241132
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60777801"
---
# <a name="filetransfers-view"></a>Exibição FileTransfers
 
O exibição FileTransfer armazena informações sobre sessões de transferência de arquivos ponto a ponto. Essa exibição foi introduzida no Microsoft Lync Server 2013.
  
> [!NOTE]
> O exibição FileTransfers contém todas as colunas no [exibição SessionDetails,](sessiondetails-0.md) além das colunas listadas abaixo.
  
|**Column**|**Tipo de dados**|**Detalhes**|
|:-----|:-----|:-----|
|**FileName** <br/> |nvarchar(256)  <br/> |Nome do arquivo transferido.  <br/> |
|**Cookie** <br/> |nvarchar(128)  <br/> |Usado para identificar cada mensagem de acompanhamento como sendo associado a este.  <br/> |
|**FileIdentity** <br/> |uniqueidentifier  <br/> |Identificador exclusivo para distinguir entre as transferências de arquivo envolvendo o mesmo nome do arquivo.  <br/> |
|**Accept** <br/> |bit  <br/> |Pode ser TRUE ou NULL. Se for TRUE, Rejeitar e Cancelar serão NULL.  <br/> |
|**Reject** <br/> |bit  <br/> |Pode ser TRUE ou NULL. Se for TRUE, Aceitar e Cancelar serão NULL.  <br/> |
|**Cancel** <br/> |bit  <br/> |Pode ser TRUE ou NULL. Se for TRUE, Aceitar e Rejeitar serão NULL.  <br/> |
   

