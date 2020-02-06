---
title: Detalhes de exibição de QoE
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6a658318-a317-4546-a44c-a9c473d8e86a
description: Os modos de exibição abrangem os cenários mais comuns para retornar dados do banco de dados do QoE SQL. Ele é recomendado para a criação de relatórios personalizados, em vez de acessar diretamente as tabelas de banco de dados; Isso porque os modos de exibição são mais prováveis de manter a compatibilidade retroativa com versões futuras.
ms.openlocfilehash: d207c2cff86c398fed62023b30d193e974cbca7a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41807169"
---
# <a name="qoe-view-details"></a>Detalhes de exibição de QoE
 
Os modos de exibição abrangem os cenários mais comuns para retornar dados do banco de dados do QoE SQL. Ele é recomendado para a criação de relatórios personalizados, em vez de acessar diretamente as tabelas de banco de dados; Isso porque os modos de exibição são mais prováveis de manter a compatibilidade retroativa com versões futuras.
  
|**Nome do modo de exibição**|**Descrição**|
|:-----|:-----|
|[Exibição AudioStreamDetail](audiostreamdetail.md) <br/> |Armazena informações sobre cada fluxo de áudio no banco de dados.  <br/> |
|[Modo de exibição de mídia](medialine.md) <br/> |Armazena informações sobre cada linha de mídia no banco de dados. Uma sessão de áudio geralmente contém uma linha de mídia de áudio. Uma sessão de áudio e vídeo (A/V) geralmente contém uma linha de mídia de áudio e uma linha de mídia de vídeo; no entanto, a sessão pode conter duas linhas de mídia de vídeo se um dispositivo de conferência for usado ou se o modo de exibição de galeria for usado.  <br/> |
|[Exibição NetworkConfigurationSettings](networkconfigurationsettings.md) <br/> |Armazena informações sobre a configuração de rede.  <br/> |
|[Modo de exibição sessão](session-0.md) <br/> |Armazena informações sobre sessões que têm registros no banco de dados.  <br/> |
|[Exibição do UserAgent](useragent-0.md) <br/> |Armazena informações sobre os agentes de usuário envolvidos em sessões que têm registros no banco de dados.  <br/> |
|[Exibição VideoStreamDetail](videostreamdetail.md) <br/> |Armazena informações sobre cada fluxo de vídeo no banco de dados.  <br/> |
   

