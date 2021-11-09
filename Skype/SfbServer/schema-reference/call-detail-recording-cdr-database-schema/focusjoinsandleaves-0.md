---
title: Exibição FocusJoinsAndLeaves
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 226460ef-766f-4d61-80cb-f332b65a210d
description: A exibição FocusJoinsAndLeaves armazena informações sobre como ingressar e deixar informações para uma conferência. Cada conferência é representada nesta exibição por um registro escrito sempre que um usuário ins junta e sai da conferência. Essa exibição foi introduzida no Microsoft Lync Server 2013.
ms.openlocfilehash: 8dcc82fe641b451190236f813f432c237e7fa2e2
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60845054"
---
# <a name="focusjoinsandleaves-view"></a>Exibição FocusJoinsAndLeaves
 
A exibição FocusJoinsAndLeaves armazena informações sobre como ingressar e deixar informações para uma conferência. Cada conferência é representada nesta exibição por um registro escrito sempre que um usuário ins junta e sai da conferência. Essa exibição foi introduzida no Microsoft Lync Server 2013.
  
|**Column**|**Tipo de dados**|**Detalhes**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Hora da instância da conferência. Usada em conjunto com SessionIdSeq para identificar uma instância da conferência de maneira exclusiva. Consulte a [tabela Conferências no Skype for Business Server 2015](conferences.md) para obter mais informações. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Número de ID para identificar a instância da conferência. Usada em conjunto com SessionIdTime para identificar uma instância da conferência de maneira exclusiva. Consulte a [tabela Conferências no Skype for Business Server 2015](conferences.md) para obter mais informações. <br/> |
|**UserUri** <br/> |nvarchar(450)  <br/> |URI do usuário cujas informações de união/saída de conferência foram capturadas.  <br/> |
|**UserUriType** <br/> |nvarchar(256)  <br/> |Tipo de URI do usuário cujas informações de união/saída de conferência foram capturadas. Consulte a [tabela UriTypes para](uritypes.md) obter mais informações. <br/> |
|**UserTenant** <br/> |nvarchar(256)  <br/> |Locatário do usuário cujas informações de união/saída de conferência foram capturadas. Consulte a [tabela Locatários](tenants.md) para obter mais informações. <br/> |
|**UserEndpointId** <br/> |uniqueidentifier  <br/> |Identificador exclusivo do usuário cujas informações de união/saída de conferência foram capturadas.  <br/> |
|**UserClientVersion** <br/> |nvarchar(256)  <br/> |Versão do cliente usada pelo usuário cujas informações de união/saída de conferência foram capturadas.  <br/> |
|**UserClientType** <br/> |int  <br/> |Cliente usado pelo usuário cujas informações de união/saída de conferência foram capturadas. Consulte [UserAgentDef table](useragentdef.md) para obter mais detalhes. <br/> |
|**UserClientCategory** <br/> |nvarchar(64)  <br/> |Nome da categoria do cliente usado pelo usuário cujas informações de união/saída de conferência foram capturadas.  <br/> |
|**FocusUserInstance** <br/> |int  <br/> ||
|**IsuserInternal** <br/> |bit  <br/> |Bit que representa se o usuário é interno ou não.  <br/> |
|**DialogSessionIdTime** <br/> |datetime  <br/> |Hora da solicitação da sessão. Utilizada em conjunto com o SessionIdSeq para identificar de forma exclusiva uma sessão. Consulte a [tabela Dialogs no Skype for Business Server 2015](dialogs.md) para obter mais informações. <br/> |
|**DialogSessionIdSeq** <br/> |int  <br/> |Se um usuário estiver conectado em vários computadores ou dispositivos ao mesmo tempo, UserInstance será usado para identificar exclusivamente a combinação usuário/dispositivo.  <br/> |
|**DialogId** <br/> |varchar(775)  <br/> |ID de diálogo SIP da sessão. O formato é: diálogo;de-marca;para-marca.  <br/> |
|**UserJoinTime** <br/> |datetime  <br/> |Hora em que o usuário ingressou na conferência.  <br/> |
|**UserLeaveTime** <br/> |datetime  <br/> |Hora em que o usuário saiu da conferência.  <br/> |
|**UserRole** <br/> |nvarchar(256)  <br/> |Função do usuário na conferência, como Apresentador ou Participante.  <br/> |
   

