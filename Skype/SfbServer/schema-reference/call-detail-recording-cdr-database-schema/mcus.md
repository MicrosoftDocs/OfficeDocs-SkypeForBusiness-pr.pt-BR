---
title: Tabela MCUs no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 271b7963-8fd8-4d92-a701-1a62aaf895ee
description: A tabela MCUs é uma tabela de suporte. Cada registro armazena informações sobre um serviço de conferência. Eles podem incluir o serviço de conferência de mensagem instantânea e o serviço de conferência de telefonia (que são executados como processos em servidores front-end) e o serviço de conferência via Web e o serviço de conferência A/V.
ms.openlocfilehash: fcd12bcc8da7aa6513d78e1a9c4a6f11930065aa
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296039"
---
# <a name="mcus-table-in-skype-for-business-server-2015"></a>Tabela MCUs no Skype for Business Server 2015
 
A tabela MCUs é uma tabela de suporte. Cada registro armazena informações sobre um serviço de conferência. Eles podem incluir o serviço de conferência de mensagem instantânea e o serviço de conferência de telefonia (que são executados como processos em servidores front-end) e o serviço de conferência via Web e o serviço de conferência A/V. 
  
|**Coluna**|**Tipo de dados**|**Chave/índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**McuId** <br/> |int  <br/> |Primária  <br/> |Número exclusivo que identifica esse servidor de conferência.  <br/> |
|**McuUri** <br/> |nvarchar (450)  <br/> | <br/> | <br/> |
|**McuTypeId** <br/> |inyint  <br/> | Exterior <br/> |Tipo de servidor de conferência, como conf: Chat (para IMs) ou conf: Audio-Video. Consulte a [tabela UriTypes](uritypes.md) para obter mais informações. <br/> |
   

