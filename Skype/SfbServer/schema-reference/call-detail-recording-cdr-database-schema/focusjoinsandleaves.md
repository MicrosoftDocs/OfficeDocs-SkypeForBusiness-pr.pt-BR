---
title: Tabela FocusJoinsAndLeaves no Skype for Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: e6f0212c-67e9-4061-8720-d0296e855991
description: Cada registro nesta tabela contém as informações de CDR sobre a junção de um usuário e deixar informações para uma conferência. Cada conferência é representada nesta tabela por um registro para cada vez que um usuário entra e sai da conferência.
ms.openlocfilehash: 607101a4bbcc5909ab8c9271a878a0b59164552d
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62392283"
---
# <a name="focusjoinsandleaves-table-in-skype-for-business-server-2015"></a>Tabela FocusJoinsAndLeaves no Skype for Business Server 2015
 
Cada registro nesta tabela contém as informações de CDR sobre a junção de um usuário e deixar informações para uma conferência. Cada conferência é representada nesta tabela por um registro para cada vez que um usuário entra e sai da conferência.
  
|**Coluna**|**Tipo de dados**|**Chave/Índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Primário, externo  <br/> |Hora da instância da conferência. Usado em conjunto com **SessionIdSeq** para identificar exclusivamente uma instância de conferência. Consulte a [tabela Conferências no Skype for Business Server 2015](conferences.md) para obter mais informações. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primário, externo  <br/> |Número de ID para identificar a instância da conferência. Usado em conjunto com **SessionIdTime** para identificar exclusivamente uma instância de conferência. Consulte a [tabela Conferências no Skype for Business Server 2015](conferences.md) para obter mais informações. <br/> |
|**DialogSessionIdTime** <br/> |datetime  <br/> |Primário, Estrangeiro  <br/> |Tempo da solicitação de sessão. Usado em conjunto com **SessionIdSeq** para identificar exclusivamente uma sessão. Consulte a [tabela Dialogs no Skype for Business Server 2015](dialogs.md) para obter mais informações. <br/> |
|**DialogSessionIdSeq** <br/> |int  <br/> |Primário, Estrangeiro  <br/> |O número de ID para identificar a sessão. Usado em conjunto com **SessionIdTime** para identificar exclusivamente uma sessão. consulte a [tabela Dialogs no Skype for Business Server 2015](dialogs.md) para obter mais informações. <br/> |
|**UserId** <br/> |int  <br/> |Foreign  <br/> |Número exclusivo que identifica esse usuário, referenciado da [tabela Usuários](users.md).  <br/> |
|**FocusUserInstance** <br/> |int  <br/> ||Se um usuário estiver conectado em vários computadores ou dispositivos ao mesmo tempo, **UserInstance** será usado para identificar exclusivamente a combinação usuário/dispositivo. <br/> |
|**IsUserInternal** <br/> |bit  <br/> | <br/> |Se o usuário se registrou internamente ou não.  <br/> |
|**UserRole** <br/> |int  <br/> | <br/> |A função desse usuário na conferência, como Apresentador ou Participante.  <br/> |
|**UserJoinTime** <br/> |datetime  <br/> | <br/> |A hora em que esse usuário ingressar na conferência.  <br/> |
|**UserLeaveTime** <br/> |datetime  <br/> | <br/> |A hora em que esse usuário sai da conferência.  <br/> |
|**ClientVerId** <br/> |int  <br/> |Foreign  <br/> |Versão do software cliente do usuário, referenciada à tabela [ClientVersions no Skype for Business Server 2015](clientversions.md).  <br/> |
|**UserEndpointId** <br/> |uniqueIdentifier  <br/> ||Identificador global exclusivo (GUID) do ponto de extremidade usado na conferência.  <br/> Este campo foi introduzido no Microsoft Lync Server 2013.  <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||Para uso interno pelo serviço de Monitoramento.  <br/> Este campo foi introduzido no Skype for Business Server 2015.  <br/> |
   

