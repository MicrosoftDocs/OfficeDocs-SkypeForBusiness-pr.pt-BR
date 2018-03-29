---
title: Tabela SIPResponseMetaData
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cf723737-4a75-4352-829b-f4954aa59716
description: O SIPResponseMetaDataTable contém uma lista dos códigos de resposta SIP e a classificação e a definição de cada um desses códigos. Esses códigos são gerados em resposta a eventos que afetam os dispositivos SIP e SIP sessões de comunicação; Por exemplo, o código de resposta 403 é gerado quando um dispositivo SIP faz uma solicitação, mas o servidor recusar aceitar esse pedido.
ms.openlocfilehash: a90a248837dd705746fe3b342874aad10480e8a6
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="sipresponsemetadata-table"></a>Tabela SIPResponseMetaData
 
O SIPResponseMetaDataTable contém uma lista dos códigos de resposta SIP e a classificação e a definição de cada um desses códigos. Esses códigos são gerados em resposta a eventos que afetam os dispositivos SIP e SIP sessões de comunicação; Por exemplo, o código de resposta 403 é gerado quando um dispositivo SIP faz uma solicitação, mas o servidor recusar aceitar esse pedido.
  
Esta tabela foi introduzida no Skype para Business Server 2015.
  
|**Coluna**|**Tipo de dados**|**Índice de chaves /**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**ResponseCode** <br/> |int  <br/> |Primária  <br/> |Valor numérico que representa o código de resposta SIP.  <br/> |
|**Classe** <br/> |int  <br/> || Classificação geral para o código de resposta. Classificações incluem: <br/>  1 - respostas informacionais <br/>  2 - respostas bem-sucedidas <br/>  3 - respostas de redirecionamento de <br/>  4 - respostas de falha de cliente <br/>  5-- Respostas de falha do servidor <br/>  6 - resposta de falha global <br/> |
|**Descrição** <br/> |nvarchar(256)  <br/> ||Descrição do código de resposta SIP. Por exemplo, o código de resposta 181 tem a seguinte descrição:  <br/> Chamada está sendo encaminhada  <br/> |
   

