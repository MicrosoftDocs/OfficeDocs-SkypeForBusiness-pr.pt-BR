---
title: Tabela FocusJoinsAndLeaves Skype para Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 7/15/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e6f0212c-67e9-4061-8720-d0296e855991
description: Cada registro desta tabela contém as informações de CDR sobre associação de um usuário e informações de saída para uma conferência. Nesta tabela, a cada conferência é representada por um registro de cada vez que um usuário entradas e saídas na conferência.
ms.openlocfilehash: dea6ae9e66416da41c9ca5df0d6a8c3e61550238
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213078"
---
# <a name="focusjoinsandleaves-table-in-skype-for-business-server-2015"></a>Tabela FocusJoinsAndLeaves Skype para Business Server 2015
 
Cada registro desta tabela contém as informações de CDR sobre associação de um usuário e informações de saída para uma conferência. Nesta tabela, a cada conferência é representada por um registro de cada vez que um usuário entradas e saídas na conferência.
  
|**Coluna**|**Tipo de dados**|**Chave/índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Primária, estrangeira  <br/> |Hora da ocorrência de conferência. Usado em conjunto com **SessionIdSeq** para identificar exclusivamente uma instância de conferência. Consulte a [tabela de conferências em Skype para Business Server 2015](conferences.md) para obter mais informações. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primária, estrangeira  <br/> |Número de identificação para identificar a instância de conferência. Usado em conjunto com **SessionIdTime** para identificar exclusivamente uma instância de conferência. Consulte a [tabela de conferências em Skype para Business Server 2015](conferences.md) para obter mais informações. <br/> |
|**DialogSessionIdTime** <br/> |datetime  <br/> |Primária, estrangeira  <br/> |Hora da solicitação de sessão. Usado em conjunto com **SessionIdSeq** para identificar exclusivamente uma sessão. Consulte a [tabela no Skype para Business Server 2015 de diálogos](dialogs.md) para obter mais informações. <br/> |
|**DialogSessionIdSeq** <br/> |int  <br/> |Primária, estrangeira  <br/> |Número de identificação para identificar a sessão. Usado em conjunto com **SessionIdTime** para identificar exclusivamente uma sessão. Consulte a [tabela no Skype para Business Server 2015 de diálogos](dialogs.md) para obter mais informações. <br/> |
|**UserId** <br/> |int  <br/> |Externa  <br/> |Número exclusivo que identifica este usuário, referenciado de [Users table](users.md).  <br/> |
|**FocusUserInstance** <br/> |int  <br/> ||Se um usuário está conectado em vários computadores ou dispositivos ao mesmo tempo, **UserInstance** é usado para identificar exclusivamente a combinação de usuário/dispositivo. <br/> |
|**IsUserInternal** <br/> |bit  <br/> | <br/> |Se o usuário conectado internamente ou não.  <br/> |
|**UserRole** <br/> |int  <br/> | <br/> |Função do usuário na conferência, como apresentador ou participante.  <br/> |
|**UserJoinTime** <br/> |datetime  <br/> | <br/> |A hora em que este usuário ingressa na conferência.  <br/> |
|**UserLeaveTime** <br/> |datetime  <br/> | <br/> |A hora em que esse usuário sair da conferência.  <br/> |
|**ClientVerId** <br/> |int  <br/> |Externa  <br/> |Versão do software de cliente do usuário, referenciado na [tabela ClientVersions Skype para Business Server 2015](clientversions.md).  <br/> |
|**UserEndpointId** <br/> |Identificador exclusivo  <br/> ||Identificador globalmente exclusivo (GUID) do ponto de extremidade usado na conferência.  <br/> Este campo foi introduzido no Microsoft Lync Server 2013.  <br/> |
|**LastModifiedTime** <br/> |DateTime  <br/> ||Para uso interno pelo serviço de monitoramento.  <br/> Este campo foi introduzido no Skype para Business Server 2015.  <br/> |
   

