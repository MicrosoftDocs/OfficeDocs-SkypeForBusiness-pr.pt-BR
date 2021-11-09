---
title: Tabela Mcus no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 271b7963-8fd8-4d92-a701-1a62aaf895ee
description: A tabela Mcus é uma tabela de suporte. Cada registro armazena informações sobre um serviço de conferência. Eles podem incluir o serviço de Conferência de IM e o serviço de Conferência de Telefonia (que são executados como processos em servidores front-end), o serviço de WebConferência e o serviço de Conferência A/V.
ms.openlocfilehash: abbbe20d6b247b23f0042dcc3bf552dd4a1362f1
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60846304"
---
# <a name="mcus-table-in-skype-for-business-server-2015"></a>Tabela Mcus no Skype for Business Server 2015
 
A tabela Mcus é uma tabela de suporte. Cada registro armazena informações sobre um serviço de conferência. Eles podem incluir o serviço de Conferência de IM e o serviço de Conferência de Telefonia (que são executados como processos em servidores front-end), o serviço de WebConferência e o serviço de Conferência A/V. 
  
|**Column**|**Tipo de dados**|**Chave/Índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**McuId** <br/> |int  <br/> |Primário  <br/> |Número exclusivo que identifica esse servidor de conferência.  <br/> |
|**McuUri** <br/> |nvarchar(450)  <br/> | <br/> | <br/> |
|**McuTypeId** <br/> |inyint  <br/> | Foreign <br/> |Tipo de servidor de conferência, como conf:chat (para IMs) ou conf:audio-video. Consulte a [tabela UriTypes para](uritypes.md) obter mais informações. <br/> |
   

