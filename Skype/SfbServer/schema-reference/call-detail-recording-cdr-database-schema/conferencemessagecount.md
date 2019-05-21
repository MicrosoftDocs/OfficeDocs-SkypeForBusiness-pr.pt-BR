---
title: Tabela ConferenceMessageCount no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 78569dbf-5217-42fa-ba1a-4380f56e2a3d
description: Cada registro nessa tabela representa um usuário em uma conferência de mensagem instantânea e inclui o número de mensagens enviadas por esse usuário. Cada conferência é representada por vários registros nesta tabela; um registro para cada usuário.
ms.openlocfilehash: ef343536c34b3bd27d71ee37813e4b4e65156094
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296452"
---
# <a name="conferencemessagecount-table-in-skype-for-business-server-2015"></a>Tabela ConferenceMessageCount no Skype for Business Server 2015
 
Cada registro nessa tabela representa um usuário em uma conferência de mensagem instantânea e inclui o número de mensagens enviadas por esse usuário. Cada conferência é representada por vários registros nesta tabela; um registro para cada usuário.
  
|**Coluna**|**Tipo de dados**|**Chave/índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**Id_da_sessãotime** <br/> |datetime  <br/> |Primário, estrangeiro  <br/> |Hora da ocorrência da conferência. Usado em conjunto com **SessionIdSeq** para identificar uma instância de conferência de maneira exclusiva. Consulte a [tabela conferências no Skype for Business Server 2015](conferences.md) para obter mais informações. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primário, estrangeiro  <br/> |Número de identificação para identificar a instância de conferência. Usado em conjunto com **** a identificação_da_sessãotime para identificar exclusivamente uma instância de conferência. Consulte a [tabela conferências no Skype for Business Server 2015](conferences.md) para obter mais informações. <br/> |
|**ID** <br/> |int  <br/> |Exterior  <br/> |Número exclusivo que identifica esse usuário, referenciado pela [tabela usuários](users.md).  <br/> |
|**MessageCount** <br/> |smallint  <br/> | <br/> |O número de mensagens enviadas por este usuário durante esta conferência.  <br/> |
   

