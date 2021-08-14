---
title: Tabela McuJoinsAndLeaves no Skype for Business Server 2015
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
ms.assetid: 4e073366-0b5d-45b4-a3f6-d63dd5fd9f25
description: Cada registro nesta tabela contém detalhes de chamada sobre uma combinação de um servidor de união ou saída do usuário e conferência. Por exemplo, se um usuário ingressar em uma conferência que inclua elementos de webconferência e áudio/vídeo, um registro será criado para a junção de webconferência desse usuário e outro registro será criado para a junção de conferência de áudio/vídeo do usuário.
ms.openlocfilehash: 9f879a683e45a4272096bfdacc500b48d405bb6c8fb02721fda543134726b181
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54326277"
---
# <a name="mcujoinsandleaves-table-in-skype-for-business-server-2015"></a>Tabela McuJoinsAndLeaves no Skype for Business Server 2015
 
Cada registro nesta tabela contém detalhes de chamada sobre uma combinação de um servidor de união ou saída do usuário e conferência. Por exemplo, se um usuário ingressar em uma conferência que inclua elementos de webconferência e áudio/vídeo, um registro será criado para a junção de webconferência desse usuário e outro registro será criado para a junção de conferência de áudio/vídeo do usuário.
  
|**Coluna**|**Tipo de dados**|**Chave/Índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Primário, externo  <br/> |Hora da instância da conferência. Usado em conjunto com **SessionIdSeq** para identificar exclusivamente uma instância de conferência. Consulte a [tabela Conferências no Skype for Business Server 2015](conferences.md) para obter mais informações. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primário, externo  <br/> |Número de ID para identificar a instância da conferência. Usado em conjunto com **SessionIdTime** para identificar exclusivamente uma instância de conferência. Consulte a [tabela Conferências no Skype for Business Server 2015](conferences.md) para obter mais informações. <br/> |
|**UserId** <br/> |int  <br/> |Primário, externo  <br/> |Número exclusivo identificando este usuário. Consulte a [tabela Usuários para](users.md) obter mais informações. <br/> |
|**McuUserInstance** <br/> |int  <br/> |Primário  <br/> |Se um usuário estiver conectado em vários computadores ou dispositivos ao mesmo tempo, McuUserInstance identificará exclusivamente a combinação usuário/dispositivo.  <br/> |
|**IsFromPstn** <br/> |bit  <br/> | <br/> |Se o usuário está participando de um PSTN ou não.  <br/> |
|**McuId** <br/> |int  <br/> |Primário, externo  <br/> |Número exclusivo que identifica esse servidor de conferência. Consulte a [tabela Mcus no Skype for Business Server 2015](mcus.md) para obter mais informações. <br/> |
|**DialogSessionIdTime** <br/> |datetime  <br/> |Foreign  <br/> |Tempo da solicitação de sessão. Usado em conjunto com **SessionIdSeq** para identificar exclusivamente uma sessão. Consulte a [tabela Dialogs no Skype for Business Server 2015](dialogs.md) para obter mais informações. <br/> |
|**DialogSessionIdSeq** <br/> |int  <br/> |Foreign  <br/> |O número de ID para identificar a sessão. Usado em conjunto com **SessionIdTime** para identificar exclusivamente uma sessão. Consulte a [tabela Dialogs no Skype for Business Server 2015](dialogs.md) para obter mais informações. <br/> |
|**UserJoinTime** <br/> |datetime  <br/> | <br/> |A hora em que esse usuário ingressar nesse servidor de conferência.  <br/> |
|**UserLeaveTime** <br/> |datetime  <br/> | <br/> |A hora em que esse usuário deixa esse servidor de conferência.  <br/> |
|**ClientVerId** <br/> |int  <br/> |Foreign  <br/> |Identificador que especifica o número de versão do software cliente usado na conferência. Consulte a [tabela ClientVersions no Skype for Business Server 2015](clientversions.md) para obter mais informações. <br/> Este campo foi introduzido no Microsoft Lync Server 2013.  <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||Para uso interno pelo serviço de Monitoramento.  <br/> Este campo foi introduzido no Skype for Business Server 2015.  <br/> |
   

