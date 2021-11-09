---
title: Tabela SIPResponseMetaData
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: cf723737-4a75-4352-829b-f4954aa59716
description: O SIPResponseMetaDataTable contém uma lista de códigos de resposta SIP e a classificação e definição de cada um destes códigos. Estes códigos são gerados em resposta aos eventos que afetam dispositivos SIP e sessões de comunicação SIP. Por exemplo, o código de resposta 403 é gerado quando um dispositivo SIP faz uma solicitação, mas o servidor declina esta solicitação.
ms.openlocfilehash: acf2c3166628af3a4633e98713ca25a5ae703ff6
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60863388"
---
# <a name="sipresponsemetadata-table"></a>Tabela SIPResponseMetaData
 
O SIPResponseMetaDataTable contém uma lista de códigos de resposta SIP e a classificação e definição de cada um destes códigos. Estes códigos são gerados em resposta aos eventos que afetam dispositivos SIP e sessões de comunicação SIP. Por exemplo, o código de resposta 403 é gerado quando um dispositivo SIP faz uma solicitação, mas o servidor declina esta solicitação.
  
Esta tabela foi introduzida no Skype for Business Server 2015.
  
|**Column**|**Tipo de dados**|**Chave/Índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**ResponseCode** <br/> |int  <br/> |Primário  <br/> |Valor numérico que representa o código de resposta SIP.  <br/> |
|**Classe** <br/> |int  <br/> || Classificação geral do código de resposta. As classificações incluem: <br/>  1 - Respostas informacionais <br/>  2 - Respostas bem-sucedidas <br/>  3 - Respostas de redirecionamento <br/>  4 - Respostas de falha do cliente <br/>  5 - Respostas de falha do servidor <br/>  6 - Resposta de Falha Global <br/> |
|**Descrição** <br/> |nvarchar(256)  <br/> ||Descrição do código de resposta SIP. Por exemplo, o código de resposta 181 possui a seguinte descrição:  <br/> A chamada está sendo encaminhada  <br/> |
   

