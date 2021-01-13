---
title: Detalhes de exibição de QoE
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
ms.assetid: 6a658318-a317-4546-a44c-a9c473d8e86a
description: As exibições abrangem os cenários mais comuns para retornar dados do banco de dados SQL de QoE. São exibições recomendadas usadas para criar relatórios personalizados em vez de acessar diretamente as tabelas de banco de dados; isso porque as exibições têm mais probabilidade de manter a compatibilidade com versões futuras.
ms.openlocfilehash: cabe483da624d801b9b87d51ba61caed7a22f7d4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834471"
---
# <a name="qoe-view-details"></a>Detalhes de exibição de QoE
 
As exibições abrangem os cenários mais comuns para retornar dados do banco de dados SQL de QoE. São exibições recomendadas usadas para criar relatórios personalizados em vez de acessar diretamente as tabelas de banco de dados; isso porque as exibições têm mais probabilidade de manter a compatibilidade com versões futuras.
  
|**Nome do Modo de Exibição**|**Descrição**|
|:-----|:-----|
|[Exibição AudioStreamDetail](audiostreamdetail.md) <br/> |Armazena informações sobre cada fluxo de áudio no banco de dados.  <br/> |
|[Exibição MediaLine](medialine.md) <br/> |Armazena informações sobre cada linha de mídia no banco de dados. Uma sessão de áudio normalmente contém uma linha de mídia de áudio. Uma sessão de áudio e vídeo (A/V) normalmente contém uma linha de mídia de áudio e uma linha de mídia de vídeo; no entanto, a sessão pode conter duas linhas de mídia de vídeo se um dispositivo de conferência ou o modo de exibição de galeria for usado.  <br/> |
|[Exibição NetworkConfigurationSettings](networkconfigurationsettings.md) <br/> |Armazena informações sobre a configuração de rede.  <br/> |
|[Exibição de sessão](session-0.md) <br/> |Armazena informações sobre sessões que tenham registros no banco de dados.  <br/> |
|[Exibição UserAgent](useragent-0.md) <br/> |Armazena informações sobre os agentes do usuário envolvidos em sessões com registros no banco de dados.  <br/> |
|[Exibição VideoStreamDetail](videostreamdetail.md) <br/> |Armazena informações sobre cada fluxo de vídeo no banco de dados.  <br/> |
   

