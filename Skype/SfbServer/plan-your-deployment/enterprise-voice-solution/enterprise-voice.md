---
title: Planejar Enterprise Voice no Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fd8d5867-0ac9-47f8-94f0-1c3ee5e25575
description: Enterprise Voice noções básicas de planejamento em Skype for Business Server, incluindo sites, regiões, links de rede entre sites e estimativa de tráfego de uso de voz.
ms.openlocfilehash: 60b762d2e9ef49d912dc00407d7b12d44ec334c0
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60762139"
---
# <a name="plan-for-enterprise-voice-in-skype-for-business-server"></a>Planejar Enterprise Voice no Skype for Business Server
 
Enterprise Voice noções básicas de planejamento em Skype for Business Server, incluindo sites, regiões, links de rede entre sites e estimativa de tráfego de uso de voz.
  
O processo de implantação para Enterprise Voice depende de sua topologia, infraestrutura e a funcionalidade de Enterprise Voice que você deseja dar suporte. Os procedimentos necessários dependem dos recursos que você escolher, mas há outras considerações de planejamento a fazer em um nível elevado.
  
Em geral, considere o tipo e o número de sites que você deseja implantar e suas localizações geográficas, o volume de chamadas em cada site, os tipos de links de rede que conectam sites, se você deseja fornecer redundância e failover para a funcionalidade de voz para cada site e se deseja usar equipamentos PBX existentes. Há algumas considerações, como alta disponibilidade, que você deve considerar ao planejar Skype for Business Server como um todo. Essas considerações são discutidas em tópicos ao longo desta seção, conforme necessário.
  
## <a name="sites-and-regions"></a>Sites e regiões

Primeiro, identifique os sites em sua topologia onde você implantará Enterprise Voice e as regiões de rede às quais esses sites pertencem. Especificamente, considere como será fornecida a conectividade PSTN (rede telefônica pública comutada) a cada site. Para motivos de gerenciamento e logística, as regiões às quais esses sites pertencem podem ser um fator decisivo. Decida onde os gateways serão implantados localmente, onde os Aparelhos de Filial (SBAs) serão implantados e onde você pode configurar troncos SIP (localmente ou no site central) para um provedor de serviços de telefonia da Internet (ITSP).
  
## <a name="network-links-between-sites"></a>Links de rede entre sites

Você também precisa considerar o uso de largura de banda esperado nos links de rede entre seu site central e seus sites de filial. Se você tiver ou planeja implantar links wan resilientes entre sites, recomendamos implantar um gateway em cada site de filial para fornecer a terminação de discagem interna (DID) local para usuários nesses sites. Se você tiver links WAN resilientes, mas a largura de banda em um link WAN provavelmente for restrita, configure o controle de admissão de chamada para esse link. Se você não tiver links WAN resilientes, hospede menos de 1.000 usuários em seu site de filial e não tenha administradores locais treinados Skype for Business Server disponíveis, recomendamos implantar um Aparelho de Filial Persistente no site da filial. Se você hospedar entre 1.000 e 5.000 usuários em seu site de filial, não tiver uma conexão WAN resiliente e tiver treinado administradores Skype for Business Server disponíveis, recomendamos implantar um Servidor de Filial Persistente com um pequeno gateway no site da filial. Considere também a habilitação de bypass de mídia em links restritos se você tiver um gateway par que suporte bypass de mídia.
  
## <a name="estimating-voice-usage-and-traffic"></a>Estimando o uso e o tráfego de voz

A Ferramenta de Planejamento do Microsoft Lync Server 2013 usa a métrica a seguir para estimar o tráfego do usuário em cada site e o número de portas necessárias para dar suporte a esse tráfego.
  
> Para **Tráfego leve** (uma chamada PSTN por usuário por hora), calcula-se 15 usuários por porta
> 
> Para **Tráfego médio**, (duas chamadas PSTN por usuário por hora), calcula-se 10 usuários por porta
> 
> Para **Tráfego pesado** (três ou mais chamadas PSTN por usuário por hora), calcula-se 5 usuários por porta
    
O número de portas, por sua vez, determina o número de Servidores de Mediação e gateways que serão necessários. Os gateways PSTN (rede telefônica pública comutado) que a maioria das organizações considera implantar no intervalo de tamanho de duas portas para até 960 portas. (Há gateways ainda maiores, mas eles são usados principalmente por provedores de serviços de telefonia.)
  
Por exemplo, uma organização com 10.000 usuários e tráfego médio exigiria 1000 portas. O número de gateways necessário seria igual o número total de portas necessárias, conforme determinado pela capacidade total dos gateways.
  
## <a name="components-features-and-options-of-enterprise-voice"></a>Componentes, recursos e opções de Enterprise Voice

Consulte as seções a seguir para obter mais informações sobre como planejar sua Enterprise Voice implantação.
  
- [Componentes necessários para Enterprise Voice no Skype for Business Server](components-required-for-enterprise-voice.md)
    
- [Planejar a conectividade PSTN no Skype for Business Server](pstn-connectivity-0.md)
    
- [Configurações de rede para os recursos de Enterprise Voice avançados no Skype for Business Server](network-settings-for-advanced-features.md)
    
- [Planejar o controle de admissão de chamada Skype for Business Server](call-admission-control.md)
    
- [Planejar serviços de emergência no Skype for Business Server](emergency-services.md)
    
- [Planejar o bypass de mídia Skype for Business](media-bypass.md)
    
- [Planejar linhas telefônicas privadas com Skype for Business](private-telephone-lines.md)
    
- [Planejar o Location-Based roteamento no Skype for Business](location-based-routing.md)
    
- [Planejar recursos de gerenciamento de chamada em Skype for Business](call-management-features.md)
    
- [Planejar Enterprise Voice resiliência no Skype for Business Server](enterprise-voice-resiliency.md)
    

