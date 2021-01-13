---
title: Tabela FocusJoinsAndLeaves no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: e6f0212c-67e9-4061-8720-d0296e855991
description: Cada registro nesta tabela contém as informações de CDR sobre o ingressar e deixar informações de um usuário para uma conferência. Cada conferência é representada nesta tabela por um registro para cada vez que um usuário entra e sai da conferência.
ms.openlocfilehash: ea3af4da259fe4186a3fa3937fd2977779dafeaa
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821621"
---
# <a name="focusjoinsandleaves-table-in-skype-for-business-server-2015"></a>Tabela FocusJoinsAndLeaves no Skype for Business Server 2015
 
Cada registro nesta tabela contém as informações de CDR sobre o ingressar e deixar informações de um usuário para uma conferência. Cada conferência é representada nesta tabela por um registro para cada vez que um usuário entra e sai da conferência.
  
|**Coluna**|**Tipo de dados**|**Chave/Índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Primário, externo  <br/> |Hora da instância da conferência. Usado em conjunto com **SessionIdSeq para** identificar exclusivamente uma instância de conferência. Consulte a [tabela Conferências no Skype for Business Server 2015](conferences.md) para obter mais informações. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primário, externo  <br/> |Número de ID para identificar a instância da conferência. Usado em conjunto com **SessionIdTime** para identificar exclusivamente uma instância de conferência. Consulte a [tabela Conferências no Skype for Business Server 2015](conferences.md) para obter mais informações. <br/> |
|**DialogSessionIdTime** <br/> |datetime  <br/> |Primário, Estrangeiro  <br/> |Tempo da solicitação de sessão. Usado em conjunto com **SessionIdSeq** para identificar exclusivamente uma sessão. Consulte a [tabela Dialogs no Skype for Business Server 2015](dialogs.md) para obter mais informações. <br/> |
|**DialogSessionIdSeq** <br/> |int  <br/> |Primário, Estrangeiro  <br/> |O número de ID para identificar a sessão. Usado em conjunto com **SessionIdTime** para identificar exclusivamente uma sessão. consulte a [tabela Dialogs no Skype for Business Server 2015](dialogs.md) para obter mais informações. <br/> |
|**UserId** <br/> |int  <br/> |Externo  <br/> |Número exclusivo que identifica esse usuário, referenciado na [tabela Usuários.](users.md)  <br/> |
|**FocusUserInstance** <br/> |int  <br/> ||Se um usuário estiver conectado em vários computadores ou dispositivos ao mesmo tempo, **UserInstance** será usado para identificar exclusivamente a combinação de usuário/dispositivo. <br/> |
|**IsUserInternal** <br/> |bit  <br/> | <br/> |Se o usuário se registrou internamente ou não.  <br/> |
|**UserRole** <br/> |int  <br/> | <br/> |A função desse usuário na conferência, como Apresentador ou Participante.  <br/> |
|**UserJoinTime** <br/> |datetime  <br/> | <br/> |A hora em que esse usuário ingressar na conferência.  <br/> |
|**UserLeaveTime** <br/> |datetime  <br/> | <br/> |A hora em que esse usuário deixa a conferência.  <br/> |
|**ClientVerId** <br/> |int  <br/> |Externo  <br/> |Versão do software cliente do usuário, referenciada na tabela [ClientVersions no Skype for Business Server 2015.](clientversions.md)  <br/> |
|**UserEndpointId** <br/> |uniqueIdentifier  <br/> ||Identificador global exclusivo (GUID) do ponto de extremidade usado na conferência.  <br/> Este campo foi introduzido no Microsoft Lync Server 2013.  <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||Para uso interno pelo serviço de Monitoramento.  <br/> Esse campo foi introduzido no Skype for Business Server 2015.  <br/> |
   

