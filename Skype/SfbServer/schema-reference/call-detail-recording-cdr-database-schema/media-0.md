---
title: Modo de exibição de mídia
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1a7b2e59-082e-4188-98ae-48ae9bd3494a
description: O modo de exibição mídia armazena informações sobre um tipo de mídia usado em uma sessão ponto a ponto. Uma sessão seria representada por vários registros na tabela, se mais de um tipo de mídia for usado. Este modo de exibição foi apresentado no Microsoft Lync Server 2013.
ms.openlocfilehash: 044a31381d4e1e48c465f7ee6de89acab10ab54e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295997"
---
# <a name="media-view"></a>Modo de exibição de mídia
 
O modo de exibição mídia armazena informações sobre um tipo de mídia usado em uma sessão ponto a ponto. Uma sessão seria representada por vários registros na tabela, se mais de um tipo de mídia for usado. Este modo de exibição foi apresentado no Microsoft Lync Server 2013.
  
> [!NOTE]
> O modo de exibição de mídia não deve ser usado para calcular a duração da mídia de uma sessão. Este modo de exibição contém os detalhes de sinalização da troca de mídia em uma sessão. A troca de mídia é feita pela solicitação de convite e StartTime indica a hora em que o convite foi enviado. O tempo de convite não significa necessariamente a hora de início da mídia porque a mídia só inicia após a aceitação da sessão. 
  
O modo de exibição de mídia contém todas as colunas na [exibição SessionDetails](sessiondetails-0.md) além daquelas listadas abaixo.
  
|**Coluna**|**Tipo de dados**|**Detalhes**|
|:-----|:-----|:-----|
|**Media** <br/> |nvarchar(256)  <br/> |Tipo de mídia. Consulte a [tabela medialist](medialist.md) para obter mais informações. <br/> |
|**MediaStartTime** <br/> |datetime  <br/> |Tempo em que uma solicitação de mídia foi enviada.  <br/> |
|**MediaEndTime** <br/> |datetime  <br/> |Hora de término da sessão.  <br/> |
   

