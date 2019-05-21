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
ms.collection: M365-collaboration
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Optimization
description: Este artigo fornece informações sobre como usar um servidor proxy com o Teams ou o Skype for Business.
ms.openlocfilehash: e0733393a40c2d2c2fd62d986a4b4d66d0c2c35f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34304366"
---
# <a name="proxy-servers-for-teams-or-skype-for-business-online"></a>Servidores proxy para Teams ou Skype for Business Online

Este artigo fornece diretrizes sobre como usar um servidor proxy com o Teams ou o Skype for Business.
  
## <a name="not-using-a-proxy-server-is-recommended"></a>É recomendável não usar um servidor proxy

Quando se trata de Teams ou tráfego do Skype for Business em proxies, a Microsoft recomenda ignorar proxies. Os proxies não tornam o Microsoft Teams nem o Skype for Business mais seguros porque o tráfego já está criptografado.
  
E o uso de um proxy pode ocasionar problemas. Problemas relacionados ao desempenho podem ocorrer no ambiente devido à latência e à perda de pacote. Problemas como esses podem resultar em uma experiência negativa em tais equipes ou em cenários do Skype for Business como áudio e vídeo, em que os fluxos em tempo real são essenciais.
  
## <a name="if-you-need-to-use-a-proxy-server"></a>Caso seja necessário o uso de um servidor proxy

Algumas organizações não têm a opção de ignorar um proxy para o Microsoft Teams ou o tráfego do Skype for Business. Nesse caso, os problemas mencionados acima deverão ser levados em consideração.
  
A Microsoft também recomenda:
  
- O uso de resolução DNS externa
    
- O uso de UDP direto com base em roteamento
    
- Permissão para tráfego UDP
    
- Seguindo as outras recomendações em nossas diretrizes de rede:
    
  - [Qualidade de mídia e desempenho da conectividade de rede no Skype for Business Online](https://support.office.com/en-us/article/Media-Quality-and-Network-Connectivity-Performance-in-Skype-for-Business-Online-5fe3e01b-34cf-44e0-b897-b0b2a83f0917)
    
  - [Como otimizar sua rede para o Skype for Business Online](https://support.office.com/en-us/article/Optimizing-your-network-for-Skype-for-Business-Online-b363bdca-b00d-4150-96c3-ec7eab5a8a43)
    
A observação desta diretriz minimizará problemas potenciais.
  
## <a name="related-topics"></a>Tópicos relacionados

[Como otimizar sua rede para o Skype for Business Online](https://support.office.com/en-us/article/Optimizing-your-network-for-Skype-for-Business-Online-b363bdca-b00d-4150-96c3-ec7eab5a8a43)

  
 