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
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Optimization
- seo-marvel-apr2020
description: Este artigo fornece informações sobre como usar um servidor proxy com o Microsoft Teams ou o Skype for Business.
ms.openlocfilehash: 3d8e2e067cce4214f51ee54ec08bafa1f4100770
ms.sourcegitcommit: f586d2765195dbd5b7cf65615a03a1cb098c5466
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/09/2020
ms.locfileid: "44665953"
---
# <a name="proxy-servers-for-teams-or-skype-for-business-online"></a>Servidores proxy para Teams ou Skype for Business Online

Este artigo fornece diretrizes sobre como usar um servidor proxy com o Teams ou o Skype for Business.
  
## <a name="not-using-a-proxy-server-is-recommended"></a>É recomendável não usar um servidor proxy

Quando se trata de Teams ou tráfego do Skype for Business em proxies, a Microsoft recomenda ignorar proxies. Os proxies não tornam o Microsoft Teams nem o Skype for Business mais seguros porque o tráfego já está criptografado.
  
E ter um proxy pode causar problemas. Os problemas relacionados ao desempenho podem ser introduzidos ao ambiente por meio de latência e perda de pacote. Problemas como esses podem resultar em uma experiência negativa em tais equipes ou em cenários do Skype for Business como áudio e vídeo, em que os fluxos em tempo real são essenciais.
  
## <a name="if-you-need-to-use-a-proxy-server"></a>Caso seja necessário o uso de um servidor proxy

Algumas organizações não têm a opção de ignorar um proxy para o Microsoft Teams ou o tráfego do Skype for Business. Se esse for o caso para você, os problemas mencionados acima devem ser mantidos em mente.
  
A Microsoft também recomenda:
  
- O uso de resolução DNS externa
    
- O uso de UDP direto com base em roteamento
    
- Permissão para tráfego UDP
    
- Seguindo as outras recomendações em nossas diretrizes de rede: [preparar a rede da sua organização para o Teams](prepare-network.md)
  
    
A observação desta diretriz minimizará problemas potenciais.
  
## <a name="related-topics"></a>Tópicos relacionados

[Princípios de conectividade de rede do Microsoft 365 e do Office 365](https://aka.ms/pnc)

[Prepare a rede da sua organização para o Teams](prepare-network.md)
