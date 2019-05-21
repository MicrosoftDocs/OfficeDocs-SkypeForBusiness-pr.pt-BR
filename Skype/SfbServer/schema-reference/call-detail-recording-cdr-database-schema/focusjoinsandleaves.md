---
title: Tabela FocusJoinsAndLeaves no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e6f0212c-67e9-4061-8720-d0296e855991
description: Cada registro desta tabela contém as informações de CDR sobre o ingresso de um usuário e as informações de licença de uma conferência. Cada conferência é representada por um registro por cada vez que um usuário entra e sai da conferência.
ms.openlocfilehash: 4eb9f6300613fb61a7173be547aa83adf61d1026
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296207"
---
# <a name="focusjoinsandleaves-table-in-skype-for-business-server-2015"></a>Tabela FocusJoinsAndLeaves no Skype for Business Server 2015
 
Cada registro desta tabela contém as informações de CDR sobre o ingresso de um usuário e as informações de licença de uma conferência. Cada conferência é representada por um registro por cada vez que um usuário entra e sai da conferência.
  
|**Coluna**|**Tipo de dados**|**Chave/índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**Id_da_sessãotime** <br/> |datetime  <br/> |Primário, estrangeiro  <br/> |Hora da ocorrência da conferência. Usado em conjunto com **SessionIdSeq** para identificar uma instância de conferência de maneira exclusiva. Consulte a [tabela conferências no Skype for Business Server 2015](conferences.md) para obter mais informações. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primário, estrangeiro  <br/> |Número de identificação para identificar a instância de conferência. Usado em conjunto com **** a identificação_da_sessãotime para identificar exclusivamente uma instância de conferência. Consulte a [tabela conferências no Skype for Business Server 2015](conferences.md) para obter mais informações. <br/> |
|**DialogSessionIdTime** <br/> |datetime  <br/> |Primário, estrangeiro  <br/> |Tempo de solicitação de sessão. Usado em conjunto com o **SessionIdSeq** para identificar exclusivamente uma sessão. Consulte a [tabela de diálogos no Skype for Business Server 2015](dialogs.md) para obter mais informações. <br/> |
|**DialogSessionIdSeq** <br/> |int  <br/> |Primário, estrangeiro  <br/> |Número de identificação para identificar a sessão. Usado em conjunto com **** a identificação_da_sessãotime para identificar exclusivamente uma sessão. consulte a [tabela de diálogos no Skype for Business Server 2015](dialogs.md) para obter mais informações. <br/> |
|**ID** <br/> |int  <br/> |Exterior  <br/> |Número exclusivo que identifica esse usuário, referenciado pela [tabela usuários](users.md).  <br/> |
|**FocusUserInstance** <br/> |int  <br/> ||Se um usuário estiver conectado em vários computadores ou dispositivos ao mesmo tempo, o **UserInstance** será usado para identificar exclusivamente a combinação de usuário/dispositivo. <br/> |
|**IsUserInternal** <br/> |bit  <br/> | <br/> |Se o usuário está conectado de interno ou não.  <br/> |
|**Função** <br/> |int  <br/> | <br/> |A função deste usuário na conferência, como apresentador ou participante.  <br/> |
|**Userjointime** <br/> |datetime  <br/> | <br/> |A hora em que este usuário entra na conferência.  <br/> |
|**Userleavetime** <br/> |datetime  <br/> | <br/> |A hora em que esse usuário sai da conferência.  <br/> |
|**ClientVerId** <br/> |int  <br/> |Exterior  <br/> |Versão do software cliente do usuário, referenciada à [tabela ClientVersions no Skype for Business Server 2015](clientversions.md).  <br/> |
|**Userendpointid** <br/> |Identificador  <br/> ||Identificador global exclusivo (GUID) do ponto de extremidade usado na conferência.  <br/> Este campo foi apresentado no Microsoft Lync Server 2013.  <br/> |
|**LastModifiedtime** <br/> |DateTime  <br/> ||Para uso interno pelo serviço de monitoramento.  <br/> Este campo foi apresentado no Skype for Business Server 2015.  <br/> |
   

