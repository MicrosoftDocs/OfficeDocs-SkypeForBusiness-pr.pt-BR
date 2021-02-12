---
title: Planejar o Enterprise Voice no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fd8d5867-0ac9-47f8-94f0-1c3ee5e25575
description: Noções básicas de planejamento do Enterprise Voice no Skype for Business Server, incluindo sites, regiões, links de rede entre sites e estimativa do tráfego de uso de voz.
ms.openlocfilehash: 8f10eed8dfcfa7a8878b673ab76fd4d1fd40cc29
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825671"
---
# <a name="plan-for-enterprise-voice-in-skype-for-business-server"></a>Planejar o Enterprise Voice no Skype for Business Server
 
Noções básicas de planejamento do Enterprise Voice no Skype for Business Server, incluindo sites, regiões, links de rede entre sites e estimativa do tráfego de uso de voz.
  
O processo de implantação do Enterprise Voice depende da sua topologia existente, da infraestrutura e da funcionalidade do Enterprise Voice que você deseja suportar. Os procedimentos necessários dependem dos recursos que você escolher, mas há outras considerações de planejamento a fazer em um nível elevado.
  
Em geral, considere o tipo e o número de sites que você deseja implantar e suas localizações geográficas, o volume de chamadas em cada site, os tipos de links de rede que conectam sites, se você deseja fornecer redundância e failover para funcionalidade de voz para cada site e se deseja usar equipamentos PBX existentes. Existem certas considerações, como alta disponibilidade, que você deve considerar ao planejar o Skype for Business Server como um todo. Essas considerações são discutidas nos tópicos desta seção, conforme necessário.
  
## <a name="sites-and-regions"></a>Sites e regiões

Primeiro, identifique os sites em sua topologia onde você implantará o Enterprise Voice e as regiões de rede às quais esses sites pertencem. Especificamente, considere como será fornecida a conectividade PSTN (rede telefônica pública comutada) a cada site. Para motivos de gerenciamento e logística, as regiões às quais esses sites pertencem podem ser um fator decisivo. Decida onde os gateways serão implantados localmente, onde serão implantados os Aparelhos de Filial (SBAs) e onde você poderá configurar os troncos SIP (localmente ou no local central) para um PROVEDOR de serviços de telefonia pela Internet (ITSP).
  
## <a name="network-links-between-sites"></a>Links de rede entre sites

Você também precisa considerar o uso de largura de banda esperado nos links de rede entre seu site central e seus sites de filial. Se você tiver ou planeja implantar links WAN resilientes entre sites, recomendamos implantar um gateway em cada filial para fornecer terminação DID (discagem direta interna) local para os usuários nesses sites. Se você tiver links WAN resilientes, mas a largura de banda em um link WAN provavelmente for restrita, configure o controle de admissão de chamada para esse link. Se você não tiver links WAN resilientes, hospedar menos de 1000 usuários em seu site de filial e não tiver administradores locais treinados do Skype for Business Server disponíveis, recomendamos que você implante um Aparelho de Filial Persistente no site de filial. Se você hospedar entre 1.000 e 5.000 usuários em seu site de filial, não tiver uma conexão WAN resiliente e tiver administradores treinados do Skype for Business Server disponíveis, recomendamos que você implante um Servidor de Filial Persistente com um pequeno gateway no site de filial. Considere também a habilitação de bypass de mídia em links restritos se você tiver um gateway par que suporte bypass de mídia.
  
## <a name="estimating-voice-usage-and-traffic"></a>Estimando o uso e o tráfego de voz

A Ferramenta de Planejamento do Microsoft Lync Server 2013 usa a métrica a seguir para estimar o tráfego do usuário em cada local e o número de portas necessárias para dar suporte a esse tráfego.
  
> Para **Tráfego leve** (uma chamada PSTN por usuário por hora), calcula-se 15 usuários por porta
> 
> Para **Tráfego médio**, (duas chamadas PSTN por usuário por hora), calcula-se 10 usuários por porta
> 
> Para **Tráfego pesado** (três ou mais chamadas PSTN por usuário por hora), calcula-se 5 usuários por porta
    
O número de portas, por sua vez, determina o número de Servidores de Mediação e gateways que serão necessários. Os gateways PSTN (rede telefônica pública comutado) que a maioria das organizações considera implantar variam de duas portas a até 960 portas. (Há gateways ainda maiores, mas eles são usados principalmente por provedores de serviços de telefonia.)
  
Por exemplo, uma organização com 10.000 usuários e tráfego médio exigiria 1000 portas. O número de gateways necessário seria igual o número total de portas necessárias, conforme determinado pela capacidade total dos gateways.
  
## <a name="components-features-and-options-of-enterprise-voice"></a>Componentes, recursos e opções do Enterprise Voice

Consulte as seções a seguir para obter mais informações sobre como planejar sua implantação do Enterprise Voice.
  
- [Componentes necessários para o Enterprise Voice no Skype for Business Server](components-required-for-enterprise-voice.md)
    
- [Planejar a conectividade PSTN no Skype for Business Server](pstn-connectivity-0.md)
    
- [Configurações de rede para os recursos avançados do Enterprise Voice no Skype for Business Server](network-settings-for-advanced-features.md)
    
- [Planejar o controle de admissão de chamadas no Skype for Business Server](call-admission-control.md)
    
- [Planejar serviços de emergência no Skype for Business Server](emergency-services.md)
    
- [Planejar bypass de mídia no Skype for Business](media-bypass.md)
    
- [Planejar linhas telefônicas privadas com o Skype for Business](private-telephone-lines.md)
    
- [Planejar o roteamento Location-Based no Skype for Business](location-based-routing.md)
    
- [Planejar recursos de gerenciamento de chamadas no Skype for Business](call-management-features.md)
    
- [Planejar a resiliência do Enterprise Voice no Skype for Business Server](enterprise-voice-resiliency.md)
    

