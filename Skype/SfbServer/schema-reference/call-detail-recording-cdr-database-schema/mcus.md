---
title: Tabela Mcus no Skype for Business Server 2015
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
ms.assetid: 271b7963-8fd8-4d92-a701-1a62aaf895ee
description: A tabela Mcus é uma tabela de suporte. Cada registro armazena informações sobre um serviço de conferência. Eles podem incluir o serviço de Conferência de IM e o serviço de Conferência de Telefonia (que são executados como processos em servidores front-end), o serviço de WebConferência e o serviço de Conferência A/V.
ms.openlocfilehash: 501736f91073b193f68a22dee8bf54899ee1250373258cf49fb19ed02af5c5e1
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54352070"
---
# <a name="mcus-table-in-skype-for-business-server-2015"></a>Tabela Mcus no Skype for Business Server 2015
 
A tabela Mcus é uma tabela de suporte. Cada registro armazena informações sobre um serviço de conferência. Eles podem incluir o serviço de Conferência de IM e o serviço de Conferência de Telefonia (que são executados como processos em servidores front-end), o serviço de WebConferência e o serviço de Conferência A/V. 
  
|**Coluna**|**Tipo de dados**|**Chave/Índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**McuId** <br/> |int  <br/> |Primário  <br/> |Número exclusivo que identifica esse servidor de conferência.  <br/> |
|**McuUri** <br/> |nvarchar(450)  <br/> | <br/> | <br/> |
|**McuTypeId** <br/> |inyint  <br/> | Foreign <br/> |Tipo de servidor de conferência, como conf:chat (para IMs) ou conf:audio-video. Consulte a [tabela UriTypes para](uritypes.md) obter mais informações. <br/> |
   

