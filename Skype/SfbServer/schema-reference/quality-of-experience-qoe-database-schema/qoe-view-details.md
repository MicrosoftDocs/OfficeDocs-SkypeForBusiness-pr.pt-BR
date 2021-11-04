---
title: Detalhes de exibição de QoE
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
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
ms.openlocfilehash: 5e0a4b4c83d6cc2b04eb2075e8f6248a0061cbdb
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60741767"
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
   

