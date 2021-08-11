---
title: Tabela ConferenceMessageCount no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 78569dbf-5217-42fa-ba1a-4380f56e2a3d
description: Cada registro nesta tabela representa um usuário em uma conferência de IM e inclui o número de mensagens enviadas por esse usuário. Cada conferência é representada por vários registros nesta tabela; um registro para cada usuário.
ms.openlocfilehash: 7e713e6d2eb9f856ee039345a0ab2e920e5ee09778b80201c823b14fbc270009
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54289499"
---
# <a name="conferencemessagecount-table-in-skype-for-business-server-2015"></a>Tabela ConferenceMessageCount no Skype for Business Server 2015
 
Cada registro nesta tabela representa um usuário em uma conferência de IM e inclui o número de mensagens enviadas por esse usuário. Cada conferência é representada por vários registros nesta tabela; um registro para cada usuário.
  
|**Coluna**|**Tipo de dados**|**Chave/Índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Primário, externo  <br/> |Hora da instância da conferência. Usado em conjunto com **SessionIdSeq** para identificar exclusivamente uma instância de conferência. Consulte a [tabela Conferências no Skype for Business Server 2015](conferences.md) para obter mais informações. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primário, externo  <br/> |Número de ID para identificar a instância da conferência. Usado em conjunto com **SessionIdTime** para identificar exclusivamente uma instância de conferência. Consulte a [tabela Conferências no Skype for Business Server 2015](conferences.md) para obter mais informações. <br/> |
|**UserId** <br/> |int  <br/> |Foreign  <br/> |Número exclusivo que identifica esse usuário, referenciado da [tabela Usuários.](users.md)  <br/> |
|**MessageCount** <br/> |smallint  <br/> | <br/> |O número de mensagens enviadas por esse usuário durante esta conferência.  <br/> |
   

