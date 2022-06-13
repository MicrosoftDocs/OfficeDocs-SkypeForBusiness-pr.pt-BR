---
title: Servidores proxy para Teams ou Skype for Business Online
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: jastark
ms.topic: reference
ms.assetid: 7acaf2c2-35fa-490f-84cd-822e446e0fc7
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-collaboration
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Optimization
- seo-marvel-apr2020
description: Este artigo fornece informações sobre como usar um servidor proxy com Microsoft Teams ou Skype for Business.
ms.openlocfilehash: 61a1878b3c7057de7dddbcd63c480f80c2f16e0f
ms.sourcegitcommit: 91cfb1a9c527d605300580c3acad63834ee54682
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/13/2022
ms.locfileid: "66045430"
---
# <a name="proxy-servers-for-teams-or-skype-for-business-online"></a>Servidores proxy para Teams ou Skype for Business Online

Este artigo fornece diretrizes sobre como usar um servidor proxy com Teams ou Skype for Business.
  
## <a name="not-using-a-proxy-server-is-recommended"></a>É recomendável não usar um servidor proxy

Quando se trata de Teams ou Skype for Business por proxies, a Microsoft recomenda ignorar proxies. Os proxies não tornam as Teams ou Skype for Business mais seguras porque o tráfego já está criptografado.
  
E o uso de um proxy pode ocasionar problemas. Problemas relacionados ao desempenho podem ocorrer no ambiente devido à latência e à perda de pacote. Problemas como esses resultarão em uma experiência negativa em cenários Teams ou Skype for Business como áudio e vídeo, em que os fluxos em tempo real são essenciais.
  
## <a name="if-you-need-to-use-a-proxy-server"></a>Caso seja necessário o uso de um servidor proxy

Algumas organizações não têm nenhuma opção para ignorar um proxy para Teams ou Skype for Business tráfego. Nesse caso, os problemas mencionados acima deverão ser levados em consideração.
  
A Microsoft também recomenda:
  
- O uso de resolução DNS externa
    
- O uso de UDP direto com base em roteamento
    
- Permissão para tráfego UDP
    
- Seguindo as outras recomendações em nossas diretrizes de rede: [preparar a rede da sua organização para Teams](prepare-network.md)
  
    
A observação desta diretriz minimizará problemas potenciais.
  
## <a name="related-topics"></a>Tópicos relacionados

[Princípios de conectividade de rede do Microsoft 365 e do Office 365](/microsoft-365/enterprise/microsoft-365-network-connectivity-principles)

[Preparo da rede da sua organização para o Teams](prepare-network.md)