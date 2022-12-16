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
ms.openlocfilehash: b2d46cbaa46670daf0235bfd020cae90c5bf624b
ms.sourcegitcommit: 00a526c5b9829302f7c4e0631d0c2dac50b7d004
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/16/2022
ms.locfileid: "69436677"
---
# <a name="proxy-servers-for-teams-and-skype-for-business-online"></a>Servidores proxy para Teams e Skype for Business Online

Este artigo fornece diretrizes sobre como usar um servidor proxy com o Teams ou Skype for Business.
  
## <a name="not-using-a-proxy-server-is-recommended"></a>É recomendável não usar um servidor proxy

Quando se trata de Teams ou Skype for Business tráfego sobre proxies, Microsoft recomenda ignorar proxies. Proxies não tornam o Teams ou Skype for Business mais seguros porque o tráfego já está criptografado.
  
E o uso de um proxy pode ocasionar problemas. Problemas relacionados ao desempenho podem ser introduzidos ao ambiente por meio de latência e perda de pacotes ao tentar rotear o tráfego do Teams por meio de um servidor proxy. Problemas como esses resultarão em uma experiência negativa em cenários do Teams ou Skype for Business como áudio e vídeo, em que fluxos em tempo real são essenciais.

Recomendamos que o tráfego do Teams ignore a infraestrutura do servidor proxy. Você pode querer fazer isso colocando telefones do Teams e dispositivos da Sala de Reunião em sua própria VLAN e fornecendo-lhes acesso à Internet.

## <a name="windows-based-teams-devices"></a>Windows-Based Dispositivos do Teams

As salas de reunião do Teams baseadas no Windows e os Surface Hubs dão suporte a alguns servidores proxy, mas não dão suporte a servidores proxy que exigem autenticação.

Recomendamos que esses dispositivos ignorem sua infraestrutura de proxy e acessem Microsoft serviços 365 por meio do firewall.

## <a name="android-based-teams-devices"></a>Android-Based Dispositivos do Teams

Dispositivos Teams baseados em Android, incluindo telefones do Teams, painéis, displays e placas não dão suporte a servidores proxy.

Devido à maneira como determinados componentes em execução nesses dispositivos acessam a Internet, não é possível rotear todo o tráfego por meio de um proxy. Você deve garantir que o tráfego entre esses dispositivos e Microsoft 365 serviços seja permitido por meio do firewall.

## <a name="if-you-need-to-use-a-proxy-server"></a>Caso seja necessário o uso de um servidor proxy

Algumas organizações não têm opção de ignorar um proxy para o Teams ou Skype for Business tráfego. Nesse caso, os problemas mencionados acima deverão ser levados em consideração.

> [!Note]
> Se você usar um certificado assinado privadamente em sua infraestrutura proxy, precisará instalar o certificado assinado privadamente e a cadeia de certificados no dispositivo da sala de reunião do Teams para permitir que o dispositivo confie no certificado. Não há suporte para a instalação de certificados assinados privadamente em Telefones do Teams e em outros dispositivos Teams baseados em Android.
  
A Microsoft também recomenda:
  
- Usar a resolução DNS local e externa (algumas soluções de proxy baseadas em nuvem podem fazer com que a resolução DNS ocorra em outro local).

- Garantir que o caminho entre o dispositivo teams e nosso serviço seja o mais curto e direto possível
    
- Usar o roteamento direto baseado em UDP em vez de depender do roteamento baseado em TCP para mídia
    
- Permitindo o tráfego UDP para o Teams Media (3478-3481) por meio do firewall

- Permitindo todas as URLs e IPs necessários, incluindo aqueles para Azure, Office 365, Intune e Teams Room Pro (onde usado) por meio do firewall
    
- Seguindo as outras recomendações em nossas diretrizes de rede: [Preparar a rede da sua organização para o Teams](prepare-network.md)
  
    
A observação desta diretriz minimizará problemas potenciais.
  
## <a name="related-topics"></a>Tópicos relacionados

[Princípios de conectividade de rede do Microsoft 365 e do Office 365](/microsoft-365/enterprise/microsoft-365-network-connectivity-principles)

[Preparo da rede da sua organização para o Teams](prepare-network.md)
