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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Optimization
description: Este artigo fornece informações sobre como usar um servidor proxy com Skype for Business.
ms.openlocfilehash: b0f8e9898e2c898387e7f726b470013dcf62caae
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58585985"
---
# <a name="proxy-servers-for-skype-for-business-online"></a>Servidores proxy para Skype for Business Online

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Este artigo fornece orientações sobre como usar um servidor proxy com Skype for Business.
  
## <a name="not-using-a-proxy-server-is-recommended"></a>É recomendável não usar um servidor proxy

Quanto ao tráfego do Skype for Business por meio de proxies, a Microsoft recomenda não usar proxies. Proxies não fazem com que Skype for Business mais seguro porque o tráfego já está criptografado.
  
E o uso de um proxy pode ocasionar problemas. Problemas relacionados ao desempenho podem ocorrer no ambiente devido à latência e à perda de pacote. Problemas como esses resultarão em uma experiência negativa em cenários Teams ou Skype for Business como áudio e vídeo, onde fluxos em tempo real são essenciais.
  
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
 
