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
description: A tabela Mcus é uma tabela de suporte. Cada registro armazena informações sobre um serviço de conferência. Eles podem incluir o serviço de Conferência de IM e o serviço de Conferência de Telefonia (que é executado como processos em servidores front-end), o serviço de Webconferência e o serviço de Conferência A/V.
ms.openlocfilehash: fe43bfc747cd08febe00a68925ad520b6add5846
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821421"
---
# <a name="mcus-table-in-skype-for-business-server-2015"></a>Tabela Mcus no Skype for Business Server 2015
 
A tabela Mcus é uma tabela de suporte. Cada registro armazena informações sobre um serviço de conferência. Eles podem incluir o serviço de Conferência de IM e o serviço de Conferência de Telefonia (que é executado como processos em servidores front-end), o serviço de Webconferência e o serviço de Conferência A/V. 
  
|**Coluna**|**Tipo de dados**|**Chave/Índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**McuId** <br/> |int  <br/> |Primário  <br/> |Número exclusivo que identifica este servidor de conferência.  <br/> |
|**McuUri** <br/> |nvarchar(450)  <br/> | <br/> | <br/> |
|**McuTypeId** <br/> |inyint  <br/> | Externo <br/> |Tipo de servidor de conferência, como conf:chat (para IMs) ou conf:audio-video. Consulte a [tabela UriTypes para](uritypes.md) obter mais informações. <br/> |
   

