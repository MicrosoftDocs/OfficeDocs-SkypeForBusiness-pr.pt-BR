---
title: Servidores proxy para Teams ou Skype for Business Online
ms.author: tonysmit
author: tonysmit
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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Optimization
description: Este artigo fornece informações sobre como usar um servidor proxy com o Skype for Business.
ms.openlocfilehash: a154b36fc03dc84916d5cb4bd383ff80bef901cd
ms.sourcegitcommit: 2511cd95a186d95f4571afa4212f8e0fc207817d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/08/2020
ms.locfileid: "41863742"
---
# <a name="proxy-servers-for-skype-for-business-online"></a>Servidores proxy do Skype for Business Online

Este artigo fornece orientações sobre como usar um servidor proxy com o Skype for Business.
  
## <a name="not-using-a-proxy-server-is-recommended"></a>É recomendável não usar um servidor proxy

Quando se trata de tráfego do Skype for Business por proxies, a Microsoft recomenda ignorar proxies. Proxies não tornar o Skype for Business mais seguro porque o tráfego já está criptografado.
  
E ter um proxy pode causar problemas. Problemas relacionados ao desempenho podem ser introduzidos ao ambiente por meio da latência e da perda de pacotes. Problemas como esses resultarão em uma experiência negativa em cenários como áudio e vídeo do Teams ou skype for Business, em que os fluxos em tempo real são essenciais.
  
## <a name="if-you-need-to-use-a-proxy-server"></a>Caso seja necessário o uso de um servidor proxy

Algumas organizações não têm a opção de não usar um proxy para o tráfego do Skype for Business. Nesse caso, os problemas mencionados acima deverão ser levados em consideração.
  
A Microsoft também recomenda:
  
- O uso de resolução DNS externa
    
- O uso de UDP direto com base em roteamento
    
- Permissão para tráfego UDP
    
- Seguindo as outras recomendações em nossas diretrizes de rede:
    
  - [Qualidade de mídia e desempenho da conectividade de rede no Skype for Business Online](media-quality-and-network-connectivity-performance.md)
    
  - [Como otimizar sua rede para o Skype for Business Online](optimizing-your-network.md)
    
A observação desta diretriz minimizará problemas potenciais.
  
## <a name="related-topics"></a>Tópicos relacionados

[Como otimizar sua rede para o Skype for Business Online](optimizing-your-network.md)
 