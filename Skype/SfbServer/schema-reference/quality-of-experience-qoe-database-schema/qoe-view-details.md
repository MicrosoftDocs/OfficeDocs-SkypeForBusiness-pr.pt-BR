---
title: Detalhes de exibição de QoE
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6a658318-a317-4546-a44c-a9c473d8e86a
description: Modos de exibição abordam os cenários mais comuns para retornar dados do banco de dados SQL de QoE. É recomendável exibições usadas para a criação de relatórios personalizados em vez de acessar diretamente as tabelas de banco de dados; Isso ocorre porque os modos de exibição estão mais prováveis manter a compatibilidade com versões futuras com versões anteriores.
ms.openlocfilehash: 2726900a1fc31c6e69571123c87137b3291a507e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33924861"
---
# <a name="qoe-view-details"></a>Detalhes de exibição de QoE
 
Modos de exibição abordam os cenários mais comuns para retornar dados do banco de dados SQL de QoE. É recomendável exibições usadas para a criação de relatórios personalizados em vez de acessar diretamente as tabelas de banco de dados; Isso ocorre porque os modos de exibição estão mais prováveis manter a compatibilidade com versões futuras com versões anteriores.
  
|**Nome da exibição**|**Descrição**|
|:-----|:-----|
|[Exibir audiostreamdetail](audiostreamdetail.md) <br/> |Armazena informações sobre cada transmissão de áudio no banco de dados.  <br/> |
|[Exibir MediaLine](medialine.md) <br/> |Armazena informações sobre cada linha de mídia no banco de dados. Normalmente, uma sessão de áudio conterá uma linha de mídia de áudio. Um áudio e vídeo (A / V) sessão normalmente contém uma linha de mídia de áudio e uma linha de mídia de vídeo; No entanto, a sessão pode conter duas linhas de mídia de vídeo, se um dispositivo de conferência for usado, ou se o modo de exibição de galeria é usado.  <br/> |
|[Exibir NetworkConfigurationSettings](networkconfigurationsettings.md) <br/> |Armazena informações sobre a configuração de rede.  <br/> |
|[Modo de exibição de sessão](session-0.md) <br/> |Armazena informações sobre sessões que têm registros no banco de dados.  <br/> |
|[Exibir UserAgent](useragent-0.md) <br/> |Armazena informações sobre os agentes de usuário que participaram de sessões que têm registros no banco de dados.  <br/> |
|[Exibir videostreamdetail](videostreamdetail.md) <br/> |Armazena informações sobre cada transmissão de vídeo no banco de dados.  <br/> |
   

