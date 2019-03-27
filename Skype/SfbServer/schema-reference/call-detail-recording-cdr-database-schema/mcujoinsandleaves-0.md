---
title: Exibir McuJoinsAndLeaves
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6f00b8e7-b8b6-4657-ac5e-d8a571806ae2
description: O modo de exibição McuJoinsAndLeaves armazena informações sobre a participação de usuários e deixar informações para um servidor de conferência. Cada registro nesse modo de exibição contém detalhes de chamada sobre uma combinação de um servidor de conferência e ingressar ou deixar de usuário. Este modo de exibição foi introduzido no Microsoft Lync Server 2013.
ms.openlocfilehash: db759e324689cfbad92389f30c8fd632c24ebd5e
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30892805"
---
# <a name="mcujoinsandleaves-view"></a>Exibir McuJoinsAndLeaves
 
O modo de exibição McuJoinsAndLeaves armazena informações sobre a participação de usuários e deixar informações para um servidor de conferência. Cada registro nesse modo de exibição contém detalhes de chamada sobre uma combinação de um servidor de conferência e ingressar ou deixar de usuário. Este modo de exibição foi introduzido no Microsoft Lync Server 2013.
  
|**Coluna**|**Tipo de dados**|**Detalhes**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Hora da ocorrência de conferência. Usado em conjunto com SessionIdSeq para identificar exclusivamente uma instância de conferência. Consulte a [tabela de conferências em Skype para Business Server 2015](conferences.md) para obter mais informações. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Número de identificação para identificar a instância de conferência. Usado em conjunto com SessionIdTime para identificar exclusivamente uma instância de conferência. Consulte a [tabela de conferências em Skype para Business Server 2015](conferences.md) para obter mais informações. <br/> |
|**McuUri** <br/> |nvarchar(256)  <br/> |O URI do servidor de conferência que o usuário está conectado.  <br/> |
|**McuUriType** <br/> |nvarchar(256)  <br/> |O URI do servidor de conferência que o usuário está conectado. Consulte a [tabela UriTypes](uritypes.md) para obter mais informações. <br/> |
|**UserUri** <br/> |nvarchar(450)  <br/> |O URI do usuário cujas informações de ingresso/saída de servidor de conferência foi capturadas.  <br/> |
|**UserUriType** <br/> |nvarchar(256)  <br/> |O tipo de URI do usuário cujas informações de ingresso/saída de servidor de conferência foi capturadas. Consulte a [tabela UriTypes](uritypes.md) para obter mais informações. <br/> |
|**UserTenant** <br/> |nvarchar(256)  <br/> |O locatário do usuário cujas informações de ingresso/saída de servidor de conferência foi capturadas. Consulte a [tabela de inquilinos](tenants.md) para obter mais informações. <br/> |
|**UserClientVersion** <br/> |nvarchar(256)  <br/> |A versão do cliente usado pelo usuário cujas informações de ingresso/saída de servidor de conferência foi capturadas.  <br/> |
|**UserClientType** <br/> |int  <br/> |O cliente usado pelo usuário cujas informações de ingresso/saída de servidor de conferência foi capturadas. Consulte a [tabela UserAgentDef](useragentdef.md) para obter mais detalhes. <br/> |
|**UserClientCategory** <br/> |nvarchar(64)  <br/> |O nome da categoria do cliente usado pelo usuário cujas informações de ingresso/saída de servidor de conferência foi capturadas.  <br/> |
|**McuUserInstance** <br/> |int  <br/> |Identifica exclusivamente a combinação de dispositivo do usuário para usuários que fizeram logon simultâneo em vários dispositivos.  <br/> |
|**IsUserFromPstn** <br/> |bit  <br/> |Bit que indica se o usuário é um usuário interno ou não.  <br/> |
|**DialogSessionIdTime** <br/> |datetime  <br/> |Hora da solicitação de sessão. Usado em conjunto com SessionIdSeq para identificar exclusivamente uma sessão. Consulte a [tabela no Skype para Business Server 2015 de diálogos](dialogs.md) para obter mais informações. <br/> |
|**DialogSessionIdSeq** <br/> |int  <br/> |Número de identificação para identificar a sessão. Usado em conjunto com SessionIdTime para identificar exclusivamente uma sessão. Consulte a [tabela no Skype para Business Server 2015 de diálogos](dialogs.md) para obter mais informações. <br/> |
|**DialogId** <br/> |varchar(775)  <br/> |ID de diálogo SIP da sessão. O formato é: diálogo; da marca; a marca.  <br/> |
|**UserJoinTime** <br/> |datetime  <br/> |Hora em que o usuário entrou o servidor de conferência.  <br/> |
|**UserLeaveTime** <br/> |datetime  <br/> |Hora em que o usuário saiu do servidor de conferência.  <br/> |
   

