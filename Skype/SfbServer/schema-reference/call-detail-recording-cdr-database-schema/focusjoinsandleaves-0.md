---
title: Exibir FocusJoinsAndLeaves
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 226460ef-766f-4d61-80cb-f332b65a210d
description: O modo de exibição FocusJoinsAndLeaves armazena informações sobre a participação e deixar informações para uma conferência. Cada conferência é representada nesse modo de exibição por um registro escrito cada vez que um usuário entradas e saídas na conferência. Este modo de exibição foi introduzido no Microsoft Lync Server 2013.
ms.openlocfilehash: 4fa6a2ec043c5f9746a14d5214be9ad531159cd7
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213673"
---
# <a name="focusjoinsandleaves-view"></a>Exibir FocusJoinsAndLeaves
 
O modo de exibição FocusJoinsAndLeaves armazena informações sobre a participação e deixar informações para uma conferência. Cada conferência é representada nesse modo de exibição por um registro escrito cada vez que um usuário entradas e saídas na conferência. Este modo de exibição foi introduzido no Microsoft Lync Server 2013.
  
|**Coluna**|**Tipo de dados**|**Detalhes**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Hora da ocorrência de conferência. Usado em conjunto com SessionIdSeq para identificar exclusivamente uma instância de conferência. Consulte a [tabela de conferências em Skype para Business Server 2015](conferences.md) para obter mais informações. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Número de identificação para identificar a instância de conferência. Usado em conjunto com SessionIdTime para identificar exclusivamente uma instância de conferência. Consulte a [tabela de conferências em Skype para Business Server 2015](conferences.md) para obter mais informações. <br/> |
|**UserUri** <br/> |nvarchar(450)  <br/> |URI do usuário cujas informações de ingresso/saída da conferência foi capturadas.  <br/> |
|**UserUriType** <br/> |nvarchar(256)  <br/> |Tipo de URI do usuário cujas informações de ingresso/saída da conferência foi capturadas. Consulte a [tabela UriTypes](uritypes.md) para obter mais informações. <br/> |
|**UserTenant** <br/> |nvarchar(256)  <br/> |Locatário do usuário cujas informações de ingresso/saída da conferência foi capturadas. Consulte a [tabela de inquilinos](tenants.md) para obter mais informações. <br/> |
|**UserEndpointId** <br/> |Identificador exclusivo  <br/> |Identificador exclusivo do usuário cujas informações de ingresso/saída da conferência foi capturadas.  <br/> |
|**UserClientVersion** <br/> |nvarchar(256)  <br/> |Versão do cliente usado pelo usuário cujas informações de ingresso/saída da conferência foi capturadas.  <br/> |
|**UserClientType** <br/> |int  <br/> |Cliente usado pelo usuário cujas informações de ingresso/saída da conferência foi capturadas. Consulte a [tabela UserAgentDef](useragentdef.md) para obter mais detalhes. <br/> |
|**UserClientCategory** <br/> |nvarchar(64)  <br/> |Nome da categoria do cliente usado pelo usuário cujas informações de ingresso/saída da conferência foi capturadas.  <br/> |
|**FocusUserInstance** <br/> |int  <br/> ||
|**IsuserInternal** <br/> |bit  <br/> |Bit que indica se o usuário é um usuário interno ou não.  <br/> |
|**DialogSessionIdTime** <br/> |datetime  <br/> |Hora da solicitação de sessão. Usado em conjunto com SessionIdSeq para identificar exclusivamente uma sessão. Consulte a [tabela no Skype para Business Server 2015 de diálogos](dialogs.md) para obter mais informações. <br/> |
|**DialogSessionIdSeq** <br/> |int  <br/> |Se um usuário está conectado em vários computadores ou dispositivos ao mesmo tempo, UserInstance é usado para identificar exclusivamente a combinação de usuário/dispositivo.  <br/> |
|**DialogId** <br/> |varchar(775)  <br/> |ID de diálogo SIP da sessão. O formato é: diálogo; da marca; a marca.  <br/> |
|**UserJoinTime** <br/> |datetime  <br/> |Hora em que o usuário entrou na conferência.  <br/> |
|**UserLeaveTime** <br/> |datetime  <br/> |Hora em que o usuário saiu da conferência.  <br/> |
|**UserRole** <br/> |nvarchar(256)  <br/> |Função do usuário na conferência, como apresentador ou participante.  <br/> |
   

