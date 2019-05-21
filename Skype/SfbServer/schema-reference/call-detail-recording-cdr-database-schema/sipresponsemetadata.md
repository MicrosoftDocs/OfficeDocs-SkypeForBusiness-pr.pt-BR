---
title: Tabela SIPResponseMetaData
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cf723737-4a75-4352-829b-f4954aa59716
description: O SIPResponseMetaDataTable contém uma lista de códigos de resposta SIP e a classificação e definição de cada um desses códigos. Esses códigos são gerados em resposta a eventos que afetam dispositivos SIP e sessões de comunicação SIP; por exemplo, o código de resposta 403 é gerado quando um dispositivo SIP faz uma solicitação, mas o servidor recusa para honrar essa solicitação.
ms.openlocfilehash: eecd8397315b93ebce9e5fad973f1274a6eb763a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295787"
---
# <a name="sipresponsemetadata-table"></a>Tabela SIPResponseMetaData
 
O SIPResponseMetaDataTable contém uma lista de códigos de resposta SIP e a classificação e definição de cada um desses códigos. Esses códigos são gerados em resposta a eventos que afetam dispositivos SIP e sessões de comunicação SIP; por exemplo, o código de resposta 403 é gerado quando um dispositivo SIP faz uma solicitação, mas o servidor recusa para honrar essa solicitação.
  
Esta tabela foi introduzida no Skype for Business Server 2015.
  
|**Coluna**|**Tipo de dados**|**Chave/índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**ResponseCode** <br/> |int  <br/> |Primária  <br/> |Valor numérico que representa o código de resposta SIP.  <br/> |
|**Classe** <br/> |int  <br/> || Classificação geral do código de resposta. As classificações incluem: <br/>  1-respostas informativas <br/>  2-respostas bem-sucedidas <br/>  3-respostas de redirecionamento <br/>  4-respostas de falha do cliente <br/>  5--respostas de falha do servidor <br/>  6-resposta de falha global <br/> |
|**Descrição** <br/> |nvarchar(256)  <br/> ||Descrição do código de resposta SIP. Por exemplo, o código de resposta 181 tem a seguinte descrição:  <br/> A chamada está sendo encaminhada  <br/> |
   

