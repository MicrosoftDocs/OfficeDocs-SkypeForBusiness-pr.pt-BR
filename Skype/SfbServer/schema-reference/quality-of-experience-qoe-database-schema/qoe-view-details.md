---
title: Detalhes de exibição de QoE
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 6a658318-a317-4546-a44c-a9c473d8e86a
description: Os views abrangem os cenários mais comuns para retornar dados do banco de dados de SQL QoE. Recomendamos exibições usadas para a criação de relatórios personalizados em vez de acessar diretamente as tabelas de banco de dados; isso porque as exibições têm mais probabilidade de manter a compatibilidade com versões futuras.
ms.openlocfilehash: d812af701a0073b8be4188b98cd94a66d50c68d3
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62385379"
---
# <a name="qoe-view-details"></a>Detalhes de exibição de QoE
 
Os views abrangem os cenários mais comuns para retornar dados do banco de dados de SQL QoE. Recomendamos exibições usadas para a criação de relatórios personalizados em vez de acessar diretamente as tabelas de banco de dados; isso porque as exibições têm mais probabilidade de manter a compatibilidade com versões futuras.
  
|**Nome do Modo de Exibição**|**Descrição**|
|:-----|:-----|
|[Exibição AudioStreamDetail](audiostreamdetail.md) <br/> |Armazena informações sobre cada fluxo de áudio no banco de dados.  <br/> |
|[Exibição MediaLine](medialine.md) <br/> |Armazena informações sobre cada linha de mídia no banco de dados. Uma sessão de áudio normalmente contém uma linha de mídia de áudio. Uma sessão de áudio e vídeo (A/V) normalmente contém uma linha de mídia de áudio e uma linha de mídia de vídeo; no entanto, a sessão pode conter duas linhas de mídia de vídeo se um dispositivo de conferência ou o modo de exibição de galeria for usado.  <br/> |
|[Exibição NetworkConfigurationSettings](networkconfigurationsettings.md) <br/> |Armazena informações sobre a configuração de rede.  <br/> |
|[Exibição de sessão](session-0.md) <br/> |Armazena informações sobre sessões que têm registros no banco de dados.  <br/> |
|[Exibição UserAgent](useragent-0.md) <br/> |Armazena informações sobre os agentes do usuário envolvidos em sessões que têm registros no banco de dados.  <br/> |
|[Exibição VideoStreamDetail](videostreamdetail.md) <br/> |Armazena informações sobre cada fluxo de vídeo no banco de dados.  <br/> |
   

