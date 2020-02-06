---
title: Plano para Enterprise Voice no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.openlocfilehash: 7ef2a37a1ab39dd9c2e40544e06cfb995e846f7a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802891"
---
# <a name="plan-for-enterprise-voice-in-skype-for-business-server"></a>Plano para Enterprise Voice no Skype for Business Server
 
Noções básicas de planejamento do Enterprise Voice no Skype for Business Server, incluindo sites, regiões, links de rede entre sites e estimativa do tráfego de uso de voz.
  
O processo de implantação do Enterprise Voice depende da topologia existente, da infraestrutura e da funcionalidade do Enterprise Voice às quais você deseja dar suporte. Os procedimentos necessários dependem dos recursos que você escolher, mas há outras considerações de planejamento a fazer em um nível elevado.
  
Em geral, considere o tipo e o número de sites que você deseja implantar e seus locais geográficos, o volume da chamada em cada site, os tipos de links de rede que conectam sites, se você deseja fornecer redundância e failover para funcionalidade de voz para cada e se você deseja usar equipamento PBX existente. Há certas considerações, como alta disponibilidade, que você deve considerar ao planejar o Skype for Business Server como um todo. Essas considerações são discutidas em tópicos em toda esta seção, conforme necessário.
  
## <a name="sites-and-regions"></a>Locais e regiões

Em primeiro lugar, identifique os sites na sua topologia em que você vai implantar o Enterprise Voice e as regiões de rede às quais esses sites pertencem. Especificamente, considere como será fornecida a conectividade PSTN (rede telefônica pública comutada) a cada site. Para motivos de gerenciamento e logística, as regiões às quais esses sites pertencem podem ser um fator decisivo. Decida onde os gateways serão implantados localmente, onde utensílios de ramificação sobreviventes (SBAs) serão implantados e onde você pode configurar troncos SIP (localmente ou no site central) para um provedor de serviços de telefonia pela Internet (ITSP).
  
## <a name="network-links-between-sites"></a>Links de rede entre locais

Você também precisa considerar o uso de largura de banda esperado nos links de rede entre o seu site central e seus sites de filiais. Se você tem, ou planeja implantar, links de WAN resistentes entre sites, recomendamos que implante um gateway em cada site de filial para fornecer cancelamento local direto do Direct Inward (DID) para usuários naqueles sites. Se você tiver links WAN resilientes, mas a largura de banda em um link WAN provavelmente for restrita, configure o controle de admissão de chamada para esse link. Se você não tiver links de WAN resilientes, hospede menos de 1000 usuários no seu site de filial e não tiver administradores do Skype for Business Server treinados, recomendamos que você implante um aparelho de ramificação sobreviventes no site da filial. Se você estiver hospedando entre os usuários do 1000 e do 5000 no seu site da sua filial, não há uma conexão WAN resistente e tiver os administradores do Skype for Business Server treinados, recomendamos implantar um servidor de ramificação sobreviventes com um pequeno gateway no site da filial. Considere também a habilitação de bypass de mídia em links restritos se você tiver um gateway par que suporte bypass de mídia.
  
## <a name="estimating-voice-usage-and-traffic"></a>Estimando uso e tráfego de voz

O Microsoft Lync Server 2013, ferramenta de planejamento usa a métrica a seguir para estimar o tráfego do usuário em cada site e o número de portas necessárias para dar suporte a esse tráfego.
  
> No caso de **Tráfego leve** (uma chamada PSTN por usuário por hora), calcula-se 15 usuários por porta.
> 
> No caso de **Tráfego médio** (duas chamadas PSTN por usuário por hora), calcula-se 10 usuários por porta.
> 
> No caso de **Tráfego pesado** (três ou mais chamadas PSTN por usuário por hora), calcula-se 5 usuários por porta.
    
O número de portas, por sua vez, determina o número de servidores e gateways de mediação que serão necessários. Os gateways de rede telefônica pública comutada (PSTN) que a maioria das organizações considera implantando o tamanho de duas portas para até 960 portas. (Ainda há gateways maiores, mas eles são usados principalmente por provedores de serviços de telefonia.)
  
Por exemplo, uma organização com 10.000 usuários e tráfego médio exigiria 1000 portas. O número de gateways necessário seria igual o número total de portas necessárias, conforme determinado pela capacidade total dos gateways.
  
## <a name="components-features-and-options-of-enterprise-voice"></a>Componentes, recursos e opções do Enterprise Voice

Confira as seções a seguir para obter mais informações sobre como planejar a implantação do Enterprise Voice.
  
- [Componentes necessários para o Enterprise Voice no Skype for Business Server](components-required-for-enterprise-voice.md)
    
- [Planejar a conectividade PSTN no Skype for Business Server](pstn-connectivity-0.md)
    
- [Configurações de rede para os recursos avançados de voz empresarial no Skype for Business Server](network-settings-for-advanced-features.md)
    
- [Planejar o controle de admissão de chamadas no Skype for Business Server](call-admission-control.md)
    
- [Planejar serviços de emergência no Skype for Business Server](emergency-services.md)
    
- [Planejar a bypass de mídia no Skype for Business](media-bypass.md)
    
- [Planejar linhas telefônicas particulares com o Skype for Business](private-telephone-lines.md)
    
- [Planejar o roteamento baseado em localização no Skype for Business](location-based-routing.md)
    
- [Planejar os recursos de gerenciamento de chamadas no Skype for Business](call-management-features.md)
    
- [Plan for Enterprise Voice resiliency in Skype for Business Server](enterprise-voice-resiliency.md)
    

