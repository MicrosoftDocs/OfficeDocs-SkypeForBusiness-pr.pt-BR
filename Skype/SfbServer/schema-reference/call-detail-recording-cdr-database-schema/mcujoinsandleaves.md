---
title: Tabela McuJoinsAndLeaves no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4e073366-0b5d-45b4-a3f6-d63dd5fd9f25
description: Cada registro desta tabela contém detalhes da chamada sobre uma combinação de um servidor de ingresso ou de saída e conferência do usuário. Por exemplo, se um usuário ingressar em uma conferência que inclui a conferência da Web e os elementos de áudio/vídeo, um registro seria criado para a sua associação de Webconferência do usuário e outro registro será criado para a reunião de conferência de áudio/vídeo do usuário.
ms.openlocfilehash: d61b3c1ef1aa6fe481a4022f7bc434b523b68213
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296067"
---
# <a name="mcujoinsandleaves-table-in-skype-for-business-server-2015"></a>Tabela McuJoinsAndLeaves no Skype for Business Server 2015
 
Cada registro desta tabela contém detalhes da chamada sobre uma combinação de um servidor de ingresso ou de saída e conferência do usuário. Por exemplo, se um usuário ingressar em uma conferência que inclui a conferência da Web e os elementos de áudio/vídeo, um registro seria criado para a sua associação de Webconferência do usuário e outro registro será criado para a reunião de conferência de áudio/vídeo do usuário.
  
|**Coluna**|**Tipo de dados**|**Chave/índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**Id_da_sessãotime** <br/> |datetime  <br/> |Primário, estrangeiro  <br/> |Hora da ocorrência da conferência. Usado em conjunto com **SessionIdSeq** para identificar uma instância de conferência de maneira exclusiva. Consulte a [tabela conferências no Skype for Business Server 2015](conferences.md) para obter mais informações. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primário, estrangeiro  <br/> |Número de identificação para identificar a instância de conferência. Usado em conjunto com **** a identificação_da_sessãotime para identificar exclusivamente uma instância de conferência. Consulte a [tabela conferências no Skype for Business Server 2015](conferences.md) para obter mais informações. <br/> |
|**ID** <br/> |int  <br/> |Primário, estrangeiro  <br/> |Número exclusivo que identifica esse usuário. Para obter mais informações, consulte a [tabela usuários](users.md) . <br/> |
|**McuUserInstance** <br/> |int  <br/> |Primária  <br/> |Se um usuário estiver conectado em vários computadores ou dispositivos de uma vez, o McuUserInstance identifica exclusivamente a combinação de usuário/dispositivo.  <br/> |
|**IsFromPstn** <br/> |bit  <br/> | <br/> |Se o usuário está ingressando de uma PSTN ou não.  <br/> |
|**McuId** <br/> |int  <br/> |Primário, estrangeiro  <br/> |Número exclusivo que identifica esse servidor de conferência. Consulte a [tabela MCUs no Skype for Business Server 2015](mcus.md) para obter mais informações. <br/> |
|**DialogSessionIdTime** <br/> |datetime  <br/> |Exterior  <br/> |Tempo de solicitação de sessão. Usado em conjunto com o **SessionIdSeq** para identificar exclusivamente uma sessão. Consulte a [tabela de diálogos no Skype for Business Server 2015](dialogs.md) para obter mais informações. <br/> |
|**DialogSessionIdSeq** <br/> |int  <br/> |Exterior  <br/> |Número de identificação para identificar a sessão. Usado em conjunto com **** a identificação_da_sessãotime para identificar exclusivamente uma sessão. Consulte a [tabela de diálogos no Skype for Business Server 2015](dialogs.md) para obter mais informações. <br/> |
|**Userjointime** <br/> |datetime  <br/> | <br/> |A hora em que este usuário entra neste servidor de conferência.  <br/> |
|**Userleavetime** <br/> |datetime  <br/> | <br/> |O horário em que este usuário sai deste servidor de conferência.  <br/> |
|**ClientVerId** <br/> |int  <br/> |Exterior  <br/> |Identificador que especifica o número da versão do software cliente usado na conferência. Consulte a [tabela ClientVersions no Skype for Business Server 2015](clientversions.md) para obter mais informações. <br/> Este campo foi apresentado no Microsoft Lync Server 2013.  <br/> |
|**LastModifiedtime** <br/> |DateTime  <br/> ||Para uso interno pelo serviço de monitoramento.  <br/> Este campo foi apresentado no Skype for Business Server 2015.  <br/> |
   

