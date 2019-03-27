---
title: Tabela McuJoinsAndLeaves Skype para Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 7/15/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4e073366-0b5d-45b4-a3f6-d63dd5fd9f25
description: Cada registro desta tabela contém detalhes de chamada sobre uma combinação de um servidor de conferência e ingressar ou deixar de usuário. Por exemplo, se um usuário ingressa em uma conferência que inclui elementos de áudio/vídeo e webconferência, seria criado um registro para ingresso de conferência web desse usuário, e outro registro seria criado para o ingresso de conferência de áudio/vídeo do usuário.
ms.openlocfilehash: 7a31564ed770c956baa0ef7e968d0fba1dc3fd7d
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30894947"
---
# <a name="mcujoinsandleaves-table-in-skype-for-business-server-2015"></a>Tabela McuJoinsAndLeaves Skype para Business Server 2015
 
Cada registro desta tabela contém detalhes de chamada sobre uma combinação de um servidor de conferência e ingressar ou deixar de usuário. Por exemplo, se um usuário ingressa em uma conferência que inclui elementos de áudio/vídeo e webconferência, seria criado um registro para ingresso de conferência web desse usuário, e outro registro seria criado para o ingresso de conferência de áudio/vídeo do usuário.
  
|**Coluna**|**Tipo de dados**|**Chave/índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Primária, estrangeira  <br/> |Hora da ocorrência de conferência. Usado em conjunto com **SessionIdSeq** para identificar exclusivamente uma instância de conferência. Consulte a [tabela de conferências em Skype para Business Server 2015](conferences.md) para obter mais informações. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primária, estrangeira  <br/> |Número de identificação para identificar a instância de conferência. Usado em conjunto com **SessionIdTime** para identificar exclusivamente uma instância de conferência. Consulte a [tabela de conferências em Skype para Business Server 2015](conferences.md) para obter mais informações. <br/> |
|**UserId** <br/> |int  <br/> |Primária, estrangeira  <br/> |Número exclusivo que identifica este usuário. Consulte a [tabela de usuários](users.md) para obter mais informações. <br/> |
|**McuUserInstance** <br/> |int  <br/> |Primária  <br/> |Se um usuário está conectado em vários computadores ou dispositivos ao mesmo tempo, o McuUserInstance identifica exclusivamente a combinação de usuário/dispositivo.  <br/> |
|**IsFromPstn** <br/> |bit  <br/> | <br/> |Se o usuário está ingressando a partir de uma PSTN ou não.  <br/> |
|**McuId** <br/> |int  <br/> |Primária, estrangeira  <br/> |Número exclusivo que identifica este servidor de conferência. Consulte a [tabela Mcus Skype para Business Server 2015](mcus.md) para obter mais informações. <br/> |
|**DialogSessionIdTime** <br/> |datetime  <br/> |Externa  <br/> |Hora da solicitação de sessão. Usado em conjunto com **SessionIdSeq** para identificar exclusivamente uma sessão. Consulte a [tabela no Skype para Business Server 2015 de diálogos](dialogs.md) para obter mais informações. <br/> |
|**DialogSessionIdSeq** <br/> |int  <br/> |Externa  <br/> |Número de identificação para identificar a sessão. Usado em conjunto com **SessionIdTime** para identificar exclusivamente uma sessão. Consulte a [tabela no Skype para Business Server 2015 de diálogos](dialogs.md) para obter mais informações. <br/> |
|**UserJoinTime** <br/> |datetime  <br/> | <br/> |A hora em que este usuário ingressa neste servidor de conferência.  <br/> |
|**UserLeaveTime** <br/> |datetime  <br/> | <br/> |A hora em que este usuário deixa este servidor de conferência.  <br/> |
|**ClientVerId** <br/> |int  <br/> |Externa  <br/> |Identificador que especifica o número de versão do software cliente use na conferência. Consulte a [tabela ClientVersions Skype para Business Server 2015](clientversions.md) para obter mais informações. <br/> Este campo foi introduzido no Microsoft Lync Server 2013.  <br/> |
|**LastModifiedTime** <br/> |DateTime  <br/> ||Para uso interno pelo serviço de monitoramento.  <br/> Este campo foi introduzido no Skype para Business Server 2015.  <br/> |
   

