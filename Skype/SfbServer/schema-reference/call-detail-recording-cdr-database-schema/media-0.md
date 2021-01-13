---
title: Exibição de mídia
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
ms.assetid: 1a7b2e59-082e-4188-98ae-48ae9bd3494a
description: A exibição de mídia armazena informações sobre um tipo de mídia usado em uma sessão ponto a ponto. Uma sessão será representada por vários registros na tabela caso mais de um tipo de mídia seja usado. Essa exibição foi introduzida no Microsoft Lync Server 2013.
ms.openlocfilehash: 77c22246056a28cdb41a007ac0d7e2617fa00ad9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831781"
---
# <a name="media-view"></a>Exibição de mídia
 
A exibição de mídia armazena informações sobre um tipo de mídia usado em uma sessão ponto a ponto. Uma sessão será representada por vários registros na tabela caso mais de um tipo de mídia seja usado. Essa exibição foi introduzida no Microsoft Lync Server 2013.
  
> [!NOTE]
> A exibição de mídia não deve ser usada para calcular a duração de mídia para uma sessão. Essa exibição contém os detalhes de sinalização da troca de mídia em uma sessão. A troca de mídia é feita pela solicitação INVITE, e o StartTime indica o horário em que o INVITE foi enviado. O horário de convite não significa, necessariamente, o horário de início da mídia, pois a mídia só começa depois que a sessão tenha sido aceita. 
  
O visualizador de mídia contém todas as colunas no [exibição SessionDetails,](sessiondetails-0.md) além das listadas abaixo.
  
|**Coluna**|**Tipo de dados**|**Detalhes**|
|:-----|:-----|:-----|
|**Mídia** <br/> |nvarchar(256)  <br/> |Tipo de mídia. Consulte a [tabela MediaList](medialist.md) para obter mais informações. <br/> |
|**MediaStartTime** <br/> |datetime  <br/> |Horário em que a solicitação de mídia foi enviada.  <br/> |
|**MediaEndTime** <br/> |datetime  <br/> |Horário de término da sessão.  <br/> |
   

