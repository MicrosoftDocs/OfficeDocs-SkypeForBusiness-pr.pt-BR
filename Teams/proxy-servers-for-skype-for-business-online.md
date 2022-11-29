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
ms.openlocfilehash: cdb4e6ccf05f597c87d066c18b1722eb08f89374
ms.sourcegitcommit: e9718ad7e23317d490b238b3801267cb2e6b26e2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/28/2022
ms.locfileid: "69176668"
---
# <a name="proxy-servers-for-teams-or-skype-for-business-online"></a>Servidores proxy para Teams ou Skype for Business Online

Este artigo fornece diretrizes sobre como usar um servidor proxy com o Teams ou Skype for Business.
  
## <a name="not-using-a-proxy-server-is-recommended"></a>É recomendável não usar um servidor proxy

Quando se trata de Teams ou Skype for Business tráfego sobre proxies, Microsoft recomenda ignorar proxies. Proxies não tornam o Teams ou Skype for Business mais seguros porque o tráfego já está criptografado.
  
E o uso de um proxy pode ocasionar problemas. Problemas relacionados ao desempenho podem ser introduzidos ao ambiente por meio de latência e perda de pacotes ao tentar rotear o tráfego do Teams por meio de um servidor proxy. Problemas como esses resultarão em uma experiência negativa em cenários do Teams ou Skype for Business como áudio e vídeo, em que fluxos em tempo real são essenciais.

Recomendamos que o tráfego do Teams ignore a infraestrutura do servidor proxy.

## <a name="teams-phones"></a>Telefones do Teams

Os Telefones do Teams não dão suporte a servidores proxy.

Nossa recomendação é garantir que o tráfego de sinalização (TCP 443) e mídia (UDP 3478-3481) ignore a infraestrutura do servidor proxy.

## <a name="teams-meeting-rooms-and-panels"></a>Salas e Painéis de Reunião do Teams

Nossa recomendação é garantir que suas Salas de Reunião do Teams ignorem a infraestrutura de proxy.

As Salas de Reunião do Teams baseadas no Windows dão suporte a servidores proxy, mas não dão suporte a servidores proxy que exigem autenticação. As Salas de Reunião do Teams baseadas em Android não dão suporte a servidores proxy.
  
## <a name="if-you-need-to-use-a-proxy-server"></a>Caso seja necessário o uso de um servidor proxy

Algumas organizações não têm opção de ignorar um proxy para o Teams ou Skype for Business tráfego. Nesse caso, os problemas mencionados acima deverão ser levados em consideração.
  
A Microsoft também recomenda:
  
- Usar a resolução DNS local e externa (algumas soluções de proxy baseadas em nuvem podem fazer com que a resolução DNS ocorra em outro local).
    
- Usar o roteamento direto baseado em UDP em vez de depender do roteamento baseado em TCP para mídia
    
- Permitindo o tráfego UDP (3478-3481)

- Permitindo todas as URLs e IPs necessários, incluindo aqueles para Azure, Office 365, Intune e Teams Room Pro (onde usado)
    
- Seguindo as outras recomendações em nossas diretrizes de rede: [Preparar a rede da sua organização para o Teams](prepare-network.md)
  
    
A observação desta diretriz minimizará problemas potenciais.
  
## <a name="related-topics"></a>Tópicos relacionados

[Princípios de conectividade de rede do Microsoft 365 e do Office 365](/microsoft-365/enterprise/microsoft-365-network-connectivity-principles)

[Preparo da rede da sua organização para o Teams](prepare-network.md)
